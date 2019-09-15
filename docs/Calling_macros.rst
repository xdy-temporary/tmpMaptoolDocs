.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Advanced}}

.. _calling_macros_from_another_macro:

Calling Macros From another Macro
=================================

Sometimes you want to call a macro from another macro. As a coder, you
want this often, because it enables you to split your code in small,
simple chunks that can be reused over and over again. This handy
technique also helps keep the stack size requirement low and mitigates
the need for large code-level-nesting.

When calling a macro from another macro, you will often want to transfer
data from one to the other and vice versa. In addition, it is also
important to know what happens with chat output.

There are four different ways to call a macro - and they all behave a
little bit differently. While reading this tutorial, please be sure to
follow the wiki-links provided for any items you are not familiar with,
as they will not be covered.

.. _the_four_methods_to_call_a_macro:

The Four Methods to Call a Macro
--------------------------------

.. _the_macro_roll_option:

The Macro Roll Option
~~~~~~~~~~~~~~~~~~~~~

This is the most straight forward way to call a macro. When using the
roll option , you must specify the location of the macro being called
and give a single argument. Note that this argument must always be
specified, even if you do not need it. In such cases, it is common
practice is to use an empty string "".

This argument can be accessed inside the called macro via the special
variable called `macro.args <macro.args>`__.

All of the called macro's output will be inserted into the calling macro
at the point in the code where the roll option is placed. This output
usually goes into the chat output. However, you can choose to instead
assign the returned value to the variable
`macro.return <macro.return>`__.

Once the called macro is processed, the `macro.return <macro.return>`__
variable can be used in the calling macro in a function call.

Example
^^^^^^^

Lets say you have a macro called that can roll any number of dice. In
another macro, you want to call , have it roll three dice and then use
the result of that roll.

Calling macro:

.. code:: mtmacro
   :number-lines:

    [h, macro("attackRoll@Lib:Token"): 3]    
   Attack roll: [r: macro.return] 

Called macro (named and placed on token ):

.. code:: mtmacro
   :number-lines:

    [h: diceNr = macro.args]
   [r: roll(diceNr, 6)]    

Note that you could write the called macro this way, too:

.. code:: mtmacro
   :number-lines:

    [h: diceNr = macro.args]
   [h: macro.return = roll(diceNr, 6)]    

For this simple example, it really makes no difference.

.. _user_defined_function:

User Defined Function
~~~~~~~~~~~~~~~~~~~~~

Often referred to as UDF in the forum, User Defined Functions are
probably the most convenient way to do complex coding. A User Defined
Function can be used just like a regular function. It can have arguments
and it will be replaced by its resulting value when MapTool parses the
calling macro. *User defined* means that you can specify the macro to be
called when you create the function.

Arguments are assigned to the UDF by writing them inside the parentheses
(), separated by comas. The macro's complete chat output will be used as
the resulting value and replace the function call, so you can easily
assign it to a variableor use it as an argument for another function. It
is important to note that HTML comments will be included in this output
as well, even though they will not appear in the chat window. Also note
that only the first macro in an execution chain will dump its output to
chat.

In the called macro, the arguments are inside the
`macro.args <macro.args>`__ variable, formatted as a JSON array. You can
use and for easy access.

To set up a UDF you have to call on every client where the function will
be used. This can be done automatically by placing all the calls inside
the special macro `onCampaignLoad <onCampaignLoad>`__ on a library
token. This is the standard practice. It is executed whenever the
campaign file is loaded by MT (whether from a server or from file).

.. _example_1:

Example
^^^^^^^

Lets rewrite the above example using a UDF.

.. raw:: mediawiki

   {{code|onCampaignLoad}}

on a token :

.. code:: mtmacro
   :number-lines:

   [defineFunction("attackRoll", "attackRoll@Lib:Token")]
    

Calling macro:

.. code:: mtmacro
   :number-lines:

   Attack roll: [r: attackRoll(3)]

Called macro (named and placed on token ):

.. code:: mtmacro
   :number-lines:

   [h: assert(argCount()>0, "attackRoll() expects one argument.")]
   [h: diceNr = arg(0)]
   [r: roll(diceNr, 6)]

.. _create_udfs_automatically:

Create UDFs Automatically
^^^^^^^^^^^^^^^^^^^^^^^^^

You can write a macro that scans your `Lib:token <Library_Token>`__
macros and converts them all into user defined functions. This is a
nice, convenient little trick that's done here (`see forum
post <http://forums.rptools.net/viewtopic.php?f=20&t=19856#p209019m>`__),
in really elaborated way, by aliasmask.

.. _macro_links:

Macro Links
~~~~~~~~~~~

When you want to call macros on user reaction, you can send out
clickable links to chat or place them into frames. Also use them if you
want to work with HTML forms or the fancier form-based events.

Since the macro is not executed immediately, there is a way to use the
macro's result in the calling macro. Arguments, the token in context and
where the output should be sent can all be specified precisely when you
create the macro link.

See also , .

.. _example_2:

Example
^^^^^^^

This time, let us assume we want to send an attack roll to chat and then
ask for a defense roll. We also want to send the Macro Link to everybody
connected (because that is much easier) and don't care about the current
token in context.

Calling macro:

.. code:: mtmacro
   :number-lines:

   [h: atk = roll(3,6)]
   Attack roll: [r: atk]<br>
   [r: macroLink("Do you want to defend?", "defenceRoll@Lib:Token", "all", atk)]

Called macro (named and placed on token ): *Note that this macro will be
executed whenever the link is clicked.*

.. code:: mtmacro
   :number-lines:

   [h: atk = macro.args]
   [h: def = roll(3,6)]

   Defence roll: [r: def] [r, if(atk<def): "You defended successfully!"; "You are hit."]

.. _evaluate_a_macro:

Evaluate a Macro
~~~~~~~~~~~~~~~~

This does not directly call a macro stored somewhere, but rather
evaluates some string you feed into the function as if it were macro
code. This happens in place. It is not easy to retrieve the macro code
from a stored macro, thus this is not a good way to call a macro stored
in the usual way. This is most often used for small code snippets
created dynamically or stored on token properties.

See also , , , . Here, and do exactly the same thing; they are just two
different names with the same functionality.

.. _example_3:

Example
^^^^^^^

Lets say a RPG has a complex weapon damage system with formulas that
follow no rule. The formula for the active would be stored in a token
property called .

.. code:: mtmacro
   :number-lines:

   [h: myFormula = getProperty("damageFormula")]
   You made [r: evalMacro(myFormula)] damage.

Content of the property:

.. code:: mtmacro
   :number-lines:

   [h: "<!-- roll 1d3, weapon makes 3d6 dmg on 1 or 2 , 2d10 on a 3 -->"]
   [h: firstRoll = 1d3]
   [r, if(firstRoll==3): 2d10; 3d6]

*Yeah, such a damage system would be horrible.*

| One notable difference between and is how you pass a parameter:
| For example -- the call ...

.. code:: mtmacro
   :number-lines:

   [r:myFunction()]

... can also be called as follows with the two methods:

.. code:: mtmacro
   :number-lines:

   [r:evalMacro("[r:myFunction()]"]

Which has the same result as:

.. code:: mtmacro
   :number-lines:

   [r:eval("myFunction()"]

Do you see how works with square brackets (roll options) and just the
function text?

.. _variable_context_scope:

Variable Context (Scope)
------------------------

Usually, a new macro creates a new context (scope) for variables, thus
locally defined variables in one macro are not defined in another.

By using , you can call macros that operate in the same *variable
context (scope)* as the calling macro -- when you want so.

The token context is usually transported along with the macro call. With
macro links, you can specify the token context. ]

`Category:Tutorial <Category:Tutorial>`__
