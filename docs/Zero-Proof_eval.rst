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

               #. .. code:: de1

                     [ defineFunction( "eval", "evalFunction@this", 1, 0 ) ]

         --------------

         --------------

         **evalFunction**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code:: de1

                     //  Error handling

               #. .. code:: de1

                     [ assert( argCount() >= 1, "<b>eval()</b> - Invalid number of parameters <i>0</i>,

               #. .. code:: de1

                                                 expected at least <i>1</i> parameter.", 0 ) ]

               #. .. code:: de1

                      

               #. .. code:: de2

                     //  Initialise variables

               #. .. code:: de1

                     [ X_Expression_X = arg( argCount()-1 ) ]

               #. .. code:: de1

                     [ X_CancelEval_X = 0 ]

               #. .. code:: de1

                     [ X_TypeTest_X = json.type( X_Expression_X ) ]

               #. .. code:: de1

                      

               #. .. code:: de2

                     //  Handle all numbers

               #. .. code:: de1

                     [ if( isNumber( X_Expression_X ) == 1 ), code:

               #. .. code:: de1

                     {

               #. .. code:: de1

                        [ X_CancelEval_X = 1 ]

               #. .. code:: de1

                     } ]

               #. .. code:: de2

                      

               #. .. code:: de1

                     //  Handle empty strings

               #. .. code:: de1

                     [ if( X_TypeTest_X == "UNKNOWN" ), code:

               #. .. code:: de1

                     {

               #. .. code:: de1

                         [ if( X_Expression_X == "" ), code:

               #. .. code:: de2

                         {

               #. .. code:: de1

                             [ X_CancelEval_X = 1 ]

               #. .. code:: de1

                         } ]

               #. .. code:: de1

                     } ]

               #. .. code:: de1

                      

               #. .. code:: de2

                     //  Handle JSON types

               #. .. code:: de1

                     [ if( X_TypeTest_X == "ARRAY" || X_TypeTest_X == "OBJECT" ), code:

               #. .. code:: de1

                     {

               #. .. code:: de1

                         [ X_CancelEval_X = 1 ]

               #. .. code:: de1

                     } ]

               #. .. code:: de2

                      

               #. .. code:: de1

                     //  Evaluate or cancel, then return

               #. .. code:: de1

                     [ if( X_CancelEval_X == 1 ), code:

               #. .. code:: de1

                     {

               #. .. code:: de1

                         [ macro.return = X_Expression_X ]

               #. .. code:: de2

                     };{

               #. .. code:: de1

                         [ macro.return = oldFunction( X_Expression_X ) ]

               #. .. code:: de1

                     } ]

         --------------

         | 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Custom_Robust_eval_Function&oldid=3518"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `Cookbook </rptools/wiki/Category:Cookbook>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ >
         `Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: visualClear

.. container::
   :name: mw-navigation

   .. rubric:: Navigation menu
      :name: navigation-menu

   .. container::
      :name: mw-head

      .. container::
         :name: p-personal

         .. rubric:: Personal tools
            :name: p-personal-label

         -  `Log
            in </maptool/index.php?title=Special:UserLogin&returnto=Custom+Robust+eval+Function>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Custom_Robust_eval_Function>`__
            -  `Discussion </maptool/index.php?title=Talk:Custom_Robust_eval_Function&action=edit&redlink=1>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-variants

            .. rubric:: Variants\ ` <#>`__
               :name: p-variants-label

            .. container:: menu

      .. container::
         :name: right-navigation

         .. container:: vectorTabs
            :name: p-views

            .. rubric:: Views
               :name: p-views-label

            -  `Read </rptools/wiki/Custom_Robust_eval_Function>`__
            -  `View
               source </maptool/index.php?title=Custom_Robust_eval_Function&action=edit>`__
            -  `View
               history </maptool/index.php?title=Custom_Robust_eval_Function&action=history>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-cactions

            .. rubric:: More\ ` <#>`__
               :name: p-cactions-label

            .. container:: menu

         .. container::
            :name: p-search

            .. rubric:: Search
               :name: search

            .. container::
               :name: simpleSearch

   .. container::
      :name: mw-panel

      .. container::
         :name: p-logo

         ` </rptools/wiki/Main_Page>`__

      .. container:: portal
         :name: p-navigation

         .. rubric:: Navigation
            :name: p-navigation-label

         .. container:: body

            -  `Main page </rptools/wiki/Main_Page>`__
            -  `Random page </rptools/wiki/Special:Random>`__
            -  `Help <https://www.mediawiki.org/wiki/Special:MyLanguage/Help:Contents>`__

      .. container:: portal
         :name: p-Basic_Usage

         .. rubric:: Basic Usage
            :name: p-Basic_Usage-label

         .. container:: body

            -  `Tutorials </rptools/wiki/Category:Tutorial>`__
            -  `Chat Commands </rptools/wiki/Chat_Commands>`__
            -  `Dice Expressions </rptools/wiki/Dice_Expressions>`__
            -  `Glossary </rptools/wiki/Glossary>`__

      .. container:: portal
         :name: p-Macro_Reference

         .. rubric:: Macro Reference
            :name: p-Macro_Reference-label

         .. container:: body

            -  `List of
               Functions </rptools/wiki/Category:Macro_Function>`__
            -  `Roll Options </rptools/wiki/Category:Roll_Option>`__
            -  `Special
               Variables </rptools/wiki/Category:Special_Variable>`__
            -  `Macro Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: portal
         :name: p-Editors

         .. rubric:: Editors
            :name: p-Editors-label

         .. container:: body

            -  `Editor Discussion </rptools/wiki/Editor>`__
            -  `Recent Changes </rptools/wiki/Special:RecentChanges>`__

      .. container:: portal
         :name: p-tb

         .. rubric:: Tools
            :name: p-tb-label

         .. container:: body

            -  `What links
               here </rptools/wiki/Special:WhatLinksHere/Custom_Robust_eval_Function>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Custom_Robust_eval_Function>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Custom_Robust_eval_Function&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Custom_Robust_eval_Function&oldid=3518>`__
            -  `Page
               information </maptool/index.php?title=Custom_Robust_eval_Function&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 17 June 2009, at 21:24.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
