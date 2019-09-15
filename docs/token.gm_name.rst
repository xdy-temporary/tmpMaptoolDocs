==========================
token.gm_name - MapToolDoc
==========================

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

   .. rubric:: token.gm_name
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

         The variable *token.gm_name* allows programmatic querying and
         setting of the token's `GM
         Name </maptool/index.php?title=Token:GM_Name&action=edit&redlink=1>`__
         (the second text field in the screenshot of the Edit Token
         dialog).

         *token.gm_name* is only a valid expression in a trusted macro.

         |Edittoken-name-and-label.jpg|

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Examples <#Examples>`__

               -  `1.1 Getting the Token GM
                  Name <#Getting_the_Token_GM_Name>`__
               -  `1.2 Setting the Token GM
                  Name <#Setting_the_Token_GM_Name>`__

            -  `2 Related Pages <#Related_Pages>`__

         .. rubric:: Examples
            :name: examples

         .. rubric:: Getting the Token GM Name
            :name: getting-the-token-gm-name

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:secretName=token.gm_name]

               #. .. code-block:: none

                     GM's Name: [secretName]

         Outputs the value of *token.gm_name*.

         .. rubric:: Setting the Token GM Name
            :name: setting-the-token-gm-name

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:token.gm_name = "Soldier"]

         Sets the value of *token.gm_name* to "Soldier."

         .. rubric:: Related Pages
            :name: related-pages

         -  `token.name <token.name>`__
         -  `token.label <token.label>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=token.gm_name&oldid=4188"

