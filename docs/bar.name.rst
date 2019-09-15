===================
foobar - MapToolDoc
===================

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

   .. rubric:: foobar
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

         The *bar.[bar_name]* variable permits the getting and setting
         of the `token
         bar </maptool/index.php?title=Token:bar&action=edit&redlink=1>`__
         value (and the corresponding image displayed on the token)
         programmatically. Token bars are one, two, or multi-image
         graphical elements displayed on a token that are used
         (typically) to visually indicate the status of consumable or
         expendable items or character traits (such as Hit Points,
         Ammunition, Health, or the like).

         Bars, like `token states </rptools/wiki/Token:state>`__, are
         configured via the Campaign Properties dialog and are specific
         to the campaign in which they exist. In the screenshot shown
         below, the green-on-black line across the top of the token is a
         token bar.

         |Bar-example.jpg|

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Usage <#Usage>`__
            -  `2 Examples <#Examples>`__
            -  `3 Notes <#Notes>`__
            -  `4 Related Pages <#Related_Pages>`__

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [bar.[bar_name] = value]

         Sets the value of the token bar named *bar_name* to the desired
         value. *bar_name* is set when the bar is created, and may be
         any name, provided it contains no spaces or special characters
         except the underscore. *Value* must be a number between 0 and
         1.

         .. rubric:: Examples
            :name: examples

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: HP = HP - DamageTaken]

               #. .. code-block:: none

                     [h: bar.Health = HP / MaxHP]

         Sets the value of *bar.Health* to the result of *HP / MaxHP*.

         .. rubric:: Notes
            :name: notes

         Two functions,
         `setBar() </rptools/wiki/Macros:Functions:setBar>`__ and
         `getBar() </rptools/wiki/Macros:Functions:getBar>`__ also exist
         to get and set the value of the token bar.

         .. rubric:: Related Pages
            :name: related-pages

         -  `List of Special
            Variables </rptools/wiki/Macros:Variables:list_of_special_variables>`__
         -  `Token Bar
            Functions </rptools/wiki/Macros:Functions:list_of_functions_by_area#Token_Bars>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=bar.name&oldid=2385"

