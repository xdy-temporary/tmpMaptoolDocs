==============================
getInitiativeList - MapToolDoc
==============================

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

   .. rubric:: getInitiativeList
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

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *more examples.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 getInitiativeList()
               Function <#getInitiativeList.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getInitiativeList() Function
            :name: getinitiativelist-function

         .. container:: template_version

            • **Introduced in version 1.3b57**

         .. container:: template_description

            Retrieves a list of all tokens currently in the Initiative
            Panel. The return value is a JSON object with various
            information about initiative, including global information
            (round number, which map is current, which token is current)
            and token-specific information (token id, initiative value,
            whether the token is holding or not). When called from a
            `Trusted Macro </rptools/wiki/Trusted_Macro>`__ or by a
            client with GM authority, it will return all information.
            Otherwise it only returns information visible to the current
            player. In other words, it respects the Initiative Panel's
            ``Hide NPCs`` and the token's ``Visible To Owner Only``
            flags, among others. (This is new in **1.3b78**. Prior
            versions didn't have the check for trusted context at all.)

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ json = getInitiativeList() ]

         **Parameters** None.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            The following code will simply return a JSON object and
            print each property name one at a time on separate lines.
            Refer to `JSON Object </rptools/wiki/JSON_Object>`__ for
            more information about JSON object themselves and
            `json.get </rptools/wiki/json.get>`__ for information on
            retrieving properties and their values.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: json = getInitiativeList() ]

                  #. .. code-block:: none

                        [ foreach(item, json, "<br>"): item ]

            This example prints a nicely formatted output showing what
            the contents of the JSON object look like.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: json = getInitiativeList() ]

                  #. .. code-block:: none

                        <pre>[r: json.indent(json) ]</pre>

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b57** - Added macro function.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getInitiativeList&oldid=5126"

