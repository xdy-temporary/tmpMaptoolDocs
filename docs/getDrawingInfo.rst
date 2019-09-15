.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getDrawingInfo
   |version=1.5.2
   |trusted=true
   |description=
   Returns extensive information about the specified drawing.  The information is returned as a [[Introduction_to_JSON_Datatypes|JSON]] object.
   |usage=
   <source lang="mtmacro" line>
   getDrawingInfo(mapName, drawingId)
   </source>
   '''Parameters'''
   {{param|mapName|A string containing the name of the map.}}
   {{param|drawingId|A string containing the id of the drawing. The easiest way to discover a drawing's Id is via the Draw Explorer interface.}}
   |examples=
   <source lang="mtmacro" line>
   [h: id = findDrawings(getCurrentMapName(),"Funky Shape")]
   [h: dinfo = getDrawingInfo(getCurrentMapName(), id)]
   <pre>[r: json.indent(dinfo,2)]</pre>
   </source>
   '''Returns'''
   <source lang="css" line>
   {
     "fillColor": "#ffffff",
     "path":   [
           {
         "x": 250,
         "y": 200
       },
           {
         "x": 250,
         "y": 400
       },
           {
         "x": 500,
         "y": 400
       },
           {
         "x": 500,
         "y": 200
       },
           {
         "x": 400,
         "y": 200
       },
           {
         "x": 400,
         "y": 300
       },
           {
         "x": 350,
         "y": 300
       },
           {
         "x": 350,
         "y": 200
       },
           {
         "x": 250,
         "y": 200
       }
     ],
     "penWidth": 3,
     "name": "Funky Shape",
     "bounds":   {
       "x": 250,
       "width": 250,
       "y": 200,
       "height": 200
     },
     "penColor": "#000000",
     "id": "B7041D43935D4BDCA330E431D892DEAB",
     "type": "Polygon",
     "opacity": 1,
     "isEraser": 0,
     "layer": "TOKEN"
   }
   </source>
   |also=
   {{func|getDrawingProperties}}
   }}

`Category:Draw Function <Category:Draw_Function>`__
