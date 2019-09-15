.. contents::
   :depth: 3
..

.. _oncampaignload_macro:

onCampaignLoad Macro
====================

**• Introduced in version 1.3b51**

A special macro that can be created on `library
tokens <Library_Token>`__ to have macro code automatically execute when
a campaign is loaded. A campaign is considered to have been loaded if it
is opened via the File menu, or upon connecting to a server running that
campaign. All output from an macro is discarded, when it is executed
automatically.

This special macro is ideally suited for loading your User Defined
Functions (UDFs) via `defineFunction() <defineFunction>`__.

When an onCampaignLoad macro is executed automatically, it is considered
a `Trusted Macro <Trusted_Macro>`__. If you wish to use trusted
functions within and execute it manually (e.g. while developing macros),
you will have to make sure that it follows all of the rules of `Trusted
Macros <Trusted_Macro>`__.

.. _how_to_create_an_oncampaignload_macro:

How to Create an onCampaignLoad Macro
-------------------------------------

You can create an macro on any `library token <Library_Token>`__; simply
create a macro that is specifically named .

Limitations
-----------

-  Do not make changes within the macro to the library token it resides
   upon. This is not supported by MapTool. A duplicate lib token
   can/will appear and this will/can break stuff.
-  Some macro functions may not work as expected if run in without
   deferring their execution by using the defer option of
   `execLink() <execLink>`__.

   -  `goto() <goto>`__, `setZoom() <setZoom>`__ and similar function
      calls should be placed in a separate macro to be called via
      `execLink() <execLink>`__

.. _example_of_deferred_function_calls:

Example of Deferred Function Calls
----------------------------------

Inside the macro place code like this:

.. code:: mtmacro
   :number-lines:

   [h: link = macroLinkText("deferredCalls@"+getMacroLocation())]
   [h: execLink(link,1)]

And in the deferredCalls() macro place the functions to be deferred.

.. code:: mtmacro
   :number-lines:

   [h: goto("2")]
   [h: setZoom(2)]

`Category:Special Macro <Category:Special_Macro>`__
`Category:Event <Category:Event>`__
