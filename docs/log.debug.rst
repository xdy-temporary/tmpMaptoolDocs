======================
log.debug - MapToolDoc
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

   .. rubric:: log.debug
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

            -  `1 log.debug() Function <#log.debug.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: log.debug() Function
            :name: log.debug-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Writes a message to the log at the DEBUG logging level. Use
            `log.setLevel() </rptools/wiki/log.setLevel>`__ to set the
            appropriate level for the ``macro-logger``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     log.debug(message)

         **Parameters**

         -  ``message`` - A string containing the message to be logged.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Output a message to the ``macro-logger`` at the DEBUG level.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: log.debug("Switched to map " + getCurrentMapName())]

            **Returns:**

            Empty string to calling macro. Output is in log file.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        1987-09-25 08:52:18.853 [AWT-EventQueue-0] DEBUG macro-logger - Switched to map Pit of Despair

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `log.getLoggers() </rptools/wiki/log.getLoggers>`__
            `log.setLevel() </rptools/wiki/log.setLevel>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=log.debug&oldid=7396"

