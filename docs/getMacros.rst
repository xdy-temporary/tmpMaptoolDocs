======================
getMacros - MapToolDoc
======================

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

   .. rubric:: getMacros
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

            -  `1 getMacros() Function <#getMacros.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getMacros() Function
            :name: getmacros-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a list of the labels of all of the `macro
            buttons </rptools/wiki/Macro_Button>`__ on the `Current
            Token </rptools/wiki/Current_Token>`__. The type of the
            value returned depends on the delimiter parameter.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacros()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacros(delim)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getMacros(delim, id)

         **Parameters**

         -  ``delim`` - The delimiter used to separate the values in the
            `String List </rptools/wiki/String_List>`__, a JSON array is
            returned if ``"json"`` is specified as the delimiter.
            Defaults to ``","``
         -  ``id`` - The token ``id`` of the token that the function is
            executed on.

            .. container:: template_trusted_param

                Note: This parameter can only be used in a `Trusted
               Macro </rptools/wiki/Trusted_Macro>`__. 

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            To display all of the `macro
            button </rptools/wiki/Macro_Button>`__ labels on the current
            `token </rptools/wiki/Token>`__ use.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: macroLabels = getMacros()]

                  #. .. code-block:: none

                        [foreach(macro, macroLabels, "<br>"): macro]

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``json`` delimiter option.
            -  **1.3b51** - Added optional token ``id`` parameter.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getMacros&oldid=5884"

