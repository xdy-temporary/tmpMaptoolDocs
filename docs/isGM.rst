=================
isGM - MapToolDoc
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

   .. rubric:: isGM
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

            -  `1 isGM() Function <#isGM.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: isGM() Function
            :name: isgm-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns ``true``\ (``1``) if the player is a GM or
            ``false``\ (``0``) if they are not.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isGM()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     isGM(player)

         **Parameters**

         -  ``player`` - player's name as a string to check if he is a
            GM or not.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            **1. Test to see if current player is a GM.**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        I am a [r,if(isGM()): "GM"; "Player"]

            | 
            | **2. Display a list of GMs.**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     [H: allPlayers = getAllPlayerNames("json")]
                     [H: GMList = "[]"]
                     [H: foreach(player,allPlayers), code: {
                        [H, if(isGM(player)): GMList = json.append(GMList,player)]
                     }]
                     [R, if(! json.isEmpty(GMList)): "GM List: " + json.toList(GMList); "No players are listed as GM"]

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **b91** - Added ``player`` parameter

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=isGM&oldid=6306"

