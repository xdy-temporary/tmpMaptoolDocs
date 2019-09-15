====================
getName - MapToolDoc
====================

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

   .. rubric:: getName
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

         .. container:: template_stub

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 getName() Function <#getName.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getName() Function
            :name: getname-function

         .. container:: template_version

            • **Introduced in version 1.3b40**

         .. container:: template_description

            Returns the name of a `Token </rptools/wiki/Token>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getName()

               #. .. code-block:: none

                     getName(id)

               #. .. code-block:: none

                     getName(id, mapname)

         **Parameters**

         -  ``id`` - The token ``id`` of the token to name, defaults to
            the `Current Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [TokenList = getTokens("json")]

                  #. .. code-block:: none

                        [foreach(Token, TokenList, "<br>", "json"): getName(Token) + "'s ID is " + Token]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getName&oldid=7489"

