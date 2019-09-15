===========================
getTokenStates - MapToolDoc
===========================

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

   .. rubric:: getTokenStates
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

            -  `1 getTokenStates()
               Function <#getTokenStates.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getTokenStates() Function
            :name: gettokenstates-function

         .. container:: template_version

            • **Introduced in version 1.3b51**

         .. container:: template_description

            Returns the valid states in the campaign settings in either
            a `String List </rptools/wiki/String_List>`__ or `JSON
            Array </rptools/wiki/JSON_Array>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenStates()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenStates(delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getTokenStates(delim, groupName)

         **Parameter**

         -  ``delim`` - Specifies the delimiter used in the string list
            that is returned, defaultis ``","``. If the value is set to
            ``json``, the function returns a JSON array instead.
         -  ``groupName`` - Specifies the name of the group to get the
            states for. **Note that if you wish to use the ``groupname``
            parameter, you MUST set a delimiter.**

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To get a `String List </rptools/wiki/String_List>`__ of the
            valid `Token States </rptools/wiki/Token_State>`__ in the
            campaign.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: states = getTokenStates()]

            To get a `JSON Array </rptools/wiki/JSON_Array>`__ of the
            valid `Token States </rptools/wiki/Token_State>`__ in the
            campaign.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: states = getTokenStates("json")]

            To get a `JSON Array </rptools/wiki/JSON_Array>`__ of the
            valid `Token States </rptools/wiki/Token_State>`__ in the
            *Damage* group in the campaign in 1.3b55 or later.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: states = getTokenStates("json", "Damage")]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b55** - Added the ``groupName`` parameter.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getTokenStates&oldid=3325"

