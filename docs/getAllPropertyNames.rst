================================
getAllPropertyNames - MapToolDoc
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

   .. rubric:: getAllPropertyNames
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

            -  `1 getAllPropertyNames()
               Function <#getAllPropertyNames.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getAllPropertyNames() Function
            :name: getallpropertynames-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Gets a list containing the `token
            property <Token:token_property>`__ names that
            are defined in the `campaign
            properties </maptool/index.php?title=Campaign:campaign_properties&action=edit&redlink=1>`__.
            The type of the value returned depends on the delimiter
            parameter.

            -  If the delimiter is not specified then a `string
               list <Macros:string_list>`__ is returned
               and the default value of ``","`` is used.
            -  If the delimiter is ``"json"`` then a `JSON
               Array <JSON_Array>`__ is returned.
            -  Otherwise, a `string
               list <Macros:string_list>`__ is returned
               with the delimiter passed in.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getAllPropertyNames()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getAllPropertyNames(type)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getAllPropertyNames(type, delim)

         If type is specified then the `string
         list <Macros:string_list>`__ contains the
         `property <Token:token_property>`__ names for
         that `token property
         type <Token:token_property_type>`__, otherwise it
         will contain the `token
         property <Token:token_property>`__ names for all
         `token property
         types <Token:token_property_type>`__. If delim is
         specified then it is used to separate the values in the `string
         list <Macros:string_list>`__, if it is not
         specified then it defaults to ','.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            You can use the following code to print out all of the
            properties in the `campaign
            properties </maptool/index.php?title=Campaign:campaign_properties&action=edit&redlink=1>`__
            list..

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Campaign Properties<br>

                  #. .. code-block:: none

                        [h: props = getAllPropertyNames()]

                  #. .. code-block:: none

                        [foreach(name, props, "<br>"): name]

            If you have two token property sets, for instance "PC" and
            "NPC", you could print out all of the properties for the
            "PC" property set like so:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        PC Properties<br>

                  #. .. code-block:: none

                        [h: props=getAllPropertyNames("PC")]

                  #. .. code-block:: none

                        [foreach(name, props, "<br>"): name]

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getAllPropertyNames&oldid=7141"

