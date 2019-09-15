.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub}}

.. raw:: mediawiki

   {{MacroFunction
   |name=getInitiativeHold
   |version=1.3b41
   |description=Returns if the [[Token:token{{!}}

token|Token:token{{!}}token]] is on
`Initiative:hold{{!}}hold <Initiative:hold{{!}}hold>`__ in the
`Initiative:initiative panel{{!}}initiative
panel <Initiative:initiative_panel{{!}}initiative_panel>`__ or not. This
function will return 1 if the
`Token:token{{!}}token <Token:token{{!}}token>`__ is on
`Initiative:hold{{!}}hold <Initiative:hold{{!}}hold>`__ or 0 if it is
not.

\|usage=

.. code:: mtmacro
   :number-lines:

   getInitiativeHold()

\|examples=

.. code:: mtmacro
   :number-lines:

   [r: if(getInitiativeHold(), "You are on hold", "You are not on hold")]

}}

`Category:Initiative Function <Category:Initiative_Function>`__
