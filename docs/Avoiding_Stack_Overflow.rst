====================================
Avoiding Stack Overflow - MapToolDoc
====================================

.. contents::
   :depth: 3
..

.. container:: noprint
   :name: mw-page-base

.. container:: noprint
   :name: mw-head-base

.. container:: mw-body
   :name: content

   .. container:: mw-indicators

   .. rubric:: Avoiding Stack Overflow
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Stack Overflow
               Exceptions <#Stack_Overflow_Exceptions>`__

               -  `1.1 Overview of the
                  Problem <#Overview_of_the_Problem>`__
               -  `1.2 Description of Why the Error
                  Occurs <#Description_of_Why_the_Error_Occurs>`__
               -  `1.3 How to Determine an Appropriate Stack
                  Size <#How_to_Determine_an_Appropriate_Stack_Size>`__
               -  `1.4 How to Change the Amount of Stack
                  Space <#How_to_Change_the_Amount_of_Stack_Space>`__
               -  `1.5 Outlook for Future Versions of
                  MapTool <#Outlook_for_Future_Versions_of_MapTool>`__
               -  `1.6 Ways to Avoid Running Out of Stack
                  Space <#Ways_to_Avoid_Running_Out_of_Stack_Space>`__

         .. rubric:: Stack Overflow Exceptions
            :name: stack-overflow-exceptions

         If you create long and elaborate macros or use a lot of text in
         a macro, you will probably run into a **Stack Overflow
         Exception**. Note that because one macro can call others, it
         can be difficult to determine which macro in particular is the
         root cause of the problem.

         .. rubric:: Overview of the Problem
            :name: overview-of-the-problem

         At first only two things come to mind (don't miss more advice
         at the bottom of this page):

         #. Clean up your HTML as much as possible (e.g. remove all
            comments).
         #. Raise the stack size. (Start high and work your way down)
            *This is actually bad advice; why is explained below.*

         .. rubric:: Description of Why the Error Occurs
            :name: description-of-why-the-error-occurs

         The error happens because of the way the macro parsing works.
         It uses a `Regular
         Expression <http://en.wikipedia.org/wiki/Regular_expression>`__
         parser that starts by looking for the largest possible string
         that matches the regex, then backtracking to a shorter string
         (using recursion) if the first one ends up not working. This
         ends up requiring a huge amount of stack space in certain
         pathological strings when combined with the particular regexes
         being used by MapTool. Regular expressions require stack space
         based on the amount of text entered and how that text *might*
         match the regex. That's the whole point of
         `backtracking <http://en.wikipedia.org/wiki/Backtracking>`__ --
         the regex might match up to a certain point, so it saves its
         state on the stack and then checks the next piece.

         The errors are more likely when the text contains a lot of
         braces, brackets, and/or single/double quotes. But none of
         those are **REQUIREMENTS** for having a stack overflow occur.

         (A forum search on user "Azhrei" and the word "backtrack" or
         "backtracking" will probably find the threads that explain this
         in greater detail.)

         .. rubric:: How to Determine an Appropriate Stack Size
            :name: how-to-determine-an-appropriate-stack-size

         MapTool creates and destroys many threads on the fly and all
         the time. So the best advice would be, **Set your stack as low
         as possible**.

         The stack size allocated to a particular thread is part of the
         overall address space available to Java. So the larger you make
         the heap limit, the more of the address space that can be
         consumed by heap and thus will be unavailable for stack space.
         And the same thing works in reverse: the more stack space you
         allocate per-thread, the less heap space there will be. This is
         normally only a problem for the 32-bit Java since the maximum
         heap size is roughly **1.5GB** (depends on the platform; Unix
         systems will be slightly larger than Windows). You'll know
         you've hit this problem when you get an exception that says
         that a new Thread couldn't be created and the description will
         say "Native code". (In other words, it's the C language code
         that implements the Java Runtime Environment that is having the
         problem.)

         In the 64-bit world, the amount of address space available to
         the Java Runtime Environment is tremendous (on most hardware
         it's about 2^40 or roughly **1TB**; some hardware will support
         up to **256TB**). That means the stack size and heap space
         could be set very large. This will still have an effect on the
         machine's performance, since using more virtual memory than the
         machine has in physical memory will require *paging*. And
         paging is I/O intensive and thus will slow down the entire
         machine.

         .. rubric:: How to Change the Amount of Stack Space
            :name: how-to-change-the-amount-of-stack-space

         On all systems there is a command line parameter to the Java
         interpreter that tells it how much stack space to allocate for
         each thread and how much heap space to allocate overall. The
         question becomes, "How do I tell *my* Java installation how
         much to use?" And that depends on how you start MapTool.

         See `Stack Size#Configuring memory allocation for
         MapTool </rptools/wiki/Stack_Size#Configuring_memory_allocation_for_MapTool>`__
         for details.

         .. rubric:: Outlook for Future Versions of MapTool
            :name: outlook-for-future-versions-of-maptool

         There won't be done anything about this for MT 1.3. We'll be
         moving to JavaScript for 1.4. This should eliminate the regex
         stack overflow entirely as all macros will be JavaScript (well,
         except for a JavaScript macro with bugs in it). That language
         uses a lexical parser and not a bastardized (but easier to
         implement) regex parser. The MTscript parser is great at doing
         what it was designed to do, but it has been pushed waaaaay
         beyond it's original vision!

         .. rubric:: Ways to Avoid Running Out of Stack Space
            :name: ways-to-avoid-running-out-of-stack-space

         Here's a list of things you can do to help avoid stack overflow
         errors. They are in the order of Most Likely to Least Likely in
         terms of the level of benefit.

         #. Break up your macros into smaller parts (especially where
            you have brackets or single/double quotes, but not just in
            these cases). This helps because there is less backtracking
            possible when the macros themselves are shorter.
         #. If you have long static strings store them in a token
            property instead of the macro body. This helps because the
            content of properties are not subject to the parser line
            normal macro text is. Lib tokens work well for this. A table
            might work as well if your data is read-only.
         #. Use `strformat() </rptools/wiki/strformat>`__ to create your
            HTML, preferably with the format string stored in a token
            property. (See above.)
         #. If you get stack issues **it's better to reorganize your
            code than bump up the stack size**. As explained above,
            increasing the stack size is a bandage on the problem, and
            as you can see it's not a very good bandage either!
         #. Because of the way the regex is structured, you might be
            able to get more HTML text into a macro by using this
            construct: ``[r: "html text here"]`` This causes a different
            path to be taken in the MapTool source code, so different
            regexes are used. No guarantees on this, of course, but if
            you're desperate and don't want to spend the time to
            reorganize your macros it might help.
         #. If you get a stack overflow while creating a dynamic form,
            move the HTML part of the form into a new macro (e.g. you
            could create a user-defined function named
            **htmlBuilder(arguments)** and pass it any variable
            arguments). Then when you need the form, assign the HTML
            code first to a variable (such as **tmpCache**) and then run
            the form using the variable:

         ::

             [h: tmpCache = htmlBuilder(arguments)]
             [h: dialog("Dialog Test"): {[r:tmpCache]}]

         This issue has come up many times in the forum. This text was
         stitched together from `this latest
         thread <http://forums.rptools.net/viewtopic.php?p=192126#p192126>`__
         about it.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Avoiding_Stack_Overflow&oldid=5542"

