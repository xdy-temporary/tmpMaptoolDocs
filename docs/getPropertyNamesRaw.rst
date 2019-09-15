================================
getPropertyNamesRaw - MapToolDoc
================================

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

   .. rubric:: getPropertyNamesRaw
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

            -  `1 getPropertyNamesRaw()
               Function <#getPropertyNamesRaw.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__
               -  `1.4 Notes <#Notes>`__

         .. rubric:: getPropertyNamesRaw() Function
            :name: getpropertynamesraw-function

         .. container:: template_version

            • **Introduced in version 1.3b64**

         .. container:: template_description

            Returns a `String List </rptools/wiki/String_List>`__ or
            `JSON Array </rptools/wiki/JSON_Array>`__ containing the
            names of the `Token
            Properties </rptools/wiki/Token_Property>`__ on a
            `Token </rptools/wiki/Token>`__. The type of the value
            returned depends on the delimiter parameter. The difference
            between this function and
            `getPropertyNames() </rptools/wiki/getPropertyNames>`__ is
            that `getPropertyNames() </rptools/wiki/getPropertyNames>`__
            returns all the property names in lower case (see `this
            forum
            thread <http://forums.rptools.net/viewtopic.php?f=1&t=12563&p=148937&hilit=getPropertyNamesRaw#p148937>`__
            to get the reason why it was created).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getPropertyNamesRaw()

               #. .. code-block:: none

                     getPropertyNamesRaw(delim)

               #. .. code-block:: none

                     getPropertyNamesRaw(delim, id)

               #. .. code-block:: none

                     getPropertyNamesRaw(delim, id, mapname)

         **Parameters**

         -  ``delim`` - The delimiter used to separate the values in the
            `String List </rptools/wiki/String_List>`__, defaults to
            ``","``. Returns a `JSON Array </rptools/wiki/JSON_Array>`__
            if set to ``"json"``.
         -  ``id`` - The token ``id`` of the token which has its
            property names returned, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To display the names of all of the
            `properties </rptools/wiki/Token_Property>`__ on the current
            `token </rptools/wiki/Token:token>`__ use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names = getPropertyNamesRaw()]

                  #. .. code-block:: none

                        [foreach(name, names, "<br>"): name]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added ``mapname`` parameter option.

         .. rubric:: Notes
            :name: notes

         When token properties are created during campaign, they are
         persistent in the MapTool campaign, regardless of whether they
         are editable in the *Edit Token* window. In other words, even
         though a property is removed from the campaign properties, it
         remains available in the MapTool code.
         **getPropertyNamesRaw()** will return *all* token properties
         that exist or have ever existed in the particular campaign,
         even if users cannot directly edit those properties (*i.e.*,
         they do not appear in the token's properties when you double
         click on a token). To get only properties that are currently
         visible and editable, use
         `getAllPropertyNames() </rptools/wiki/getAllPropertyNames>`__.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getPropertyNamesRaw&oldid=7492"

