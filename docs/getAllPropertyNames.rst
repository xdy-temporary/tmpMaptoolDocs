.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getAllPropertyNames
   |version=1.3b48
   |description=Gets a list containing the [[Token:token_property|token property]] names that are defined in the [[Campaign:campaign_properties|campaign properties]]. The type of the value returned depends on the delimiter parameter. 
   * If the delimiter is not specified then a [[Macros:string_list|string list]] is returned and the default value of {{code|","}} is used.
   * If the delimiter is {{code|"json"}} then a [[JSON_Array|JSON Array]] is returned.
   * Otherwise, a [[Macros:string_list|string list]] is returned with the delimiter passed in.
    
   |usage=
   <source lang="mtmacro" line>
   getAllPropertyNames()
   </source>
   <source lang="mtmacro" line>
   getAllPropertyNames(type)
   </source>
   <source lang="mtmacro" line>
   getAllPropertyNames(type, delim)
   </source>

   If type is specified then the [[Macros:string_list|string list]] contains the [[Token:token_property|property]] names for that [[Token:token_property_type|token property type]], otherwise it will contain the [[Token:token_property|token property]] names for all [[Token:token_property_type|token property type]]s. If delim is specified then it is used to separate the values in the [[Macros:string_list|string list]], if it is not specified then it defaults to ','.

   |examples=
   You can use the following code to print out all of the properties in the [[Campaign:campaign_properties|campaign properties]] list..
   <source lang="mtmacro" line>
   Campaign Properties<br>
   [h: props = getAllPropertyNames()]
   [foreach(name, props, "<br>"): name]
   </source>

   If you have two token property sets, for instance "PC" and "NPC", you could print out all of the properties for the "PC" property set like so:
   <source lang="mtmacro" line>
   PC Properties<br>
   [h: props=getAllPropertyNames("PC")]
   [foreach(name, props, "<br>"): name]
   </source>

   |changes=
   {{change|1.3b49|Added {{code|json}} delimiter option.}}

   }}

`Category:Token Function <Category:Token_Function>`__ `Category:Property
Function <Category:Property_Function>`__
