.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=eraseVBL
   |proposed=false
   |trusted=true
   |version=1.3b89
   |description=
   Erases Vision Blocking Layer (VBL) shapes.

   |usage=
   <source lang="mtmacro" line>
   eraseVBL(shapesList)
   </source>

   This function works EXACTLY the same as {{func|drawVBL}} with the ONLY difference that {{func|drawVBL}} draws the shapes on the vision blocking layer and eraseVBL erases them. For descriptions on parameters and more examples goto the {{func|drawVBL}} page. 

   |example=
   This example erases a (solid) block of VBL of 200x200 pixels, centered on the origin of the map
   <source lang="mtmacro" line>
   [h:rectangle    = "{'shape':'rectangle','x':0,'y':0,'w':200,'h':200, 'fill':1}"]
   [h:objectArrary = json.append('',rectangle)]
   [h:eraseVBL(objectArrary)]
   </source>
   [[Category:VBL_Function|Category:VBL Function]]

   |also=
   [[Introduction_to_Vision_Blocking|Introduction to Vision Blocking]], {{func|drawVBL}}
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
