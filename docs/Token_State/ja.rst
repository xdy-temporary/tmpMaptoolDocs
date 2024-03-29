.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Token State}}

.. raw:: mediawiki

   {{Translation}}

A *token state* is a binary (*i.e.*, it has two possible values, on or
off) condition that is set for a given `token <Token:token>`__. States
are frequently used for conditions or statuses that affect a particular
character in a game (for example "Bloodied" or "Fatigued" or "Fighting
Defensively") and frequently have images associated with them that are
displayed to players and the GM. However, they can be used for any
application in which a condition having only two possible values would
be useful.

The image below shows a token state with an associated image applied to
the token. In this case, the state name was configured by the individual
creating the campaign to be called "Bloodied" and to have the associated
image overlay (the state image is courtesy of the RPTools forum member
AidyBaby).

.. figure:: State-example.jpg
   :alt: Image:State-example.jpg

   Image:State-example.jpg

トークン・ステータスのセット・アップ
====================================

States are configured by the user and are specific to a given campaign.
States are configured via the Campaign Properties window, under the
**States** tab. See `Configuring States <States:Configuring_states>`__
for details on setting up states for your campaign.

マクロにトークン・ステータスを追加する
======================================

States are special variables that can be referenced by macros using the
general format *state.statename* where *statename* is the name
configured by the user for a given state.

用例
----

States can be retrieved using macros.

.. code:: mtmacro
   :number-lines:

   [h:isBloodied=state.Bloodied]
   [isBloodied]

Will return 0 if *state.Bloodied* is off (in other words, the token does
*not* currently have the state called "Bloodied" set), and 1 if
*state.Bloodied* is on.

マクロによるトークン・ステータスの設定
======================================

States can also be set using macros, by assigning a value of 1 or 0 to
the token state.

.. _用例_1:

用例
----

Suppose we want to check to see if a token is "dead" and if so, set the
"Dead" state on that token. We are assuming two things:

#. "Death" occurs if the token's hit points (HP) have been reduced to 0
   or below; and
#. A state called "Dead" has been configured in the Campaign Properties.

To check for "death" and, if required, set the appropriate state, we
write the following simple macro:

.. code:: mtmacro
   :number-lines:

   [h:state.Dead=if(HP <= 0, 1, 0)]

This statement evaluates the condition within the if() statement, and if
true, assigns the value 1 to *state.Dead*. If the condition *HP >= 0* is
false, on the other hand, the value 0 is assigned to *state.Dead*.

Finally, if an image overlay is associated with the state called "Dead",
it will appear if *state.Dead* equals 1, and disappear if *state.Dead*
equals 0.

Use the function instead if your state name has a space in it.

.. raw:: mediawiki

   {{DISPLAYTITLE:Token State}}

.. raw:: mediawiki

   {{Languages|Token State}}

{{#customtitle:トークン・ステータス}}

`Category:Token <Category:Token>`__
