=========================
macro.return - MapToolDoc
=========================

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

   .. rubric:: macro.return
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

         The variable *macro.return* holds the value returned from a
         called macro to the calling macro. Other than *macro.return*, a
         called variable shares no other variables with the calling
         macro.

         .. rubric:: Examples
            :name: examples

         When a macro on a `library
         token <Token:library_token>`__ is called by
         another macro, the called macro may return a value to the
         called macro by assigning that value to the variable
         *macro.args*.

         .. rubric:: Calling Macro
            :name: calling-macro

         The macro below calls a macro called **getDamage** on the
         `library token <Token:library_token>`__
         "Lib:combat", passing the variable *damageDice* as an argument.
         It also sets

         +-----------------------------------+-----------------------------------+
         | Calling Macro                     | Called Macro                      |
         +===================================+===================================+
         | .. container::                    | .. container::                    |
         | mw-geshi mw-code mw-content-ltr   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |    .. container::                 |    .. container::                 |
         |    mtmacro source-mtmacro         |    mtmacro source-mtmacro         |
         |                                   |                                   |
         |       #. .. code-block:: none            |       #. .. code-block:: none            |
         |                                   |                                   |
         |             [h:damageDice="2d6"]  |             <!-- getDamage Macro  |
         |                                   | -->                               |
         |       #. .. code-block:: none            |                                   |
         |                                   |       #. .. code-block:: none            |
         |             [MACRO("getDamage@Lib |                                   |
         | :combat"):damageDice]             |             [h:returnData = ""]   |
         |                                   |                                   |
         |       #. .. code-block:: none            |       #. .. code-block:: none            |
         |                                   |                                   |
         |             [h:damageProperties=m |             [h:damageRoll = eval( |
         | acro.return]                      | macro.args) + 9]                  |
         |                                   |                                   |
         |       #. .. code-block:: none            |       #. .. code-block:: none            |
         |                                   |                                   |
         |             [h:varsFromStrProp(da |             [h:damageType = "pier |
         | mageProperties)]                  | cing"]                            |
         |                                   |                                   |
         |                                   |       #. .. code:: de2            |
         |                                   |                                   |
         |                                   |             You hit your target f |
         |                                   | or [r:damageRoll] damage!         |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |             [h:returnData=setStrP |
         |                                   | rop(returnData,"damType", damageT |
         |                                   | ype)]                             |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |             [h:returnData=setStrP |
         |                                   | rop(returnData,"damage", damageRo |
         |                                   | ll)]                              |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |             [h:macro.return=retur |
         |                                   | nData]                            |
         +-----------------------------------+-----------------------------------+

         In the example above, we assume that the **getDamage** macro
         was called by another macro (for example, a token macro) and
         has received some value in the form of *macro.args*. The
         statements in **getDamage** are executed, and the final
         statement assigns the value of returnData to the variable
         *macro.return*.

         When execution of the **getDamage** macro is complete and
         control is handed back to the calling macro, *macro.return* is
         also passed back to the calling macro, where it can be
         manipulated like any other variable.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=macro.return&oldid=2286"

