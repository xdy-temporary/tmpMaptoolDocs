.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=math
   |version=1.4.0.5
   |description=
   This is NOT a single MapTool function but a collection of math functions in MapTool. 
   '''Important Note''': All of these functions return a floating-point number (e.g.: `3.0`).

   |usage=
   <source lang="mtmacro" line>
   Numbers:
   [r:val = math.pi()]
   [r:val = math.e()]

   Trigonomotry:
   [r:val = math.acos(degrees)]
   [r:val = math.acos_r(radians)]
   [r:val = math.asin(degrees)]
   [r:val = math.asin_r(radians)]
   [r:val = math.atan(degrees)]
   [r:val = math.atan_r(radians)]
   [r:val = math.atan2(degrees)]
   [r:val = math.atan2_r(radians)]
   [r:val = math.cos(degrees)]
   [r:val = math.cos_r(num)]
   [r:val = math.sin(degrees)]
   [r:val = math.sin_r(num)]
   [r:val = math.tan(degrees)]
   [r:val = math.tan_r(num)]
   [r:val = math.toDegrees(num)]
   [r:val = math.toRadians(degrees)]

   Power and root:
   [r:val = math.sqrt(num)]
   [r:val = math.squareroot(num)]
   [r:val = math.cbrt(num)]
   [r:val = math.cuberoot(num)]
   [r:val = math.pow(num1,num2)]

   Logarithmic
   [r:val = math.log(num)] (this is loge())
   [r:val = math.log10(num)]

   Pythagorean:
   [r:val = math.hypot(num1,num2)]
   [r:val = math.hypotenuse(num1,num2)]

   Simple operations
   [r:val = math.abs(num)]
   [r:val = math.ceil(num)]
   [r:val = math.floor(num)]
   [r:val = math.isEven(num)]
   [r:val = math.isInt(num)]
   [r:val = math.isOdd(num)]
   [r:val = math.max(num1, num2, num2, etc.)]
   [r:val = math.min(num1, num2, num2, etc.)]
   [r:val = math.mod(num1,num2)] 

   </source>

   |examples=
   ====abs====
   <source lang="mtmacro" line>
   [r:val =  math.abs(-3)]
   </source>
   Returns:<source lang="mtmacro" line start=2>3.0</source>

   ====mod====
   <source lang="mtmacro" line>
   [r:val =  math.mod(6,3)]
   </source>
   Returns:<source lang="mtmacro" line start=2>0</source>

   ====pow====
   <source lang="mtmacro" line>
   [r:val =  math.pow(2,3)]
   </source>
   Returns:<source lang="mtmacro" line start=2>8.0</source>

   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
