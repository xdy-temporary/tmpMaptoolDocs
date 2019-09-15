=========================
log.setLevel - MapToolDoc
=========================

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

   .. rubric:: log.setLevel
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

            -  `1 log.setLevel()
               Function <#log.setLevel.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: log.setLevel() Function
            :name: log.setlevel-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Set the logging level for the specified logger.
            The log file will be found in your user directory under
            ``.maptool-rptools/logs``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     log.setLevel(logger, loglevel)

         **Parameters**

         -  ``logger`` - String containing a logger name.
         -  ``loglevel`` - String containing a log level:
            DEBUG,INFO,WARN,ERROR,FATAL

         The default level for all loggers is ERROR which means that
         only messages at ERROR or FATAL log level will be output. The
         levels noted above are in verbosity order from most(DEBUG) to
         least(FATAL).

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Set the logging level for the MapToolLineParser to **WARN**.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: log.setLevel("net.rptools.maptool.client.MapToolLineParser","WARN")]

            **Returns:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        WARN

            Get a list of loggers and then, using
            `input() <input>`__, select a logging level
            for it.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: loggers = json.sort(log.getLoggers(),"a","name")]

                  #. .. code-block:: none

                        [h: loggerList = ""]

                  #. .. code-block:: none

                        [h, FOREACH(logger, loggers), CODE: {

                  #. .. code-block:: none

                            [h: loggerList = listAppend(loggerList,json.get(logger,"name"))]

                  #. .. code:: de2

                        }]

                  #. .. code-block:: none

                        [h:status=input(

                  #. .. code-block:: none

                            "junkVar|Select a Logger and Level||LABEL|SPAN=TRUE",

                  #. .. code-block:: none

                            "lname|"+loggerList+"|Logger|LIST|VALUE=STRING",

                  #. .. code-block:: none

                            "level|DEBUG,INFO,WARN,ERROR,FATAL|Level|LIST|VALUE=STRING")]

                  #. .. code:: de2

                        [h:abort(status)]

                  #. .. code-block:: none

                        [r: "Setting <i><b>" + lname + "</b></i> to <b>" + level + "</b>."]

                  #. .. code-block:: none

                        [h: log.setLevel(lname,level)]

            | 

            |SelectLoggerLevel.png|

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `log.getLoggers() <log.getLoggers>`__
             `Available Loggers <Available_Loggers>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=log.setLevel&oldid=7402"

