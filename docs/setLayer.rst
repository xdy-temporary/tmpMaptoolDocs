.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=setLayer
   |trusted=true
   |version=1.3b48
   |description=
   Sets the [[Map_Layer|Map Layer]] that a [[Token|Token]] is on.

   The [[Map_Layer|Map Layer]] is one of:
   * {{code|TOKEN}}
   * {{code|GM}} also known as Hidden
   * {{code|OBJECT}}
   * {{code|BACKGROUND}}
    

   |usage=
   <source lang="mtmacro" line>
   setLayer(layer)
   setLayer(layer, id)
   setLayer(layer, id, forceshape)
   setLayer(layer, id, forceshape, mapname)
   </source>
   '''Parameters'''
   {{param|layer|The layer to move the [[Token|Token]] to.}}
   {{param|id|The token {{code|id}} of the token which has its layer set, defaults to the [[Current_Token|Current Token]].}}
   {{param|forceshape|}}If {{true}}, change the token shape type to TOP_DOWN if the layer is {{code|OBJECT}}, and to a shape reflecting its image if the layer is {{code|TOKEN}}. Defaults to {{true}}.
   {{param|mapname|The name of the map to find the token.  Defaults to the current map.}}

   |examples=
   When an NPC token is dead, send it to the Object layer, otherwise leave it where it is.
   <source lang="mtmacro" line>
   [h: layerName = getLayer()]
   [h: layerName = if(state.Dead&&isNPC(), "OBJECT", layerName)]
   [h: setLayer(layerName)]
   </source>

   Toggle a token between the Hidden and Token layers.
   <source lang="mtmacro" line>
   [h: layerName = getLayer()]
   [h: layerName = if(layerName=="GM", "TOKEN", "GM")]
   [h: setLayer(layerName)]
   </source>

   |also=
   [[getLayer|getLayer()]]

   |changes=
   {{change|1.3b51|Added {{code|id}} parameter option.}}
   {{change|1.5.4|Added {{code|mapname}} parameter option.}}
   }}

`Category:Token Function <Category:Token_Function>`__
