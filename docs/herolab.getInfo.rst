============================
herolab.getInfo - MapToolDoc
============================

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

   .. rubric:: herolab.getInfo
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

            -  `1 herolab.getInfo()
               Function <#herolab.getInfo.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: herolab.getInfo() Function
            :name: herolab.getinfo-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5**

         .. container:: template_description

            Get basic information about the Hero Lab data associated
            with this token. Returns a JSON object containing various
            metadata about the character.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     herolab.getInfo(id)

               #. .. code-block:: none

                     herolab.getInfo(id,field)

         **Parameters**

         -  ``id`` - The token id of the token to name, defaults to the
            Current Token.
         -  ``field`` - A particular field from the metadata.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get the Hero Lab data associated with the current token.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [herolab.getInfo()]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: javascript source-javascript

                  #. .. code-block:: none

                        {

                  #. .. code-block:: none

                           "summary": "Young red dragon - CE Large dragon",

                  #. .. code-block:: none

                            "masterIndex": null,

                  #. .. code-block:: none

                          "isAlly": false,

                  #. .. code:: de2

                          "images": ["asset://8799bd3b26bc614cf0a0f33675f5e77d", "asset://80b3ea5b47f5f1c7aec06a28219cde47"],

                  #. .. code-block:: none

                           "portfolioPath": "C:\\Users\\John\\Documents\\Pathfinder\\Giantslayer\\Episode 5 tokens\\",

                  #. .. code-block:: none

                          "playerName": "Joe",

                  #. .. code-block:: none

                            "isMinion": false,

                  #. .. code-block:: none

                            "portfolioFile": "C:\\Users\\John\\Documents\\Pathfinder\\Giantslayer\\Episode 5 tokens\\Part 3 GS 5.por",

                  #. .. code:: de2

                           "gameSystem": "Pathfinder Roleplaying Game",

                  #. .. code-block:: none

                            "heroLabIndex": "11",

                  #. .. code-block:: none

                           "isDirty": true,

                  #. .. code-block:: none

                          "name": "Young Red Dragon #3",

                  #. .. code-block:: none

                          "lastModified": "Fri Nov 02 16:28:33 CDT 2018",

                  #. .. code:: de2

                         "masterName": ""

                  #. .. code-block:: none

                        }

            Get the status of the ``isMinion`` field from the Hero Lab
            data for the token named *Orc 23*.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: isMinion = herolab.getInfo("Orc 23","isMinion")]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        1

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Hero Lab
            Integration </maptool/index.php?title=Hero_Lab_Integration&action=edit&redlink=1>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5** - Added to main MapTool build.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=herolab.getInfo&oldid=7176"

