.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Library Token}}

Introduced in MapTool version 1.3b46, the Library Token is a special
token type that acts as a library of properties and trusted macros that
may be accessed and called by other macros.

.. _library_token_naming:

Library Token Naming
====================

All library tokens must have a name in the format "Lib:*name*", to
indicate that they are to serve as a Library Token and not a "normal"
token. Example library token names might be:

-  Lib:test
-  Lib:combat
-  Lib:gamemaster

.. _creating_a_library_token:

Creating a Library Token
========================

To create a Library Token, do the following:

#. Drag a new token on to one of the maps in your campaign. The map does
   not need to be visible to players.
#. Rename it with a name in the format **Lib**:*name* (*e.g.*,
   **Lib:DnD**, **Lib:GameRules**, etc.).
#. Right click on the token and make sure that **Visible to Players** is
   checked.
#. Set the token type to NPC (upper right corner of the Token
   Configuration dialog).

After that, you have a Library Token. Note that you cannot have two
library tokens with the same name in the same campaign (even if they're
on different maps!).

Once again, the requirements are:

-  The library token must be visible to players (make sure Visible to
   Players is set in the right-click context menu).
-  The library token need not be on the "Token" layer (you can keep it
   on the "Hidden" layer to hide it from players, although "Visible to
   Players" must still be set to true).
-  The library token must have a name in the format "Lib:*name*"
-  The library token must be present on *only one* map in the campaign
   file.

.. _library_tokens_and_trusted_macros:

Library Tokens and Trusted Macros
=================================

Library Tokens may run `Trusted Macros <Trusted_Macro>`__ or utilize
trusted macro functions provided they meet one of the following
criteria:

-  The library token is **not owned by any players**, OR
-  The macros on the library token are **not player-editable**.

If the Library Token does not meet at least one of those criteria, *it
cannot run trusted macros.* This allows players to create their own
personal library tokens for various *un*\ trusted macros they wish to
run, while at the same time preventing players from altering or
manipulating any token or other element of the campaign for which they
do not have permission to do so.

.. _library_token_macros:

Library Token Macros
====================

Library token macros are created and edited like macros on any token.
Macros on a library token may be called using the
`[MACRO(): <Macros:Branching_and_Looping#MACRO_Option>`__] roll option.
Since Library token macros are trusted, they may perform operations not
available to regular tokens.

.. _library_token_properties:

Library Token Properties
========================

Library token properties can be accessed by using the function. Note
that default property values do **NOT** work using that function.

.. _library_token_oncampaignload:

Library Token onCampaignLoad
============================

Most users will find it worthwhile to add an
`onCampaignLoad <onCampaignLoad>`__ macro to your Lib token that will
use to make your Lib macros accessible like the built-in macro functions
and recognized by the macro editor.

`Category:Token <Category:Token>`__
