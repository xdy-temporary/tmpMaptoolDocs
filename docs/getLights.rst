.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getLights
   |version=1.3b48
   |description=Returns a string list containing the names of the [[Map:light_source{{!}}

light_source|Map:light source{{!}}light source]]s that are turned on for
the `Current Token <Current_Token>`__. The type of the value returned
depends on the delimiter parameter.

\|usage=

.. code:: mtmacro
   :number-lines:

   getLights()
   getLights(type)
   getLights(type, delim)
   getLights(type, delim, id)
   getLights(type, delim, id, mapname)

**Parameters** string_list|Macros:string list{{!}}string list]]. If set
to "json", a `JSON Array <JSON_Array>`__ is returned. Defaults to ",".}}

\|examples= To get a `Macros:string list{{!}}string
list <Macros:string_list{{!}}string_list>`__ of all of the
`LightSource:light sources <LightSource:light_source>`__ that the
current `Token:token{{!}}token <Token:token{{!}}token>`__ has on.

.. code:: mtmacro
   :number-lines:

   [getLights()]

To get a `Macros:string list{{!}}string
list <Macros:string_list{{!}}string_list>`__ of the `LightSource:light
sources <LightSource:light_source>`__ that the current
`Token:token{{!}}token <Token:token{{!}}token>`__ has on with the
`LightSource:type{{!}} lighet source
type <LightSource:type{{!}}_lighet_source_type>`__ of "Generic".

.. code:: mtmacro
   :number-lines:

   [getLights("Generic")]

\|changes=

}}

`Category:Light Function <Category:Light_Function>`__ `Category:Token
Function <Category:Token_Function>`__
