============================
varsFromStrProp - MapToolDoc
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

   .. rubric:: varsFromStrProp
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
            | ** This article needs:** *Documentation on how the
              decor(suffixed/unsuffixed) parameter works.*

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 varsFromStrProp()
               Function <#varsFromStrProp.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: varsFromStrProp() Function
            :name: varsfromstrprop-function

         .. container:: template_version

            • **Introduced in version 1.3b42**

         .. container:: template_description

            Creates variables from a `string property
            list </rptools/wiki/Macros:string_property_list>`__ with the
            values assigned to variables with the names of the keys in
            the `string property
            list </rptools/wiki/Macros:string_property_list>`__. The
            function returns the number of variables that were created.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  varsFromStrProp(props)
                  varsFromStrProp(props, decor)

         **Parameters**

         -  ``props`` - A string property list.
         -  ``decor`` - Either SUFFIXED, which appends an underscore to
            the variable name, or UNSUFFIXED (default) which leaves the
            name as is.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: varsFromStrProp("a=blah; b=doh; c=meh")]

                  #. .. code-block:: none

                        [r: a] [r: b] [r: c]

            **Returns**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     blah doh meh

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `strPropFromVars() </rptools/wiki/strPropFromVars>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b49** - Added ``suffixed`` or ``unsuffixed``
               parameter option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=varsFromStrProp&oldid=7477"

