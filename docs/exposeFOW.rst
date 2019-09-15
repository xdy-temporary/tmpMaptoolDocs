======================
exposeFOW - MapToolDoc
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

   .. rubric:: exposeFOW
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

            -  `1 exposeFOW() Function <#exposeFOW.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: exposeFOW() Function
            :name: exposefow-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.3b76**

         .. container:: template_description

            Clears the Fog of War (FOW) for all **selected** tokens on
            the current map according to their sight settings. An
            optional ``mapName`` parameter allows exposure on maps other
            than the current map. *Note that unless the optional
            ``tokens`` parameter is provided there must be tokens
            selected on the map.*

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  exposeFOW()
                  exposeFOW(mapname)
                  exposeFOW(mapName,tokens)
                  exposeFOW(mapName,tokens, delim)

         **Parameters**

         -  ``mapname`` - Optional map name.
         -  ``tokens`` - Optional delimited string list or JSON array of
            tokens.
         -  ``delim`` - Delimiter for tokens parameter. Defaults to ",".
            Use "json" for a JSON array.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <!-- Expose FoW for selected tokens on current map. -->

                  #. .. code-block:: none

                        [h: exposeFOW()]

                  #. .. code-block:: none

                        <!-- Expose FoW for selected tokens on the named map. -->

                  #. .. code-block:: none

                        [h: exposeFOW("Pit of Despair")]

                  #. .. code:: de2

                        <!-- Expose FoW for indicated tokens on the named map. -->

                  #. .. code-block:: none

                        [h: exposeFOW("Pit of Despair", "Westley, Count Rugen")]

                  #. .. code-block:: none

                        <!-- Expose FoW for indicated tokens, in a list delimited by a colon (":"), on the named map. -->

                  #. .. code-block:: none

                        [h: exposeFOW("Pit of Despair", "Westley:Count Rugen", ":")])]

                  #. .. code-block:: none

                        <!-- Expose FoW for indicated tokens in a JSON array on the named map. -->

                  #. .. code:: de2

                        [h: exposeFOW("Pit of Despair",'["Westley", "Count Rugen"]', "json")]

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.5.4** - Added tokens and delim parameters.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=exposeFOW&oldid=7456"

