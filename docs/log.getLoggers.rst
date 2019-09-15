===========================
log.getLoggers - MapToolDoc
===========================

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

   .. rubric:: log.getLoggers
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

            -  `1 exampleFunction()
               Function <#exampleFunction.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: exampleFunction() Function
            :name: examplefunction-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Returns a JSON array of available loggers and the current
            logging level for each.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     log.getLoggers()

         **Parameters** None.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get a list of available loggers and format the JSON result.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        <pre>[r: json.indent(log.getLoggers())]</pre>

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: javascript source-javascript

                  #. .. code-block:: none

                        [

                  #. .. code-block:: none

                                {

                  #. .. code-block:: none

                                "name": "macro-logger",

                  #. .. code-block:: none

                                "level": "ERROR"

                  #. .. code:: de2

                            },

                  #. .. code-block:: none

                                {

                  #. .. code-block:: none

                                "name": "net.rptools.lib.io.PackedFile",

                  #. .. code-block:: none

                                "level": "ERROR"

                  #. .. code-block:: none

                            },

                  #. .. code:: de2

                                {

                  #. .. code-block:: none

                                "name": "net.rptools.maptool.client.swing.AbeillePanel",

                  #. .. code-block:: none

                                "level": "ERROR"

                  #. .. code-block:: none

                            },

                  #. .. code-block:: none

                            ...

                  #. .. code:: de2

                        ]

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `log.setLevel <log.setLevel>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=log.getLoggers&oldid=7376"

