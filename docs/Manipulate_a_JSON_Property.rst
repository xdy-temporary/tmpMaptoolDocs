=======================================
Manipulate a JSON Property - MapToolDoc
=======================================

.. contents::
   :depth: 3
..

.. container:: noprint
   :name: mw-page-base

.. container:: noprint
   :name: mw-head-base

.. container:: mw-body
   :name: content

   .. container:: mw-indicators

   .. rubric:: Manipulate a JSON Property
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. rubric:: How to manipulate a JSON property
            :name: how-to-manipulate-a-json-property

         .. rubric:: Example: jsonFilterArrObj() -- Filtering out
            objects from an array of objects
            :name: example-jsonfilterarrobj----filtering-out-objects-from-an-array-of-objects

         If you have an array of objects and want to filter that list
         given one of the elements in the object, this
         subroutine/callable macro **jsonFilterArrObj** will do the job.

         As an example, here is an array of creature data:

         JSON array of Creature objects

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [{

               #. .. code-block:: none

                         "name": "Umber Hulk",

               #. .. code-block:: none

                         "hd": 8,

               #. .. code-block:: none

                         "size": "Large",

               #. .. code:: de2

                         "reach": 10,

               #. .. code-block:: none

                         "str": 23,

               #. .. code-block:: none

                         "dex": 13,

               #. .. code-block:: none

                         "con": 19,

               #. .. code-block:: none

                         "mov": "20, burrow 20",

               #. .. code:: de2

                         "AC": "18/10/17",

               #. .. code-block:: none

                         "SpecialATK": "Confusing Gaze(Su)"

               #. .. code-block:: none

                     },

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                      

               #. .. code:: de2

                         "name": "Ogre",

               #. .. code-block:: none

                         "hd": 4,

               #. .. code-block:: none

                         "size": "Large",

               #. .. code-block:: none

                         "reach": 10,

               #. .. code-block:: none

                         "str": 21,

               #. .. code:: de2

                         "dex": 8,

               #. .. code-block:: none

                         "con": 15,

               #. .. code-block:: none

                         "mov": 30,

               #. .. code-block:: none

                         "AC": "16/8/17 Hide",

               #. .. code-block:: none

                         "SpecialATK": "NA"

               #. .. code:: de2

                     }]

         | 
         | If you want to shorten the list by filtering on various
           elements of the object, you can call the **jsonFilterArrObj**
           macro to return the filtered array of objects.

         To call the macro, setup the JSON parameter to pass like thus:

         **Calling Macro snippet** (Remove all Creatures that have more
         HitDice than the entered number)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- 

               #. .. code-block:: none

                     "hd" = Element I want to filter against for this example

               #. .. code-block:: none

                     jAll = JSON array of Creature objects

               #. .. code-block:: none

                     fHD = number I prompted for with an input() dialog, this is the value I am testing against

               #. .. code:: de2

                     -->

               #. .. code-block:: none

                      

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [H: jAll = "[]"]

               #. .. code-block:: none

                     [H, FOR(i,1,cntAll): jAll = json.append(jALL, json.set(table("Polymorph", i), "imageID", tableimage("Polymorph", i)))]

               #. .. code:: de2

                     [H: jAll = json.sort(jAll, "a")]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [H: tjF = json.append("[]", jAll)]

               #. .. code-block:: none

                     [H: tjF = json.append(tjF, "hd")]

               #. .. code-block:: none

                     [H: tjF = json.append(tjF, fHD)]

               #. .. code:: de2

                     [H: tjF = json.append(tjF, "<")]

               #. .. code-block:: none

                     [H, MACRO("jsonFilterArrObj@"+getMacroLocation()): tjF]

               #. .. code-block:: none

                     [H: jFiltered = macro.return]

               #. .. code-block:: none

                     [H: Assert(!(json.isEmpty(jFiltered)), "Polymorph: No choices available.", 0)]

               #. .. code-block:: none

                     [H: cntF = json.length(jFiltered)]

               #. .. code:: de2

                      

               #. .. code-block:: none

                     <!-- continue processing with the newly filtered array of objects -->

         | 
         | **jsonFilterArrObj**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- 

               #. .. code-block:: none

                     Filter out objects from an array of objects.

               #. .. code-block:: none

                     inputs (macro.args is a JSON array containing):

               #. .. code-block:: none

                       jAO = A JSON array of objects

               #. .. code:: de2

                       elem = The element to filter against

               #. .. code-block:: none

                       fDat = The data to compare against

               #. .. code-block:: none

                       fType = Filter comparison: >, <, ==, >=, <=, !=

               #. .. code-block:: none

                     output:

               #. .. code-block:: none

                       macro.return = jAOf (The array with the elements removed that met the criteria)

               #. .. code:: de2

                     -->

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [H: jAO = json.get(macro.args, 0)]

               #. .. code-block:: none

                     [H: elem = json.get(macro.args, 1)]

               #. .. code-block:: none

                     [H: fDat = json.get(macro.args, 2)]

               #. .. code:: de2

                     [H: fType = json.get(macro.args, 3)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [H: cntAll = json.length(jAO)]

               #. .. code-block:: none

                     [H: assert(cntAll, "Null Array so filter aborts.")]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     [H, for(i, cntAll - 1, -1, -1), CODE: {

               #. .. code-block:: none

                       [H: tDat = json.get(json.get(jAO, i), elem)]

               #. .. code-block:: none

                       [ bTest = eval("fDat"+fType+"tDat")]<br>

               #. .. code-block:: none

                       [H, IF(bTest): jAO = json.remove(jAO, i); ""]

               #. .. code-block:: none

                     }]

               #. .. code:: de2

                      

               #. .. code-block:: none

                     [H: macro.return = jAO]

         .. rubric:: Sorting JSON Objects Based on an Arbitrary Nested
            Value
            :name: sorting-json-objects-based-on-an-arbitrary-nested-value

         JSON Objects can contain an arbitrary number of keys and values
         (for which the value may itself be another JSON object). For
         example, a nested JSON object called "Monsters" might look like
         this:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                      "Troll":

               #. .. code-block:: none

                       {

               #. .. code-block:: none

                         "name":"Troll",

               #. .. code:: de2

                         "HD":4,

               #. .. code-block:: none

                         "HP":75

               #. .. code-block:: none

                       },

               #. .. code-block:: none

                      "Orc":

               #. .. code-block:: none

                       {

               #. .. code:: de2

                         "name":"Orc",

               #. .. code-block:: none

                         "HD":3,

               #. .. code-block:: none

                         "HP":22

               #. .. code-block:: none

                       }

               #. .. code-block:: none

                     }

         Note that each value in the key-value pairs in the above object
         is actually a complete JSON object in its own right.

         It is occasionally useful to be able to sort a JSON object that
         contains *other* JSON objects based on a value in one of the
         "sub-objects." For instance, if a JSON object exists that
         contains token names and distances to those tokens from a given
         point, one may want to sort the JSON so that the nearest
         objects are first, and the farthest are last.

         Or, using the above "Monsters" example, one may wish to sort it
         by **name**, or by **HP**, or by **HD**.

         The following macro routine is a generic method to sort JSON
         objects based on an arbitrary value within a nested object.

         **Assumptions**

         -  This macro requires the use of a JSON object supporting
            version of MapTool; it was written and tested in version
            1.3.b53.
         -  The macro is generic, and will run using any given JSON
            object conforming to the general "nested object" structure.
            In this case, a nested JSON object is created in the
            beginning so that there is a sample object to sort.
            **However**: this routine should be applicable to JSON
            arrays of objects as well - it would simply require using
            the index of the nested object rather than the nested
            object's key.
         -  It can be unclear which object is being discussed when you
            have multiply nested objects. In the following explanation,
            "nested object" will always refer to an object contained
            *within a larger JSON*. So, the larger object is
            **Monsters**, while **Troll** would be a *nested object.*

         **Macro Code and Discussion**

         Please see the `full macro
         code <Tutorials:Macros:JSONSortingFullCode>`__
         for the complete macro.

         **1. Create Sample Object**

         This sequence simply creates a sample object to practice
         sorting. In actual use, you may wish to pass an object as an
         argument, or pull an object from a token's properties, as
         necessary.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:troll = json.set("{}", "name", "Troll", "HD", 4, "HP", 75)]

               #. .. code-block:: none

                     [h:orc = json.set("{}", "name", "Orc", "HD", 3, "HP", 13)]

               #. .. code-block:: none

                     [h:goblin = json.set("{}", "name", "Goblin", "HD", 2, "HP", 6)]

               #. .. code-block:: none

                     [h:gnoll = json.set("{}", "name", "Gnoll", "HD", 3, "HP", 19)]

               #. .. code:: de2

                     [h:kobold=json.set("{}", "name", "Kobold", "HD", 1, "HP", 4)]

               #. .. code-block:: none

                     [h:monsters = json.set("{}", "Troll", troll, "Orc", orc, "Goblin", goblin, "Gnoll", gnoll, "Kobold", kobold)]

         **2. Request Sorting Key and Sort Direction from User**

         This section is also optional (and not useful if this macro
         will be used as a function/called macro), but for the example
         code it makes it easier to experiment with. This section uses
         `input() <input>`__ to gather user input, and
         `abort() <abort>`__ to halt processing if the
         user hits "Cancel." Finally, it uses an
         `IF(): <Macros:Branching_and_Looping#IF_Option>`__
         roll option to set a variable with a "friendly" indicator of
         sort direction, which will be used at the end in the final
         output.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:status = input(

               #. .. code-block:: none

                     "whichKey|name,HD,HP|Pick Sorting Key|LIST|SELECT=0 VALUE=STRING",

               #. .. code-block:: none

                     "whichDirection|A+,A-,N+,N-|Direction (A+/- for strings, N+/- for numbers!)|LIST|SELECT=0 VALUE=STRING"

               #. .. code-block:: none

                     )]

               #. .. code:: de2

                     [h:abort(status)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h,if(substring(whichDirection,1)=="+"): dirString = "ascending"; dirString = "descending"]

         **3. Set Basic Variables**

         This segment initializes some variables that will be used
         later:

         -  *sortObj* is the object to be sorted (in this case, the JSON
            Object **Monsters**)
         -  *sortOn* is the value on which to sort (**name**, **HD**, or
            **HP**)
         -  *sortDirection* is the direction of the sort, which will be
            passed to `listSort() <listSort>`__
         -  *sortObjContentList* is a list - created using
            `json.fields() <json.fields>`__ - of each
            nested object within **Monsters**; effectively it is a list
            of the "names" of each monster
         -  *keyList* is a list that will contain the value that
            corresponds to the thing we're sorting on - so if you choose
            to sort by **name**, then *keyList* will ultimately contain
            the value of **name** for each monster in the **Monsters**
            object
         -  *sortedJSON* will hold the new, nicely sorted JSON object;
            the original object will be unchanged.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h:sortObj=monsters]

               #. .. code-block:: none

                     [h:sortKey = whichKey]

               #. .. code-block:: none

                     [h:sortDirection = whichDirection]

               #. .. code-block:: none

                     [h:sortObjContentList = json.fields(sortObj)]

               #. .. code:: de2

                     [h:keyList = ""] 

               #. .. code-block:: none

                     [h:sortedJSON = "{}"]

         **4. Extract the Value of sortKey from each Nested Object**

         Here, we use FOREACH() to loop through each element in
         *sortObjContentList* (in other words, go one-by-one through the
         list of monster names). The FOREACH() option lets us say that
         *item* holds the value of each of those (so for the first pass,
         *item* holds the first monster name in the list, and on the
         second pass, it moves to the next, and so on). We need to do
         this so that we can extract the detailed information about each
         monsters from the **Monsters** object (in this case, we assign
         the detailed information to a new variable called
         *itemDetail*).

         With the nested objects extracted, we can then retrieve the
         value of the thing we're sorting on by using
         `json.get() <json.get>`__ on the variable
         *itemDetail*. We stick that value in the previously empty list
         *keyList*.

         Finally, once we've gone through each nested object held within
         **Monsters** and each nested object's value for our chosen sort
         (remember, we put that information in the variable *sortKey*)
         has been added to *keyList*, we're finished with the loop.

         Now we actually can determine what the right order will
         ultimately be - we sort *keyList* using
         `listSort() <listSort>`__ based on the direction
         specified by the user. **This is a critical step!** We've gone
         through each object, and figured out what the *value* of the
         thing we're sorting on is - so if we're sorting on "name",
         we've gone and actually retrieved each object's *name*, and put
         it in a list with the others. We then sort that list, which
         tells us the final order to use when we reassemble the main
         object!

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h,foreach(item, sortObjContentList),CODE:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                        [h:itemDetail = json.get(sortObj,item)]

               #. .. code-block:: none

                        [h: keyList = listAppend(keyList, json.get(itemDetail, sortKey))]

               #. .. code:: de2

                     }]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     [h:keyList = listSort(keyList, sortDirection)]

         **5. Iterating through keyList and Each Nested Object**

         This is the most complex part of the routine.
         `FOREACH(): <Macros:Branching_and_Looping#FOREACH_Option>`__
         through each element in the variable *keyList* (which, you will
         recall, contains the values corresponding to *sortKey* for each
         nested object). For *each* element in *keyList*, we then loop
         through *all* of the nested objects in **Monsters** to see
         which one(s) match up to the current element of *keyList*.

         So, for example, if the current value - *key* - in the outer
         loop is 4, and we are sorting by "HD", the inner loop will
         iterate through each nested object and check to see if the
         value of "HD" for that nested object is equal to 4.

         If a match is found, the matching nested object is added to
         *sortedJSON* using `json.set() <json.set>`__. In
         this fashion, we're using *keyList* to tell us what order the
         final nested objects should be in, and we then just need to go
         through our nested objects, setting them in that order via the
         following code.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h,foreach(key,keyList),CODE:

               #. .. code-block:: none

                     {

               #. .. code-block:: none

                        [foreach(object,sortObj),CODE:

               #. .. code-block:: none

                        {

               #. .. code:: de2

                          [objectDetail = json.get(sortObj,object)]

               #. .. code-block:: none

                          [h:sortOnValue = json.get(objectDetail, sortKey)]

               #. .. code-block:: none

                          [if(sortOnValue == key): sortedJSON=json.set(sortedJSON, object, objectDetail);""]

               #. .. code-block:: none

                        }]

               #. .. code-block:: none

                     }]

         **6. Outputting the Results in an Attractive Fashion**

         The final step is to output results. The use of
         `json.indent() <json.indent>`__ here simply makes
         the sorted JSON object easy to read.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     JSON Object sorted by [r:whichKey], [r:dirString]:<br>

               #. .. code-block:: none

                     <pre>[r:json.indent(sortedJSON, 3)]</pre>

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Manipulate_a_JSON_Property&oldid=3146"

