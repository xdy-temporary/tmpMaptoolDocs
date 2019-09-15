.. contents::
   :depth: 3
..

Introduction
============

|Tutorial-names-and-images.jpg| This short macro tutorial illustrates
how to combine several string list functions and token functions to
generate a dialog that presents both the names and token images for a
list of tokens. The resulting macro will generate an
`input() <Macros:Functions:input>`__ dialog similar to the one shown to
the right; which, in this macro, is used to select a token and change
its name. The macro illustrated here is based on a macro example
provided by RPTool forum member (and MapTool contributor!)
**Knizia.fan**.

Assumptions
-----------

This macro requires a `string list <Macros:string_list>`__ containing
the names of a collection of tokens. This list can be generated in
numerous ways; in this tutorial it is generated using
`getExposedTokenNames() <Macros:Functions:getExposedTokenNames>`__.

We will also assume that there are 4 tokens visible on the map, named
(imaginatively) "Token 1", "Token 2", "Token 3", and "Token 4".

.. _macro_code_and_explanation:

Macro Code and Explanation
==========================

The `full macro code <Tutorials:Macros:List_with_images_fullcode>`__ is
broken into functional groupings and explained below.

.. _get_and_assign_string_lists:

Get and Assign String Lists
---------------------------

.. code:: mtmacro
   :number-lines:

   [H: tokenList=getExposedTokenNames()]
   [H: imgList = tokenList]

Uses `getExposedTokenNames() <Macros:Functions:getExposedTokenNames>`__
to create a `string list <Macros:string_list>`__ containing the token
names of all tokens that are not hidden by `fog of
war <Map:fog_of_war>`__, and assigning the output of
getExposedTokenNames() to the variable *tokenList*.

The variable *imgList* is also assigned the value of *tokenList*,
because for this macro to work, we will be working with a copy of the
originally generated list of token names (this copy will be altered to
include token images, but the original will be left alone). The
variables *tokenList* and *imgList* now contain:

.. _variable_values:

Variable Values
~~~~~~~~~~~~~~~

========== ========= =======
list index tokenList imgList
========== ========= =======
0          Token 1   Token 1
1          Token 2   Token 3
2          Token 3   Token 3
3          Token 4   Token 4
========== ========= =======

.. _modify_imglist_to_contain_token_images:

Modify *imgList* to Contain Token Images
----------------------------------------

.. code:: mtmacro
   :number-lines:

   [H: Num = listCount(imgList)]

   [h,COUNT(Num),CODE:
   {
   [h:tokenName=listGet(imgList,roll.count)]
   [h,token(tokenName): image=getTokenImage()]
   [h:imgList=listReplace(imgList,roll.count,tokenName+" "+image)]
   }]

The first line in this segment uses the
`listCount() <Macros:Functions:listCount>`__ function to get the number
of entries in *imgList*. Following that, a
`[COUNT(): <Macros:Branching_and_Looping>`__] roll option is used along
with the `CODE:{ } <Macros:Branching_and_Looping>`__ option to execute
the three commands for each entry in the *imgList*. The code in lines
5-7 do the following:

-  Line 5 uses `listGet() <Macros:Functions:listGet>`__ to get the value
   of the entry in *imgList* with the index *roll.count* (in other
   words, for the first loop, *roll.count* is 0; thus, listGet()
   retrieves entry 0 in *imgList*). The value returned is assigned to
   the variable *tokenName*.
-  Line 6 uses the `[token(): <Macros:Branching_and_Looping>`__] roll
   option to execute the function
   `getTokenImage() <Macros:Functions:getTokenImage>`__ against the
   token identified in line 5. The result of this line of code is to
   obtain the image asset URL of the token's image and assign that value
   to the variable *image* (image asset URLs are internal MapTool
   identifiers that point to the location of a specific image (be it a
   map, a state, or a token image).
-  Line 7 then modifies *imgList* using
   `listReplace() <Macros:Functions:listReplace>`__ to replace the
   current entry in *imgList* with a new entry composed of the token
   name and the token's image (in other words, each line in *imgList*
   contains both a name and an asset URL).

Variables
~~~~~~~~~

========== ========= ================================================
list index tokenList imgList
========== ========= ================================================
0          Token 1   Token 1 asset://7bc4e037058d908a6bdbe7ba172f0729
1          Token 2   Token 3 asset://7bc4e037058d908a6bdbe7ba172f0729
2          Token 3   Token 3 asset://a78f12b8d3df1b2e660dfa95b8a92cf1
3          Token 4   Token 4 asset://a78f12b8d3df1b2e660dfa95b8a92cf1
========== ========= ================================================

.. _create_input_dialog:

Create Input Dialog
-------------------

.. code:: mtmacro
   :number-lines:

   [h:status=input(
           "Target|"+imgList+"|Select Target|LIST|SELECT=0 ICON=TRUE ICONSIZE=30",
           "newName| |Enter a new name for this token"
   )]
   [h:abort(status)]

This segment uses the value in *imgList* in conjunction with the
`input() <Macros:Functions:input>`__ function to present a dialog with a
drop-down list showing both token names and token images.

You will note that the ICON and ICONSIZE options are set for the LIST
input control - this allows the images to be displayed within the list.
If you don't set this, you'll see the image asset URL instead.

.. _process_input_from_user:

Process Input From User
-----------------------

.. code:: mtmacro
   :number-lines:


   [h:targetName = listGet(tokenList,Target)]

   [h:switchToken(targetName)]

   [h:token.name=newName]
   The token's name has been changed to <i>[r:newName]</i>.

For the purposes of this tutorial, the end result of the macro is simply
to change the token name of the token selected in the drop-down list.
This sequence of code does three things.:

#. Since we can't use the *imgList* variable to get the token name by
   itself (because that list also contains the image asset URL!), we
   instead return to the original *tokenList* variable (this is why we
   have two lists!). We retrieve the selected token's name via the
   `listGet() <Macros:Functions:listGet>`__ function, telling it to look
   in the list *tokenList* for the item with the corresponding index.

   #. We can do this because even though we added the image asset URL to
      *imgList*, we didn't change the order of anything - so the first
      entry in each list still points to the same token, and we can rest
      assured that if we know from *imgList* that Token 1 is the first
      item in *imgList* (in programming terms, it has index 0), then we
      know Token 1 is also the first item in *tokenList*.

#. We then use the `switchToken() <Macros:Functions:switchToken>`__
   function to change the "focus" of all subsequent macro commands to
   the token selected by the user.
#. The final two lines change the token name to the value entered by the
   user, and outputs a message to chat confirming the change.

Comments
========

There is not currently a function available that will sort a string
list, so the order in which tokens appear in the lists will not be in
any particular order. This can be rather frustrating.

`Category:Tutorial <Category:Tutorial>`__

.. |Tutorial-names-and-images.jpg| image:: Tutorial-names-and-images.jpg
