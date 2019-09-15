.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=getLibProperty
   |version=1.3b48
   |description=Returns the value of a [[Token:token_property{{!}}

token_property|Token:token property{{!}}token property]] from a
`Token:library token{{!}}library
token <Token:library_token{{!}}library_token>`__. If the lib argument is
not specified then the `Token:token property{{!}}token
property <Token:token_property{{!}}token_property>`__ will be retrieved
from the `Token:library token{{!}}library
token <Token:library_token{{!}}library_token>`__ that the macro is
currently running from.

Unlike , this function will not retrieve the default value of a campaign
property. Default values are generally programmed as local variables in
a macro, then overridden with the result of this function if this
function returns a value. An example is shown below.

\|usage=

.. code:: mtmacro
   :number-lines:

   getLibProperty(name)
   getLibProperty(name, lib)

**Important Note** As mentioned in the introduction, if the value of the
property on the Token equals the default value, the function will return
nothing! This means that if e.g. you set the default property to

.. code:: mtmacro
   :number-lines:

   Weapons : Shotgun, Pistol, Revolver

And you leave the e.g. the value on the token lib:Compendium unchanged,
so it will also contain the value "Shotgun, Pistol, Revolver", then

.. code:: mtmacro
   :number-lines:

   [getLibProperty("Weapons", "lib:Compendium")]

will return nothing!

\|examples= To get the "init" `Token:token property{{!}}token
property <Token:token_property{{!}}token_property>`__ from the
`Token:library token{{!}}library
token <Token:library_token{{!}}library_token>`__ that a macro is running
from use.

.. code:: mtmacro
   :number-lines:

   [getLibProperty("init")]

To get the "init" `Token:token property{{!}}token
property <Token:token_property{{!}}token_property>`__ from the
`Token:library token{{!}}library
token <Token:library_token{{!}}library_token>`__ if the library token
has such a property. If not, use a default value of "default".

.. code:: mtmacro
   :number-lines:

   [result = getLibProperty("init")]
   [IF(result == ""): result = "default" ]

To get the "init" `Token:token property{{!}}token
property <Token:token_property{{!}}token_property>`__ from a
`Token:library token{{!}}library
token <Token:library_token{{!}}library_token>`__ called "lib:Attacks"
use.

.. code:: mtmacro
   :number-lines:

   [getLibProperty("init", "lib:Attacks")]

}}

`Category:Token Library Function <Category:Token_Library_Function>`__
`Category:Property Function <Category:Property_Function>`__
