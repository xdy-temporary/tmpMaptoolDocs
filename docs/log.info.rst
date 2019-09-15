=====================
log.info - MapToolDoc
=====================

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

   .. rubric:: log.info
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

            -  `1 log.info() Function <#log.info.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: log.info() Function
            :name: log.info-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Writes a message to the log file at the INFO logging level.
            Use `log.setLevel() <log.setLevel>`__ to set
            the appropriate level for the ``macro-logger``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     log.info(message)

         **Parameters**

         -  ``message`` - A string containing the message to be logged.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Output a message to the ``macro-logger`` at the INFO level.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: log.info("There's no place like home.")]

            **Returns:**

            Empty string to calling macro. Output is in log file.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        1939-08-25 09:19:22.844 [AWT-EventQueue-0] INFO  macro-logger - There's no place like home.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `log.getLoggers() <log.getLoggers>`__
            `log.setLevel() <log.setLevel>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=log.info&oldid=7400"

