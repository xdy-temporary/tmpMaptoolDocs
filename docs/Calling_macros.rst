===========================
Calling macros - MapToolDoc
===========================

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

   .. rubric:: Calling macros
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

         .. container:: template_advanced

            ADVANCED
            THIS IS AN ADVANCED ARTICLE

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Calling Macros From another
               Macro <#Calling_Macros_From_another_Macro>`__

               -  `1.1 The Four Methods to Call a
                  Macro <#The_Four_Methods_to_Call_a_Macro>`__

                  -  `1.1.1 The Macro Roll
                     Option <#The_Macro_Roll_Option>`__

                     -  `1.1.1.1 Example <#Example>`__

                  -  `1.1.2 User Defined
                     Function <#User_Defined_Function>`__

                     -  `1.1.2.1 Example <#Example_2>`__
                     -  `1.1.2.2 Create UDFs
                        Automatically <#Create_UDFs_Automatically>`__

                  -  `1.1.3 Macro Links <#Macro_Links>`__

                     -  `1.1.3.1 Example <#Example_3>`__

                  -  `1.1.4 Evaluate a Macro <#Evaluate_a_Macro>`__

                     -  `1.1.4.1 Example <#Example_4>`__

               -  `1.2 Variable Context
                  (Scope) <#Variable_Context_.28Scope.29>`__

         .. rubric:: Calling Macros From another Macro
            :name: calling-macros-from-another-macro

         Sometimes you want to call a macro from another macro. As a
         coder, you want this often, because it enables you to split
         your code in small, simple chunks that can be reused over and
         over again. This handy technique also helps keep the stack size
         requirement low and mitigates the need for large
         code-level-nesting.

         When calling a macro from another macro, you will often want to
         transfer data from one to the other and vice versa. In
         addition, it is also important to know what happens with chat
         output.

         There are four different ways to call a macro - and they all
         behave a little bit differently. While reading this tutorial,
         please be sure to follow the wiki-links provided for any items
         you are not familiar with, as they will not be covered.

         | 

         .. rubric:: The Four Methods to Call a Macro
            :name: the-four-methods-to-call-a-macro

         .. rubric:: The Macro Roll Option
            :name: the-macro-roll-option

         This is the most straight forward way to call a macro. When
         using the roll option
         `[macro():] </rptools/wiki/macro_(roll_option)>`__, you must
         specify the location of the macro being called and give a
         single argument. Note that this argument must always be
         specified, even if you do not need it. In such cases, it is
         common practice is to use an empty string "".

         This argument can be accessed inside the called macro via the
         special variable called
         `macro.args </rptools/wiki/macro.args>`__.

         All of the called macro's output will be inserted into the
         calling macro at the point in the code where the
         `[macro():] </rptools/wiki/macro_(roll_option)>`__ roll option
         is placed. This output usually goes into the chat output.
         However, you can choose to instead assign the returned value to
         the variable `macro.return </rptools/wiki/macro.return>`__.

         Once the called macro is processed, the
         `macro.return </rptools/wiki/macro.return>`__ variable can be
         used in the calling macro in a function call.

         .. rubric:: Example
            :name: example

         Lets say you have a macro called ``attackRoll`` that can roll
         any number of dice. In another macro, you want to call
         ``attackRoll``, have it roll three dice and then use the result
         of that roll.

         Calling macro:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                      [h, macro("attackRoll@Lib:Token"): 3]    

               #. .. code-block:: none

                     Attack roll: [r: macro.return]

         Called macro (named ``attackRoll`` and placed on token
         ``Lib:Token``):

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                      [h: diceNr = macro.args]

               #. .. code-block:: none

                     [r: roll(diceNr, 6)]

         Note that you could write the called macro this way, too:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                      [h: diceNr = macro.args]

               #. .. code-block:: none

                     [h: macro.return = roll(diceNr, 6)]

         For this simple example, it really makes no difference.

         .. rubric:: User Defined Function
            :name: user-defined-function

         Often referred to as UDF in the forum, User Defined Functions
         are probably the most convenient way to do complex coding. A
         User Defined Function can be used just like a regular function.
         It can have arguments and it will be replaced by its resulting
         value when MapTool parses the calling macro. *User defined*
         means that you can specify the macro to be called when you
         create the function.

         Arguments are assigned to the UDF by writing them inside the
         parentheses (), separated by comas. The macro's complete chat
         output will be used as the resulting value and replace the
         function call, so you can easily assign it to a variableor use
         it as an argument for another function. It is important to note
         that HTML comments will be included in this output as well,
         even though they will not appear in the chat window. Also note
         that only the first macro in an execution chain will dump its
         output to chat.

         In the called macro, the arguments are inside the
         `macro.args </rptools/wiki/macro.args>`__ variable, formatted
         as a JSON array. You can use
         `argCount() </rptools/wiki/argCount>`__ and
         `arg() </rptools/wiki/arg>`__ for easy access.

         To set up a UDF you have to call
         `defineFunction() </rptools/wiki/defineFunction>`__ on every
         client where the function will be used. This can be done
         automatically by placing all the
         `defineFunction() </rptools/wiki/defineFunction>`__ calls
         inside the special macro
         `onCampaignLoad </rptools/wiki/onCampaignLoad>`__ on a library
         token. This is the standard practice. It is executed whenever
         the campaign file is loaded by MT (whether from a server or
         from file).

         .. rubric:: Example
            :name: example-1

         Lets rewrite the above example using a UDF.

         ``onCampaignLoad`` on a token ``Lib:Token``:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [defineFunction("attackRoll", "attackRoll@Lib:Token")]

         | 
         | Calling macro:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     Attack roll: [r: attackRoll(3)]

         Called macro (named ``attackRoll`` and placed on token
         ``Lib:Token``):

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: assert(argCount()>0, "attackRoll() expects one argument.")]

               #. .. code-block:: none

                     [h: diceNr = arg(0)]

               #. .. code-block:: none

                     [r: roll(diceNr, 6)]

         .. rubric:: Create UDFs Automatically
            :name: create-udfs-automatically

         You can write a macro that scans your
         `Lib:token </rptools/wiki/Library_Token>`__ macros and converts
         them all into user defined functions. This is a nice,
         convenient little trick that's done here (`see forum
         post <http://forums.rptools.net/viewtopic.php?f=20&t=19856#p209019m>`__),
         in really elaborated way, by aliasmask.

         .. rubric:: Macro Links
            :name: macro-links

         When you want to call macros on user reaction, you can send out
         clickable links to chat or place them into frames. Also use
         them if you want to work with HTML forms or the fancier
         form-based events.

         Since the macro is not executed immediately, there is a way to
         use the macro's result in the calling macro. Arguments, the
         token in context and where the output should be sent can all be
         specified precisely when you create the macro link.

         See also `macroLink() </rptools/wiki/macroLink>`__,
         `macroLinkText() </rptools/wiki/macroLinkText>`__.

         .. rubric:: Example
            :name: example-2

         This time, let us assume we want to send an attack roll to chat
         and then ask for a defense roll. We also want to send the Macro
         Link to everybody connected (because that is much easier) and
         don't care about the current token in context.

         Calling macro:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: atk = roll(3,6)]

               #. .. code-block:: none

                     Attack roll: [r: atk]<br>

               #. .. code-block:: none

                     [r: macroLink("Do you want to defend?", "defenceRoll@Lib:Token", "all", atk)]

         | 
         | Called macro (named ``defenceRoll`` and placed on token
           ``Lib:Token``): *Note that this macro will be executed
           whenever the link is clicked.*

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: atk = macro.args]

               #. .. code-block:: none

                     [h: def = roll(3,6)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     Defence roll: [r: def] [r, if(atk<def): "You defended successfully!"; "You are hit."]

         .. rubric:: Evaluate a Macro
            :name: evaluate-a-macro

         This does not directly call a macro stored somewhere, but
         rather evaluates some string you feed into the function as if
         it were macro code. This happens in place. It is not easy to
         retrieve the macro code from a stored macro, thus this is not a
         good way to call a macro stored in the usual way. This is most
         often used for small code snippets created dynamically or
         stored on token properties.

         See also `evalMacro() </rptools/wiki/evalMacro>`__,
         `execMacro() </rptools/wiki/execMacro>`__,
         `json.evaluate() </rptools/wiki/json.evaluate>`__,
         `eval() </rptools/wiki/eval>`__. Here, ``evalMacro`` and
         ``execMacro`` do exactly the same thing; they are just two
         different names with the same functionality.

         .. rubric:: Example
            :name: example-3

         Lets say a RPG has a complex weapon damage system with formulas
         that follow no rule. The formula for the active would be stored
         in a token property called ``damageFormula``.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: myFormula = getProperty("damageFormula")]

               #. .. code-block:: none

                     You made [r: evalMacro(myFormula)] damage.

         Content of the ``damageFormula`` property:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: "<!-- roll 1d3, weapon makes 3d6 dmg on 1 or 2 , 2d10 on a 3 -->"]

               #. .. code-block:: none

                     [h: firstRoll = 1d3]

               #. .. code-block:: none

                     [r, if(firstRoll==3): 2d10; 3d6]

         *Yeah, such a damage system would be horrible.*

         | One notable difference between ``eval`` and ``evalMacro`` is
           how you pass a parameter:
         | For example -- the call ...

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [r:myFunction()]

         ... can also be called as follows with the two methods:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [r:evalMacro("[r:myFunction()]"]

         Which has the same result as:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [r:eval("myFunction()"]

         | 
         | Do you see how ``evalMacro()`` works with square brackets
           (roll options) and ``eval()`` just the function text?

         .. rubric:: Variable Context (Scope)
            :name: variable-context-scope

         Usually, a new macro creates a new context (scope) for
         variables, thus locally defined variables in one macro are not
         defined in another.

         By using `defineFunction() </rptools/wiki/defineFunction>`__,
         you can call macros that operate in the same *variable context
         (scope)* as the calling macro -- when you want so.

         The token context is usually transported along with the macro
         call. With macro links, you can specify the token context.]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Calling_macros&oldid=6012"

