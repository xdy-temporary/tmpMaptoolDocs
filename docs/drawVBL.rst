.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=drawVBL
   |proposed=false
   |trusted=true
   |version=1.3b89
   |description=
   Draws Vision Blocking Layer (VBL) shapes.

   |usage=
   <source lang="mtmacro" line>
   drawVBL(shapesList)
   </source>

   This function works EXACTLY the same as {{func|eraseVBL}} with the ONLY difference that drawVBL draws the shapes on the vision blocking layer and {{func|eraseVBL}} erases them.


   '''Parameters'''
   {{param|shapesList|A [[JSON_Array|JSON Array]] of [[JSON_Object|JSON objects]], one of the latter for each VBL shape.}}
   The shapes can be one of {{code|"Rectangle"}}, {{code|"Circle"}}, {{code|"Polygon"}} or {{code|"Cross"}}.


   '''Shape - Rectangle and Cross'''<br />
   ''Required arguments.''
   {{param|"x"|Abscissa in pixels. (aka: X-Coordinate)}}
   {{param|"y"|Ordinate in pixels. (aka: Y-Coordinate)}}
   {{param|"w"|Width in pixels. Cannot be smaller than {{code|4}}.}}
   {{param|"h"|Height in pixels. Cannot be smaller than {{code|4}}.}}
   ''Optional arguments''
   {{param|"r"|Rotation on centre axis in degrees. Using default mathematical system: {{code|0}} is no rotation, {{code|+}} is clockwise, {{code|-}} is counterclockwise.}}
   {{param|"facing"|Rotation on centre axis in degrees. Using the MT facing system: {{code|0}} will rotate the shape 90 degrees anticlockwise, {{code|+}} is counterclockwise, {{code|-}} is clockwise. When using both {{code|"r"}} and {{code|"facing"}}, then {{code|"facing"}} takes precedence.}}
   {{param|"rx"|Rotation centre offset in pixels.}}
   {{param|"ry"|Rotation centre offset in pixels. When used the centre over which the shape is rotated is positioned at the (rx,ry) coordinate. The centre defaults to the actual centre of the shape.}}
   {{param|"fill"|If {{code|1}} fills rectangle, otherwise creates empty shape.}}
   {{param|"thickness"|Line thickness from {{code|2}} to {{code|n}} pixels. Lower than {{code|2}} or empty defaults to {{code|2}}. Even numbers only (odd numbers get rounded down by one). Can't be bigger than width or height.}}
   {{param|"scale"|If provided number not {{code|0}}, will scale rectangle by {{code|x}}, ie scale: {{code|2}} is double, scale: {{code|0.5}} is half.}}<br />
   '''Note''' These two shapes (cross and rectangle) are created such that the shape INCLUDING the thickness of the line is always conform to the {{code|"x"}}, {{code|"y"}}, {{code|"w"}} and {{code|"h"}} parameters. E.g. a 100x100px rectangle with {{code|thickness}} 20 will result in a 100x100px rectangle. These are the ONLY shapes for which this check is made! Without the check the rectangle would cover an area of 110x110px (10 on the inside and 10 on the outside of the shape). This correction is also the reason why shapes cannot be smaller than 4px and the {{code|thickness}} is always even.<br />
   ''Example:''<source lang="mtmacro">
   [h:rectangle = "{'shape':'rectangle','x':50,'y':50,'w':100,'h':200,'r':45,'fill':1,'thickness':1,'scale':0}"]
   [h:cross = "{'shape':'cross','x':-50,'y':-50,'w':50,'h':100,'r':30,'fill':1,'thickness':1,'scale':2}"]
   </source><br />


   '''Shape - Circle'''<br />
   ''Required arguments''
   {{param|"x"|see {{code|"shape":"rectangle"}}.}}
   {{param|"y"|see {{code|"shape":"rectangle"}}.}}
   {{param|"radius"|This is the distance in pixels between the centre of the circle to its furthest point (is one of its vertices).}}
   {{param|"sides"|Specifies how many sides the polygon will have to approximate a circle, from {{code|3}} to {{code|100}}.}}
   ''Optional arguments''
   {{param|"r"|see {{code|"shape":"rectangle"}}.}}
   {{param|"facing"|see {{code|"shape":"rectangle"}}.}}
   {{param|"rx"|see {{code|"shape":"rectangle"}}.}}
   {{param|"ry"|see {{code|"shape":"rectangle"}}.}}
   {{param|"fill"|see {{code|"shape":"rectangle"}}.}}
   {{param|"thickness"|see {{code|"shape":"rectangle"}}.}}
   {{param|"scale"|see {{code|"shape":"rectangle"}}.}}<br /><br />
   ''Example:''<source lang="mtmacro">
   [h:circle = "{'shape':'circle', 'X':50, 'Y':100, 'radius':200, 'thickness':3, 'fill':0, 'sides':12,'r':45}"]</source><br />
   Note that this shape can be used to easily create regular polygons, e.g. a triangle:<source lang="mtmacro">
   {"shape":"circle", "X":50, "Y":100, "radius":200, "sides":3, "thickness":3, "fill":0, "r":30}</source><br />
   and a square (note that this square does ''not'' have the dimensions 200x200 but ~105x105 !):<source lang="mtmacro">
   {"shape":"circle", "X":50, "Y":100, "radius":200, "thickness":3, "fill":0, "sides":4,"r":45}</source>
   … or hexagons.<br /><br />

   '''Shape - Polygon'''<br />
   ''Required arguments''
   {{param|"points"|[[JSON_Array|JSON Array]] of 2 or more {{code|"x"}}, {{code|"y"}} coordinates.}}<br />
   ''Optional arguments''
   {{param|"close"| If {{code|1}} then it will close the polygon otherwise it will leave it open.}}
   {{param|"r"|see {{code|"shape":"rectangle"}}.}}
   {{param|"facing"|see {{code|"shape":"rectangle"}}.}}
   {{param|"rx"|see {{code|"shape":"rectangle"}}.}}
   {{param|"ry"|see {{code|"shape":"rectangle"}}.}}
   {{param|"fill"|see {{code|"shape":"rectangle"}}.}}
   {{param|"thickness"|see {{code|"shape":"rectangle"}}.}}<br /><br />
   ''Example:''<source lang="mtmacro">
   [h:polygon = "{'shape':'polygon','r':0,'close':1,'thickness':10,'points':[{'x':0,'y':0},{'x':200,'y':200},{'x':150,'y':10}]}"] </source><br />


   |example=
   This example builds an array of the object from the above examples and then feeds that array into the drawVBL function
   <source lang="mtmacro" line>
   [h:rectangle    = "{'shape':'rectangle','x':50,'y':50,'w':100,'h':200,'r':45,'fill':1,'thickness':1,'scale':0}"]
   [h:cross    = "{'shape':'cross','x':-50,'y':-50,'w':50,'h':100,'r':30,'fill':1,'thickness':1,'scale':2}"]
   [h:circle   = "{'shape':'circle', 'X':50, 'Y':100, 'radius':200, 'thickness':3, 'fill':0, 'sides':12,'r':45}"]
   [h:polygon  = "{'shape':'polygon','r':0,'close':1,'thickness':10,'points':[{'x':0,'y':0},{'x':200,'y':200},{'x':150,'y':10}]}"] 
   [h:objectArrary = json.append('',rectangle, cross, circle, polygon)]
   [h:drawVBL(objectArrary)]
   </source>
   results in:<br/>
   [[Image:VBL_Shapes.jpg|Image:VBL_Shapes.jpg]]


   |also=
   [[Introduction_to_Vision_Blocking|Introduction to Vision Blocking]], {{func|eraseVBL}}
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
`Category:VBL Function <Category:VBL_Function>`__
