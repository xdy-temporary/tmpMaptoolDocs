.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=isBarVisible
   |version=1.3b46
   |description=
   Returns {{true}} if the specified [[Token_Bar|Token Bar]] on the [[Current_Token|Current Token]] is visible, or {{false}} if it is not.

   |usage=
   <source lang="mtmacro" line>
   isBarVisible(bar)
   </source>
   '''Parameters'''
   {{param|bar|A string that contains the name of the bar that has its visibility checked.}}

   |examples=
   Displays {{code|The health bar is visible!}} if the bar named {{code|Health}} is set to visible; otherwise it displays {{code|The health bar is not visible!}}.
   <source lang="mtmacro" line>
   [if(isBarVisible("Health")), code:
   {
       The health bar is visible!
   };{
       The health bar is not visible!
   }]
   </source>

   Toggles the visibility of the bar named {{code|Fatigue}}.
   <source lang="mtmacro" line>
   [h: setBarVisible("Fatigue", !isBarVisible("Fatigue"))]
   [h: abort(0)]
   </source>

   |also=
   {{func|setBarVisible}}, 
   {{func|getBar}}, 
   {{func|setBar}}

   }}

`Category:Bar Function <Category:Bar_Function>`__
