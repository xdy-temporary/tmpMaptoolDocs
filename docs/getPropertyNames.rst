=============================
getPropertyNames - MapToolDoc
=============================

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

   .. rubric:: getPropertyNames
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

            -  `1 getPropertyNames()
               Function <#getPropertyNames.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getPropertyNames() Function
            :name: getpropertynames-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a `String List <String_List>`__ or
            `JSON Array <JSON_Array>`__ containing the
            names of the `Token
            Properties <Token_Property>`__ for the
            `Current Token <Current_Token>`__. The type of
            the value returned depends on the delimiter parameter. All
            names returned will be in lower case. Use
            `getPropertyNamesRaw() <getPropertyNamesRaw>`__
            to get the names as they are shown in `Campaign
            Properties <Introduction_to_Properties>`__.
            | 

            .. container:: template_note

               When a token is added to a campaign it inherits the
               currently defined properties of the current campaign.
               These properties are persistent in the token even if the
               properties are subsequently removed from the campaign.
               Properties that have been removed from the campaign are
               no longer editable via the Edit Token dialog but they are
               still present on the token and may be read and set with
               `getProperty() <getProperty>`__ and
               `setProperty() <setProperty>`__
               respectively. To get *all* properties defined on a token,
               including those removed from the campaign, use
               *getPropertyNames()*. To see only the currently defined
               properties for the campaign, use
               `getAllPropertyNames() <getAllPropertyNames>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getPropertyNames()

               #. .. code-block:: none

                     getPropertyNames(delim)

               #. .. code-block:: none

                     getPropertyNames(delim, id)

               #. .. code-block:: none

                     getPropertyNames(delim, id, mapname)

         **Parameters**

         -  ``delim`` - The delimiter used to separate the values in the
            `String List <String_List>`__, defaults to
            ``","``. Returns a `JSON Array <JSON_Array>`__
            if set to ``"json"``.
         -  ``id`` - The token ``id`` of the token which has its
            property names returned, defaults to the `Current
            Token <Current_Token>`__.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro <Trusted_Macro>`__. 

         -  ``mapname`` - The name of the map to find the token.
            Defaults to the current map.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            To display the names of all of the
            `properties </maptool/index.php?title=Token:property&action=edit&redlink=1>`__
            on the current `token <Token:token>`__ use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names = getPropertyNames()]

                  #. .. code-block:: none

                        [foreach(name, names, "<br>"): name]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.
            -  **1.3b51** - Added ``id`` parameter option.
            -  **1.5.4** - Added ``mapname`` parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getPropertyNames&oldid=7491"

