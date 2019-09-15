.. contents::
   :depth: 3
..

A *token property* is a variable (string or numeric) that resides on a
particular `token <Token:token>`__ within MapTool, and may be called
upon or evaluated by macros.

Token properties are tailored to fit each individual campaign file and
the macros contained in that campaign. Multiple sets of token properties
can be created (allowing them to be applied to different classes of
token - for example, PC tokens versus NPC tokens). These multiple sets
are called `token property types <Token:token_property_type>`__.

.. _default_token_properties:

Default Token Properties
========================

By default, MapTool has the following set of token properties.

| ``Strength (Str)``
| ``Dexterity (Dex)``
| ``Constitution (Con)``
| ``Intelligence (Int)``
| ``Wisdom (Wis)``
| ``Charisma (Char)``
| ``*@HP``
| ``*@AC``
| ``Defense (Def)``
| ``Movement (Mov)``
| ``*Elevation (Elv)``
| ``Description (Des)``

.. _setting_campaign_properties:

Setting Campaign Properties
===========================

Campaign properties are edited using the Campaign Properties dialog,
which is found under **Edit -> Campaign Properties** on the MapTool
menu. They can be directly edited in the Campaign Properties dialog, or
pasted in from a text editor of choice.

.. _token_property_format:

Token Property Format
---------------------

The format for all token properties.

``#*@PropertyName(ShortName):default value``

.. _example_token_property:

Example Token Property
----------------------

``*@HealingSurges(Surges):9``

Will display **Surges: 9** in the statsheet.

.. _controlling_token_property_display:

Controlling Token Property Display
----------------------------------

There are three "switches" (shown in the format string above) that
control how campaign properties are displayed in the popup *statsheet*
when the user hovers his mouse over a token:

\* - Displays the property on the *statsheet*

@ - Property will be visible only to the owner of that token

# - Property will be visible only to the GM

Note that the **\*** switch is essential for the property to be
displayed on the statsheet; the **@** and **#** are optional modifiers
to that display. If no switch is set in the property string, the
property will be present on the token and accessible to macros but will
*not* be displayed in the popup statsheet.

`Category:Token <Category:Token>`__
