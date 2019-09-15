================================
getLibPropertyNames - MapToolDoc
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

   .. rubric:: getLibPropertyNames
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

         .. rubric:: getLibPropertyNames() Function
            :name: getlibpropertynames-function

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Returns a `String List </rptools/wiki/String_List>`__ or
            `JSON Array </rptools/wiki/JSON_Array>`__ containing the
            names of the `Token
            Properties </rptools/wiki/Token_Property>`__ on a `Library
            Token </rptools/wiki/Library_Token>`__. The type of the
            value returned depends on the delimiter parameter.
            | 

            .. container:: template_note

               When token properties are created during campaign, they
               are persistent in the MapTool campaign, regardless of
               whether they are editable in the Edit Token window. In
               other words, even though a property is removed from the
               campaign properties, it remains available to macros.
               **getLibPropertyNames** will return *all* token
               properties that exist or have ever existed in the
               particular campaign, even if users cannot directly edit
               those properties (*i.e.*, they do not appear in the
               token's properties when you double click on a token). To
               get only properties that are currently visible and
               editable, use
               `getAllPropertyNames() </rptools/wiki/getAllPropertyNames>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getLibPropertyNames()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getLibPropertyNames(delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getLibPropertyNames(id, delim)

         **Parameters**

         -  ``delim`` - The delimiter used to separate the values in the
            `String List </rptools/wiki/String_List>`__, defaults to
            ``","``. Returns a `JSON Array </rptools/wiki/JSON_Array>`__
            if set to ``"json"``.
         -  ``id`` - The token ``id`` of the token which has its
            property names returned, defaults to the `Current
            Token </rptools/wiki/Current_Token>`__. This parameter may
            be ``*`` or ``this`` to indicate the current Lib token that
            this macro is executing on.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names = getLibPropertyNames()]

                  #. .. code-block:: none

                        [foreach(name, names, "<br>"): name]

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names = getLibPropertyNames("Lib:some_lib_token")]

                  #. .. code-block:: none

                        [foreach(name, names, "<br>"): name]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getLibPropertyNames&oldid=7087"

