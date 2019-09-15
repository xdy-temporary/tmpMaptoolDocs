===========================
getDrawingInfo - MapToolDoc
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

   .. rubric:: getDrawingInfo
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

            -  `1 getDrawingInfo()
               Function <#getDrawingInfo.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: getDrawingInfo() Function
            :name: getdrawinginfo-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Returns extensive information about the specified drawing.
            The information is returned as a
            `JSON <Introduction_to_JSON_Datatypes>`__
            object.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDrawingInfo(mapName, drawingId)

         **Parameters**

         -  ``mapName`` - A string containing the name of the map.
         -  ``drawingId`` - A string containing the id of the drawing.
            The easiest way to discover a drawing's Id is via the Draw
            Explorer interface.

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: id = findDrawings(getCurrentMapName(),"Funky Shape")]

                  #. .. code-block:: none

                        [h: dinfo = getDrawingInfo(getCurrentMapName(), id)]

                  #. .. code-block:: none

                        <pre>[r: json.indent(dinfo,2)]</pre>

            **Returns**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: css source-css

                  #. .. code-block:: none

                        {

                  #. .. code-block:: none

                          "fillColor": "#ffffff",

                  #. .. code-block:: none

                          "path":   [

                  #. .. code-block:: none

                                {

                  #. .. code:: de2

                              "x": 250,

                  #. .. code-block:: none

                              "y": 200

                  #. .. code-block:: none

                            },

                  #. .. code-block:: none

                                {

                  #. .. code-block:: none

                              "x": 250,

                  #. .. code:: de2

                              "y": 400

                  #. .. code-block:: none

                            },

                  #. .. code-block:: none

                                {

                  #. .. code-block:: none

                              "x": 500,

                  #. .. code-block:: none

                              "y": 400

                  #. .. code:: de2

                            },

                  #. .. code-block:: none

                                {

                  #. .. code-block:: none

                              "x": 500,

                  #. .. code-block:: none

                              "y": 200

                  #. .. code-block:: none

                            },

                  #. .. code:: de2

                                {

                  #. .. code-block:: none

                              "x": 400,

                  #. .. code-block:: none

                              "y": 200

                  #. .. code-block:: none

                            },

                  #. .. code-block:: none

                                {

                  #. .. code:: de2

                              "x": 400,

                  #. .. code-block:: none

                              "y": 300

                  #. .. code-block:: none

                            },

                  #. .. code-block:: none

                                {

                  #. .. code-block:: none

                              "x": 350,

                  #. .. code:: de2

                              "y": 300

                  #. .. code-block:: none

                            },

                  #. .. code-block:: none

                                {

                  #. .. code-block:: none

                              "x": 350,

                  #. .. code-block:: none

                              "y": 200

                  #. .. code:: de2

                            },

                  #. .. code-block:: none

                                {

                  #. .. code-block:: none

                              "x": 250,

                  #. .. code-block:: none

                              "y": 200

                  #. .. code-block:: none

                            }

                  #. .. code:: de2

                          ],

                  #. .. code-block:: none

                          "penWidth": 3,

                  #. .. code-block:: none

                          "name": "Funky Shape",

                  #. .. code-block:: none

                          "bounds":   {

                  #. .. code-block:: none

                            "x": 250,

                  #. .. code:: de2

                            "width": 250,

                  #. .. code-block:: none

                            "y": 200,

                  #. .. code-block:: none

                            "height": 200

                  #. .. code-block:: none

                          },

                  #. .. code-block:: none

                          "penColor": "#000000",

                  #. .. code:: de2

                          "id": "B7041D43935D4BDCA330E431D892DEAB",

                  #. .. code-block:: none

                          "type": "Polygon",

                  #. .. code-block:: none

                          "opacity": 1,

                  #. .. code-block:: none

                          "isEraser": 0,

                  #. .. code-block:: none

                          "layer": "TOKEN"

                  #. .. code:: de2

                        }

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `getDrawingProperties() <getDrawingProperties>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getDrawingInfo&oldid=7353"

