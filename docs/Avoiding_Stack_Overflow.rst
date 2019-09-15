.. contents::
   :depth: 3
..

.. _stack_overflow_exceptions:

Stack Overflow Exceptions
=========================

If you create long and elaborate macros or use a lot of text in a macro,
you will probably run into a **Stack Overflow Exception**. Note that
because one macro can call others, it can be difficult to determine
which macro in particular is the root cause of the problem.

.. _overview_of_the_problem:

Overview of the Problem
-----------------------

At first only two things come to mind (don't miss more advice at the
bottom of this page):

#. Clean up your HTML as much as possible (e.g. remove all comments).
#. Raise the stack size. (Start high and work your way down) *This is
   actually bad advice; why is explained below.*

.. _description_of_why_the_error_occurs:

Description of Why the Error Occurs
-----------------------------------

The error happens because of the way the macro parsing works. It uses a
`Regular Expression <http://en.wikipedia.org/wiki/Regular_expression>`__
parser that starts by looking for the largest possible string that
matches the regex, then backtracking to a shorter string (using
recursion) if the first one ends up not working. This ends up requiring
a huge amount of stack space in certain pathological strings when
combined with the particular regexes being used by MapTool. Regular
expressions require stack space based on the amount of text entered and
how that text *might* match the regex. That's the whole point of
`backtracking <http://en.wikipedia.org/wiki/Backtracking>`__ -- the
regex might match up to a certain point, so it saves its state on the
stack and then checks the next piece.

The errors are more likely when the text contains a lot of braces,
brackets, and/or single/double quotes. But none of those are
**REQUIREMENTS** for having a stack overflow occur.

(A forum search on user "Azhrei" and the word "backtrack" or
"backtracking" will probably find the threads that explain this in
greater detail.)

.. _how_to_determine_an_appropriate_stack_size:

How to Determine an Appropriate Stack Size
------------------------------------------

MapTool creates and destroys many threads on the fly and all the time.
So the best advice would be, **Set your stack as low as possible**.

The stack size allocated to a particular thread is part of the overall
address space available to Java. So the larger you make the heap limit,
the more of the address space that can be consumed by heap and thus will
be unavailable for stack space. And the same thing works in reverse: the
more stack space you allocate per-thread, the less heap space there will
be. This is normally only a problem for the 32-bit Java since the
maximum heap size is roughly **1.5GB** (depends on the platform; Unix
systems will be slightly larger than Windows). You'll know you've hit
this problem when you get an exception that says that a new Thread
couldn't be created and the description will say "Native code". (In
other words, it's the C language code that implements the Java Runtime
Environment that is having the problem.)

In the 64-bit world, the amount of address space available to the Java
Runtime Environment is tremendous (on most hardware it's about 2^40 or
roughly **1TB**; some hardware will support up to **256TB**). That means
the stack size and heap space could be set very large. This will still
have an effect on the machine's performance, since using more virtual
memory than the machine has in physical memory will require *paging*.
And paging is I/O intensive and thus will slow down the entire machine.

.. _how_to_change_the_amount_of_stack_space:

How to Change the Amount of Stack Space
---------------------------------------

On all systems there is a command line parameter to the Java interpreter
that tells it how much stack space to allocate for each thread and how
much heap space to allocate overall. The question becomes, "How do I
tell *my* Java installation how much to use?" And that depends on how
you start MapTool.

See `Stack Size#Configuring memory allocation for
MapTool <Stack_Size#Configuring_memory_allocation_for_MapTool>`__ for
details.

.. _outlook_for_future_versions_of_maptool:

Outlook for Future Versions of MapTool
--------------------------------------

There won't be done anything about this for MT 1.3. We'll be moving to
JavaScript for 1.4. This should eliminate the regex stack overflow
entirely as all macros will be JavaScript (well, except for a JavaScript
macro with bugs in it). That language uses a lexical parser and not a
bastardized (but easier to implement) regex parser. The MTscript parser
is great at doing what it was designed to do, but it has been pushed
waaaaay beyond it's original vision!

.. _ways_to_avoid_running_out_of_stack_space:

Ways to Avoid Running Out of Stack Space
----------------------------------------

Here's a list of things you can do to help avoid stack overflow errors.
They are in the order of Most Likely to Least Likely in terms of the
level of benefit.

#. Break up your macros into smaller parts (especially where you have
   brackets or single/double quotes, but not just in these cases). This
   helps because there is less backtracking possible when the macros
   themselves are shorter.
#. If you have long static strings store them in a token property
   instead of the macro body. This helps because the content of
   properties are not subject to the parser line normal macro text is.
   Lib tokens work well for this. A table might work as well if your
   data is read-only.
#. Use to create your HTML, preferably with the format string stored in
   a token property. (See above.)
#. If you get stack issues **it's better to reorganize your code than
   bump up the stack size**. As explained above, increasing the stack
   size is a bandage on the problem, and as you can see it's not a very
   good bandage either!
#. Because of the way the regex is structured, you might be able to get
   more HTML text into a macro by using this construct: This causes a
   different path to be taken in the MapTool source code, so different
   regexes are used. No guarantees on this, of course, but if you're
   desperate and don't want to spend the time to reorganize your macros
   it might help.
#. If you get a stack overflow while creating a dynamic form, move the
   HTML part of the form into a new macro (e.g. you could create a
   user-defined function named **htmlBuilder(arguments)** and pass it
   any variable arguments). Then when you need the form, assign the HTML
   code first to a variable (such as **tmpCache**) and then run the form
   using the variable:

| `` [h: tmpCache = htmlBuilder(arguments)]``
| `` [h: dialog("Dialog Test"): {[r:tmpCache]}]``

This issue has come up many times in the forum. This text was stitched
together from `this latest
thread <http://forums.rptools.net/viewtopic.php?p=192126#p192126>`__
about it.

`Category:Cookbook <Category:Cookbook>`__
