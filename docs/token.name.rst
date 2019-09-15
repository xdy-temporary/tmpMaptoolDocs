=======================
token.name - MapToolDoc
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

   .. rubric:: token.name
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

         The variable *token.name* allows programmatic querying and
         setting of the token's
         `Name </maptool/index.php?title=Token:Token_name&action=edit&redlink=1>`__
         (the first text field in the screenshot of the Edit Token
         dialog).

         |Edittoken-name-and-label.jpg|

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Examples <#Examples>`__

               -  `1.1 Getting the Token
                  Name <#Getting_the_Token_Name>`__
               -  `1.2 Setting the Token
                  Name <#Setting_the_Token_Name>`__

            -  `2 Related Pages <#Related_Pages>`__

         .. rubric:: Examples
            :name: examples

         .. rubric:: Getting the Token Name
            :name: getting-the-token-name

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:charName=token.name]

               #. .. code-block:: none

                     Token Name: [charName]

         Outputs the value of *token.name*.

         .. rubric:: Setting the Token Name
            :name: setting-the-token-name

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:token.name = "Marok the Red"]

         Sets the value of *token.name* to "Marok the Red."

         .. rubric:: Related Pages
            :name: related-pages

         -  `token.gm_name </rptools/wiki/token.gm_name>`__
         -  `token.label </rptools/wiki/token.label>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=token.name&oldid=2311"

