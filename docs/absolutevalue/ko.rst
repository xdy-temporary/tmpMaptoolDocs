.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=absolutevalue
   |description=절대값을 반환한다. The absolute value of a number 는 부호(+,-)를 제외하곤 바뀌지 않는다.

   |usage=
   <source lang="mtmacro" line>
   [h: val = absolutevalue(num)]
   </source>
   이 함수를 아래와 같이 줄여서 쓸 수 있다:
   <source lang="mtmacro" line>
   [h: val = abs(num)]
   </source>

   |examples=
   ====음수(Negative Number)====
   <source lang="mtmacro" line>
   [r: absolutevalue(-3)]
   </source>
   Returns:<source lang="mtmacro" line start=2>3</source>


   ====양수(Positive Number)====
   <source lang="mtmacro" line>
   [r: abs(4)]
   </source>
   Returns:<source lang="mtmacro" line start=2>4</source>


   ====소수(Decimal Number)====
   <source lang="mtmacro" line>
   [r: abs(3.4)]
   </source>
   Returns:<source lang="mtmacro" line start=2>3.4</source>

   }}

`Category:Mathematical Function <Category:Mathematical_Function>`__
