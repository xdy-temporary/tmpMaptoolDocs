===============
if - MapToolDoc
===============

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

   .. rubric:: if
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

            -  `1 if() Function <#if.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: if() Function
            :name: if-function

         .. container:: template_version

            • **Introduced in version 1.3b38**

         .. container:: template_description

            Is used to check whether a certain code *expression* should
            be executed or not. If the *condition* to be evaluated with
            this function is ``true``\ (``1``), the first *expression*
            of code is the result, otherwise the second *expression* of
            code is the result.
            | 

            .. container:: template_note

               Note that both *expressions*, the true and the false, are
               evaluated!
               | This means that updates, macro calling, etc. in
                 **both** *expressions* will be executed regardless of
                 the test result.

               Therefore, this function should only be used in limited
               cases where the *expressions* are simply returning a
               value.

            | 
            | This function doesn't have the parentheses limit that the
              roll option has:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [if(((1))): 1;0]     <!-- in this case if() roll option fails -->
                     [if(((1)),1,0)]      <!-- in this case if() function    works -->

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     if(condition, trueExpr, falseExpr)

         **Parameters**

         -  ``condition`` - What is tested to determine is the
            ``trueExpr`` or ``falseExpr`` will be executed. This follows
            the standard rules for *conditions* that can be found in the
            `Branching and
            Looping <Macros:Branching_and_Looping>`__
            article.
         -  ``trueExpr`` - A section of code that is returned if
            ``condition`` is ``true``\ (``1``).
         -  ``falseExpr`` - A section of code that is returned if
            ``condition`` is ``false``\ (``0``).

          

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **Example 1:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: a = 10] [h: b = 20]

                  #. .. code-block:: none

                        [r: if(a > b, "A is larger than B", "A is not larger than B")]

            **Returns:** ``A is not larger than B``
            | 
            | **Example 2:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: number = 1]

                  #. .. code-block:: none

                        [r: if(number >= 1, 20, "")]

            **Returns:** A *blank string*, please note that a *blank
            string* is not an *empty variable* if you were to assign the
            *output* of this function.
            | 
            | **Example 3:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: variable = "Foobar"]

                  #. .. code-block:: none

                        [r: if(variable == "Text", 1, 0)]

            **Returns:** ``0``
            | 
            | **Example 4:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: variable = 20]

                  #. .. code-block:: none

                        [property = if(variable > 0 && variable < 20, 1, 0)]

            **Returns:** ``property`` set to ``0``
            | 
            | **Example 5:** Usually its better to use the roll option
              version `[if():] <if_(roll_option)>`__.
              Sometimes it's pretty handy to use the version documented
              here, since you can easily embed it in loops and
              expressions.

            Let's say you want to check if one of a player's tokens has
            Initiative, you could do it this like this:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: tokensOfPlayer = getOwned(getPlayerName(), "json")]

                  #. .. code-block:: none

                        [h: hasIni = 0]

                  #. .. code-block:: none

                        [h: iniToken = getInitiativeToken()]

                  #. .. code-block:: none

                        [h, foreach(id, tokensOfPlayer): hasIni = if(id!=iniToken,hasIni,1)]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Branching and
            Looping <Macros:Branching_and_Looping>`__, `if
            (roll option) <if_(roll_option)>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=if&oldid=7215"

