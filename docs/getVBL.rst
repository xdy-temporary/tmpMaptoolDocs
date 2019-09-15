.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getVBL
   |proposed=false
   |trusted=true
   |version=1.3b90
   |description=
   Gets the Vision Blocking Layer (VBL) shapes for the area specified in the {{code|shape}} parameter.

   |usage=
   <source lang="mtmacro" line>
   getVBL(shape,format)
   </source>

   This function retrieves the VBL found in the given shape.

   '''Parameters'''
   {{param|shape|A JSON object as described in {{func|drawVBL}}.}}
   {{param|format|Boolean. Returns a JSON object if {{false}}, or an JSON array of coordinates if {{true}}.  In either case, the returned shape covers the VBL found in the area.}}


   ''Example:''<source lang="mtmacro">
   [h:rectangle = "{'shape':'rectangle','x':50,'y':50,'w':100,'h':200,'r':45,'fill':1,'thickness':1,'scale':0}"]
   [r:vblData   = getVBL(rectangle , 0)]
   </source><br />

   |also=
   [[Introduction_to_Vision_Blocking|Introduction to Vision Blocking]], {{func|eraseVBL}}, {{func|drawVBL}}
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
`Category:VBL Function <Category:VBL_Function>`__
