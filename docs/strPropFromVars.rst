============================
strPropFromVars - MapToolDoc
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

   .. rubric:: strPropFromVars
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

            -  `1 strPropFromVars()
               Function <#strPropFromVars.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: strPropFromVars() Function
            :name: strpropfromvars-function

         .. container:: template_description

            Creates a property string from the names and values of the
            variables listed in the varList string.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h: strPropFromVars(varList) ]
                  [h: strPropFromVars(varList, varStyle) ]
                  [h: strPropFromVars(varList, varStyle, delim) ]

         **Parameters**

         -  ``varList`` - A list of variable names, separated by ",".
         -  ``varStyle`` - Either "SUFFIXED" or "UNSUFFIXED". The
            "SUFFIXED" option will look for variables with underscores
            appended to the given names. Defaults to "UNSUFFIXED".
         -  ``delim`` - The delimiter for the return string. Defaults to
            ";".

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [H: props = "a=3 ; b=bob ; c=cow ; "]

                  #. .. code-block:: none

                        [H: varsFromStrProp(props, "SUFFIXED")] <!-- creates variables a_, b_, c_ -->

                  #. .. code-block:: none

                        [strPropFromVars("c,a,b", "SUFFIXED")]

            **Returns**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     "c=cow ; a=3 ; b=bob"

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `varsFromStrProp() <varsFromStrProp>`__

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Made ``varStyle`` optional.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=strPropFromVars&oldid=7479"

