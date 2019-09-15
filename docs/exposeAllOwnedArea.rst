.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=exposeAllOwnedArea
   |trusted=true
   |version=1.5.0
   |description=
   Exposes all area visible to tokens owned by the current player that have vision turned on in the token editor.  The actual area exposed depends on server settings (like '''Individual Views''') and various MapTool Preferences.

   |usage=
   <source lang="mtmacro" line>
   exposeAllOwnedArea(mapName)
   </source>
   '''Parameters'''
   {{param|mapName|The name of an existing map within the campaign.  This map does not need to be the one currently visible.  If the map holds no tokens with vision owned by the current player, no additional fog-of-war is exposed, but fog already exposed is not reset.}}

   |examples=

   |also=
   {{func|exposeFOW}}, {{func|toggleFoW}}
   }}

`Category:FoW <Category:FoW>`__
