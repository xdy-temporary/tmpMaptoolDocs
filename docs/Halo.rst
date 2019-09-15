=======================
token.halo - MapToolDoc
=======================

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

   .. rubric:: token.halo
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

         (Redirected
         from\ `Halo </maptool/index.php?title=Halo&redirect=no>`__\ )

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         The variable *token.halo* allows programmatic querying and
         setting of the token's **Halo**, a colored border that, if set,
         appears around the token. In the image below, the yellow border
         around the token is the token's halo.

         |Token-halo.jpg|

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Examples <#Examples>`__

               -  `1.1 Getting the Token Halo
                  Color <#Getting_the_Token_Halo_Color>`__
               -  `1.2 Setting the Token Halo
                  Color <#Setting_the_Token_Halo_Color>`__
               -  `1.3 Removing the Token
                  Halo <#Removing_the_Token_Halo>`__
               -  `1.4 Color Names and Standard
                  Colors <#Color_Names_and_Standard_Colors>`__

         .. rubric:: Examples
            :name: examples

         .. rubric:: Getting the Token Halo Color
            :name: getting-the-token-halo-color

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     Halo color: [token.halo]

         Outputs the hexadecimal value for the token halo color. In the
         case of the example image above, it would output *#ffff00*.

         .. rubric:: Setting the Token Halo Color
            :name: setting-the-token-halo-color

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:token.halo = "red"]

         or

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:token.halo = #ff0000]

         Sets the color of the token.halo to red (or the hexadecimal
         value *#ff0000*).

         .. rubric:: Removing the Token Halo
            :name: removing-the-token-halo

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:token.halo="None"]

         .. rubric:: Color Names and Standard Colors
            :name: color-names-and-standard-colors

         The *token.halo* variable accepts the following named colors
         (if using a named color, enclose the value in quotes):

         -  Black
         -  Green
         -  Yellow
         -  Orange
         -  Red
         -  Blue
         -  Cyan
         -  DarkGray
         -  Magenta
         -  Pink
         -  White

         The variable will also accept any hexadecimal color value.
         Hexadecimal color values do not need to be enclosed in quotes.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=token.halo&oldid=2315"

