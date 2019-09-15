========================================
Custom Robust eval Function - MapToolDoc
========================================

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

   .. rubric:: Custom Robust eval Function
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

         (Redirected from\ `Zero-Proof
         eval </maptool/index.php?title=Zero-Proof_eval&redirect=no>`__\ )

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         This user defined function redefines the standard
         `eval() </rptools/wiki/eval>`__ function, allowing it to be
         given a number, empty string, or JSON object/array and not
         throw an exception.

         .. rubric:: Macros
            :name: macros

         Place both of these macros on the same library token.

         **1.3b56+**

         --------------

         **onCampaignLoad**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ defineFunction( "eval", "evalFunction@this", 1, 0 ) ]

         --------------

         --------------

         **evalFunction**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     //  Error handling

               #. .. code-block:: none

                     [ assert( argCount() >= 1, "<b>eval()</b> - Invalid number of parameters <i>0</i>,

               #. .. code-block:: none

                                                 expected at least <i>1</i> parameter.", 0 ) ]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     //  Initialise variables

               #. .. code-block:: none

                     [ X_Expression_X = arg( argCount()-1 ) ]

               #. .. code-block:: none

                     [ X_CancelEval_X = 0 ]

               #. .. code-block:: none

                     [ X_TypeTest_X = json.type( X_Expression_X ) ]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     //  Handle all numbers

               #. .. code-block:: none

                     [ if( isNumber( X_Expression_X ) == 1 ), code:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                        [ X_CancelEval_X = 1 ]

               #. .. code-block:: none

                     } ]

               #. .. code:: de2

                      

               #. .. code-block:: none

                     //  Handle empty strings

               #. .. code-block:: none

                     [ if( X_TypeTest_X == "UNKNOWN" ), code:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                         [ if( X_Expression_X == "" ), code:

               #. .. code:: de2

                         {

               #. .. code-block:: none

                             [ X_CancelEval_X = 1 ]

               #. .. code-block:: none

                         } ]

               #. .. code-block:: none

                     } ]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     //  Handle JSON types

               #. .. code-block:: none

                     [ if( X_TypeTest_X == "ARRAY" || X_TypeTest_X == "OBJECT" ), code:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                         [ X_CancelEval_X = 1 ]

               #. .. code-block:: none

                     } ]

               #. .. code:: de2

                      

               #. .. code-block:: none

                     //  Evaluate or cancel, then return

               #. .. code-block:: none

                     [ if( X_CancelEval_X == 1 ), code:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                         [ macro.return = X_Expression_X ]

               #. .. code:: de2

                     };{

               #. .. code-block:: none

                         [ macro.return = oldFunction( X_Expression_X ) ]

               #. .. code-block:: none

                     } ]

         --------------

         | 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Custom_Robust_eval_Function&oldid=3518"

