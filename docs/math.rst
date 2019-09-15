=================
math - MapToolDoc
=================

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

   .. rubric:: math
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

            -  `1 math() Function <#math.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__

                  -  `1.2.1 mod <#mod>`__
                  -  `1.2.2 pow <#pow>`__

         .. rubric:: math() Function
            :name: math-function

         .. container:: template_version

            • **Introduced in version 1.4.0.5**

         .. container:: template_description

            This is NOT a single MapTool function but a collection of
            math functions in MapTool. **Important Note**: All of these
            functions return a floating-point number (e.g.: \`3.0`).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     Numbers:

               #. .. code-block:: none

                     [r:val = math.pi()]

               #. .. code-block:: none

                     [r:val = math.e()]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     Trigonomotry:

               #. .. code-block:: none

                     [r:val = math.acos(degrees)]

               #. .. code-block:: none

                     [r:val = math.acos_r(radians)]

               #. .. code-block:: none

                     [r:val = math.asin(degrees)]

               #. .. code-block:: none

                     [r:val = math.asin_r(radians)]

               #. .. code:: de2

                     [r:val = math.atan(degrees)]

               #. .. code-block:: none

                     [r:val = math.atan_r(radians)]

               #. .. code-block:: none

                     [r:val = math.atan2(degrees)]

               #. .. code-block:: none

                     [r:val = math.atan2_r(radians)]

               #. .. code-block:: none

                     [r:val = math.cos(degrees)]

               #. .. code:: de2

                     [r:val = math.cos_r(num)]

               #. .. code-block:: none

                     [r:val = math.sin(degrees)]

               #. .. code-block:: none

                     [r:val = math.sin_r(num)]

               #. .. code-block:: none

                     [r:val = math.tan(degrees)]

               #. .. code-block:: none

                     [r:val = math.tan_r(num)]

               #. .. code:: de2

                     [r:val = math.toDegrees(num)]

               #. .. code-block:: none

                     [r:val = math.toRadians(degrees)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     Power and root:

               #. .. code-block:: none

                     [r:val = math.sqrt(num)]

               #. .. code:: de2

                     [r:val = math.squareroot(num)]

               #. .. code-block:: none

                     [r:val = math.cbrt(num)]

               #. .. code-block:: none

                     [r:val = math.cuberoot(num)]

               #. .. code-block:: none

                     [r:val = math.pow(num1,num2)]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     Logarithmic

               #. .. code-block:: none

                     [r:val = math.log(num)] (this is loge())

               #. .. code-block:: none

                     [r:val = math.log10(num)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     Pythagorean:

               #. .. code:: de2

                     [r:val = math.hypot(num1,num2)]

               #. .. code-block:: none

                     [r:val = math.hypotenuse(num1,num2)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     Simple operations

               #. .. code-block:: none

                     [r:val = math.abs(num)]

               #. .. code:: de2

                     [r:val = math.ceil(num)]

               #. .. code-block:: none

                     [r:val = math.floor(num)]

               #. .. code-block:: none

                     [r:val = math.isEven(num)]

               #. .. code-block:: none

                     [r:val = math.isInt(num)]

               #. .. code-block:: none

                     [r:val = math.isOdd(num)]

               #. .. code:: de2

                     [r:val = math.max(num1, num2, num2, etc.)]

               #. .. code-block:: none

                     [r:val = math.min(num1, num2, num2, etc.)]

               #. .. code-block:: none

                     [r:val = math.mod(num1,num2)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            ====abs====

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:val =  math.abs(-3)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  2. .. code:: de1

                        3.0

            .. rubric:: mod
               :name: mod

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:val =  math.mod(6,3)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  2. .. code:: de1

                        0

            .. rubric:: pow
               :name: pow

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:val =  math.pow(2,3)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  2. .. code:: de1

                        8.0

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=math&oldid=7132"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro
               Function </rptools/wiki/Category:Macro_Function>`__
            -  `Mathematical
               Function </rptools/wiki/Category:Mathematical_Function>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ > `Macro
         Function </rptools/wiki/Category:Macro_Function>`__ >
         `Mathematical
         Function </rptools/wiki/Category:Mathematical_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=math>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/math>`__
            -  `Discussion </maptool/index.php?title=Talk:math&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/math>`__
            -  `View
               source </maptool/index.php?title=math&action=edit>`__
            -  `View
               history </maptool/index.php?title=math&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/math>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/math>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=math&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=math&oldid=7132>`__
            -  `Page
               information </maptool/index.php?title=math&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 1 March 2019, at 03:58.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
