=================================
Speed Up Your Macros - MapToolDoc
=================================

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

   .. rubric:: Speed Up Your Macros
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

         .. container:: template_advanced

            ADVANCED
            THIS IS AN ADVANCED ARTICLE

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Introduction <#Introduction>`__
            -  `2 Do it yourself <#Do_it_yourself>`__
            -  `3 Macro vs UDF vs
               directly <#Macro_vs_UDF_vs_directly>`__
            -  `4 Storing and Retrieving
               Variables <#Storing_and_Retrieving_Variables>`__
            -  `5 Storing and Retrieving Variables
               II <#Storing_and_Retrieving_Variables_II>`__
            -  `6 Token(), GetProperty() and
               switchToken() <#Token.28.29.2C_GetProperty.28.29_and_switchToken.28.29>`__
            -  `7 jsons <#jsons>`__
            -  `8 jsons object vs json array vs
               lists <#jsons_object_vs_json_array_vs_lists>`__
            -  `9 functions <#functions>`__

               -  `9.1 Nested functions <#Nested_functions>`__
               -  `9.2 Loop speeds <#Loop_speeds>`__

            -  `10 macros <#macros>`__
            -  `11 eval vs evalMacro <#eval_vs_evalMacro>`__
            -  `12 Tokens <#Tokens>`__
            -  `13 <!-- Comments --> <#.3C.21--_Comments_--.3E>`__
            -  `14 To [h: or not to [h: <#To_.5Bh:_or_not_to_.5Bh:>`__
            -  `15 if(): or if(,,) <#if.28.29:_or_if.28.2C.2C.29>`__
            -  `16 if(x<0,0,x) or
               max(0,x) <#if.28x.3C0.2C0.2Cx.29_or_max.280.2Cx.29>`__
            -  `17 String concatenation, strformat, add, concat and
               + <#String_concatenation.2C_strformat.2C_add.2C_concat_and_.2B>`__
            -  `18 Assign Function result to Variable first or not
               (before multiple
               use) <#Assign_Function_result_to_Variable_first_or_not_.28before_multiple_use.29>`__

         .. rubric:: Introduction
            :name: introduction

         If you start creating your own framework and if you like the
         process, then most likely you will get to a point that some of
         your more advanced macros start to become a drag. MT script
         isn't the fastest of languages and there are a couple of
         functions or methods that can really slow things down.
         Fortunately a couple of users (like Aliasmask) have started
         testing different methods to speed up their code. Below you can
         find the results, some tips are based on conjecture others have
         been throughly tested to be faster. I you find a new faster
         method, don't hesitate to put it here.

         .. rubric:: Do it yourself
            :name: do-it-yourself

         Recently I've added a new function to the `Bag of
         Tricks <http://forums.rptools.net/viewtopic.php?f=46&t=16066>`__
         called Benchmark. This function can be found in the Setup tab
         of the virtual menu. On lib:EventMacros there is a group called
         'Benchmark Macros' with one macro called 'Default' which should
         be empty. In this group you can create new macros. When you hit
         'Benchmark' then the execution time of these macros will be
         calculated. The Default macro is used as reference and that
         execution time is deducted so the actual execution time of your
         added macros remains. The result is shown in the chat. If add
         one macro you will be presented with the execution time of that
         macro on that PC. If you add more then one macros then a
         comparison report is shown as well so you can get a feeling of
         which methods is faster.

         This way you can run your own tests by simply adding your code
         to that group and running the Benchmark Macro. In the latest
         lib:EventMacros you can find two example macros 'if roll
         option' and 'if function' to show you how it works.

         .. rubric:: Macro vs UDF vs directly
            :name: macro-vs-udf-vs-directly

         | This is again something to take into consideration. Sometimes
           you need to split up macro because of the ``CODE`` nesting
           limit, sometimes to prevent stack overflow and sometimes
           cause its easier. Here's the impact of your choices:

         I've tested the macro:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                     [r:"Test"]

         in three ways. Once directly, once through a User Defined
         Functions (UDF) ``Test()`` and once through the macro call
         ``"Test"``:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                     [r:"Test"]
                     [r:Test()]
                     [r,macro("Test@lib:cifStopwatch"):""]
                     [r:eval("Test()")]

         The result is (with 10,000 cycles): directly 8.5 seconds, UDF
         14.3s, Macro 18.5 and Eval 15.4 seconds. In short, if speed is
         of the essence, try to keep it into one macro. If you need to
         split up: use UDF as much as possible. If you feed it one
         variable (argument) then the total time for both the UDF and
         the macro increases with 1 second.

         .. rubric:: Storing and Retrieving Variables
            :name: storing-and-retrieving-variables

         You can store a variable in three ways:

         -  on a token using
            `setProperty() </rptools/wiki/setProperty>`__
         -  on a lib:token using
            `setLibProperty() </rptools/wiki/setLibProperty>`__
         -  on one of the tokens identifiers (``token.name``,
            ``token.gm_name``, ``token.label``)

         The fastest method to **retrieve** a simple value is from the
         identifiers. If the time to retrieve a value from an identifier
         takes 1 second then the same value takes (on average) 1.2
         seconds using
         `getLibProperty() </rptools/wiki/getLibProperty>`__ and 1.8
         seconds using `getProperty() </rptools/wiki/getProperty>`__.
         The same test but using a heavy json object: if we set the
         identifier again on 1 (still the fastest) we notice that:
         `getLibProperty() </rptools/wiki/getLibProperty>`__ is still
         1.2 however `getProperty() </rptools/wiki/getProperty>`__ time
         has increased to 2.8 seconds. The json used was constructed out
         of 1000 identifiers. And the time average was taken over 10,000
         loops.

         Now the surprising part: To **set** a value one would expect
         similar results but that ain't the case. Using the same heavy
         json it turns out that ``token.gm_name`` was the fastest and
         ``token.label`` the slowest !!! If ``gm_name`` is set to 1
         second than the rest is: 2 seconds for both
         `setProperty() </rptools/wiki/setProperty>`__ and
         `setLibProperty() </rptools/wiki/setLibProperty>`__ (yes equal
         speed) and 2.4 seconds for ``token.label``. Again 10,000 loops
         used to test.

         I've ran more test, to see which method is faster to store
         multiple simple variables onto a libtoken and retrieving them
         again:

         -  Using json
         -  Using strProps list
         -  Each variable seperately.

         The last method is by far the slowest (10x the time for the
         other methods). Using json or strProps does not really make a
         lot of difference though strProps are faster. What I tested:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                      [testJson = json.set("{}", "test0",test0,"test1",test1,"test2",test2,...,"test9",test9)]
                      [testJson = json.fromStrProp(strPropFromVars("test0,test1,test2,...,test9","UNSUFFIXED"))]
                      [testStrProp = strPropFromVars("test0,test1,test2,...,test9","UNSUFFIXED")]

         I also tried the strFormat trick (though the I could not
         properly retrieve the json object form the lib with this
         method:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                      [testJson = strformat('{"test0":"%{test0}","test1":"%{test1}","test2":"%{test2}",...,"test9":"%{test9}"}')]
                      [testStrProp = strformat('test0=%{test0};test1=%{test1}...;test9=%{test9}')]

         Of these 5 methods the
         `strPropFromVars() </rptools/wiki/strPropFromVars>`__ and the
         `strformat() </rptools/wiki/strformat>`__ methods were the
         fastest: 9.1 seconds (10,000 cycles) and
         `json.set() </rptools/wiki/json.set>`__ the slowest 13.1s. The
         `json.fromStrProp() </rptools/wiki/json.fromStrProp>`__ was
         slightly only slower 9.6s.

         Retrieving the data showed roughly the same result, strProps
         are a bit faster:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                      [result = getLibProperty("testJson","lib:OntokenMove")]
                      [varsFromStrProp(json.toStrProp(result))]
                      [result = getLibProperty("testStrProp","lib:OntokenMove")]
                      [varsFromStrProp(result)]

         Using another method to retrieve the json vars e.g.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                      [foreach(item, result):set(item, eval(item))]

         is considerably slower.

         Another thing that is interesting is that using the above
         `varsFromStrProp() </rptools/wiki/varsFromStrProp>`__ and
         `strPropFromVars() </rptools/wiki/strPropFromVars>`__ it hardly
         matter how many variables you set. I've tested this with
         setting 2 and 100 variables in one go. It turned out that
         `strPropFromVars() </rptools/wiki/strPropFromVars>`__ took 4x
         longer (4ms to set 100 vars vs 1 ms to set 2) and
         `varsFromStrProp() </rptools/wiki/varsFromStrProp>`__ was
         equally fast for both 2 and 100! (ok a very small difference, 2
         takes 0.9ms and 100 take 1.1ms). This was tested again with
         10,000 cycles (I divided the results by 1,000 to get to the
         ms).

         .. rubric:: Storing and Retrieving Variables II
            :name: storing-and-retrieving-variables-ii

         I've noticed that storing a LOT of properties on a token
         influences the set get-property method in a negative way. This
         I wanted to quantify.

         Keep in mind, this is quite a bit technical and mainly shows
         the effect of storing a certain amount of data on a token in an
         absolute sense. This was tested on an average PC

         First test: setProperty() x1,x2,...x10000 to the value 10 and
         then immediately retrieving it (getProperty())

         Result: no time difference between the first and the last set
         value.

         Second test: changing the variable to a 26+ characters and the
         value to 260 characters. The total get/set time increased a
         bit, but again not changes whether is was value 1 or 1000.

         Third test, same as the second, but now I raised the cap to
         10,000. Finally we see something. The initial get/set time is
         30,5 ms (averaged over the first 100 samples). The last 100
         (average) took 130 ms !!

         It turned out that with these variables and values that there
         was no change for the first 1000 variables and around 1200 a
         linear increase started of roughly +8ms per 2000 variables.
         Around 9200 an exponential increase started. Variable 9176 took
         96ms and variable 9290 took 118ms. Finally point 10,000 took
         130ms (note that the times are averaged over the last 1000). If
         you look at the individual results then its interesting to note
         that the last 100 points generally took 100ms but every 14th
         variable took nearly 5x as long (475 ms).
         |getsetpropertiesTime.jpg|

         Next test was increasing the length of the variable (so not the
         value). Starting with 'i', 'i1', 'i12', etc upto
         'i1234....1000'. This remained at 21ms per get set 21
         variables, after that a pretty steep linear increase of 40 ms
         extra for the 10000 variant. (20 took 20ms and 1000 took 60ms.)

         Fourth test was increasing the length of the value, with the
         same method as directly above. This resulted in two linear
         increases with the break at 400. In short the increase from 1
         to 400 characters is 22 to 28 ms (1.25ms increase per 100).
         While from 400 to 800 is 28 to 46 ms (4.5 increase per 100).
         Here I was still using a new property name for each variable.
         Which means that the previous variables also stored on the
         token will also influence the time.

         In the final test I simply increased the length of the value
         with the same method as above, so this gives insight in the
         actual length of the value. Surprisingly this made hardly any
         difference. The increase from 1 to 10,000 characters was about
         2ms. Which raises the question: when \*does\* it go wrong. So I
         bench-marked (in a 1000 test loop) writing and reading
         1,10,100,1000,10000 and 100000 characters. For 1 to 1000 its
         roughly the same, after that it doubles for 10,000 and 100,000
         is about **87x**\ *Italic text* slower!!. Further testing
         (taking inbetween points) shows that its an exponential of
         1.54. If you would assume that a processing time of 100ms (0.1
         second) is acceptable, then you're at 50,000 characters.

         .. rubric:: Token(), GetProperty() and switchToken()
            :name: token-getproperty-and-switchtoken

         When you need to retrieve a property from a token that is not
         `currentToken() </rptools/wiki/currentToken>`__ these are the
         three methods to get it. Now there are quite a lot of ways of
         how to use these and even combinations of these. I've ran two
         tests both tests with different approaches. The first test I
         retrieved 1 value, ``"Dexterity"``, which contains a long (150
         char.) string value:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                    [tmp = getProperty("Dexterity", "Eagle")]              0.9ms
                    [token("Eagle"): tmp = getProperty("Dexterity")]       1.3ms
                    [switchToken("Eagle")][tmp = getProperty("Dexterity")] 1.3ms
                    [token("Eagle"): tmp = Dexterity]                      1.3ms
                    [switchToken("Eagle")][tmp = Dexterity]                1.3ms

         In the second test I ran the same macros, but now I executed
         the above lines 10 times, but it turned out they were all
         equally fast with the exception of [token("Eagle"): tmp =
         getProperty("Dexterity")] which was about 50% slower then the
         rest. So I've upped the number to 50x:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                    [tmp = getProperty("Dexterity", "Eagle")]                    50x 18ms
                    [token("Eagle"): tmp = getProperty("Dexterity")]             50x 29ms
                    added:
                    [token("Eagle"), CODE:{  [tmp = getProperty("Dexterity")] 50x }] 18ms
                    [switchToken("Eagle")] 1x   [tmp = getProperty("Dexterity")] 50x 18ms
                    [token("Eagle"), CODE:{ [tmp = Dexterity] 50x }]                 17ms
                    [switchToken("Eagle")] 1x [tmp = Dexterity]                  50x 16ms

         If you take into account minor fluctuations of my pc then again
         you can only say something of the second line, which apparently
         is the slowest, the rest is (surprisingly) still equally fast.

         Fortunately I have a humongous json structure lying around
         (9,000 key value pairs and 175,000 characters) so I tried that
         one, only realizing after 10 minutes or so that calling such an
         object say 300,000 times might not be the smartest thing... so
         after rebooting my pc I tried again, this time first 1 (=300
         times retrieving the object which took 14 seconds) and then 10x
         (137 seconds, its always nice if its scales along a straight
         line). This only made things even more confusing:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                    [tmp = getProperty("Dexterity", "Eagle")]                    50x 2s
                    [token("Eagle"): tmp = getProperty("Dexterity")]             50x 2s
                    [token("Eagle"), CODE:{  [tmp = getProperty("Dexterity")] 50x }] 2s
                    [switchToken("Eagle")] 1x   [tmp = getProperty("Dexterity")] 50x 2s
                    [token("Eagle"), CODE:{ [tmp = Dexterity] 50x }]                 1.8s
                    [switchToken("Eagle")] 1x [tmp = Dexterity]                  50x 1.6s
                    added:
                    [switchToken("Eagle")] 1x [tmp = Dexterity] 1x [tmp1 = tmp]  50x 1.6s

         I think the conclusions you can derive from this are:

         -  Don't do ``[token(tokID): var = getProperty(property)]``,
            either use ``[var = getProperty(property,tokID)]`` or
            ``[token(tokID): var = property]``.
         -  If you need only a few properties of a token use
            ``getPropety(property, tokID)``.
         -  If you need a lot of properties use
            `switchToken() </rptools/wiki/switchToken>`__ and then
            access the vars straight away.
         -  If you use `switchToken() </rptools/wiki/switchToken>`__ and
            then assign the property to a local var, or you just keep
            using the property straightaway, makes no difference
            (although in the latter you might inadvertently change the
            property).

         .. rubric:: jsons
            :name: jsons

         -  Try to avoid nested json objects (so json object within a
            json object). Objects within a json array is likely better.
         -  When storing a json as a property on a token, try to limit
            the ``get/setproperty``. Do it once, store it in a local
            variable and pass it along also into submacros. This also
            accounts if you're changing a property directly (so without
            ``get/setproperty``) e.g.:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- this (using get/setPropery) -->

               #. .. code-block:: none

                     [HP = getProperty(tokenName, Hitpoints)]

               #. .. code-block:: none

                     [HP = HP-1]

               #. .. code-block:: none

                     [setProperty(tokenNam, HP)]

               #. .. code:: de2

                     <!--is the same as this (changing property directly)-->

               #. .. code-block:: none

                     [Hitpoints = Hitpoints - 1]

         -  It might be the case that converting (using
            `encode() </rptools/wiki/encode>`__) a json to string and
            then storing it on a token. Retrieving it using
            `decode() </rptools/wiki/decode>`__.
         -  If you want to store a huge and complex json variable
            temporarily on a token, don't use a property but use
            ``token.gm_name`` (or ``token.label`` or ``token.name``) to
            store it (using a lib token for that). It goes without
            saying that this is a bit a of an extreme method, i.o.w. a
            hack. If you were to e.g. use the ``token.name`` variable on
            a lib token, interesting (that you don't want) stuff will
            happen.
         -  Overall keep in mind that read/write operations will get
            slower with the length of the json object. With extremely
            large json objects the read/write speed can bog down to 1 or
            more seconds per operation.

         .. rubric:: jsons object vs json array vs lists
            :name: jsons-object-vs-json-array-vs-lists

         | For **simple** operations:

         ::

             slower ------------------------------------------------------> faster 

             json object operations  --> json array operations --> list operations 

         | The operations were building the structure and retrieving all
           values. The speed differences are significant!!!
         | These test were done by comparing getting and setting 1000 x
           and y coordinates:

         -  1 list with x items, with every item being a list with y
            items, using different separator:
            ``"1,2,3,..; 1,2,3,..; 1,2,3,.."``
         -  1 array with x items, where every items contains y items:
            ``[[1,2,3,...],[1,2,3,...],[1,2,3,...], etc]``
         -  1 json containing x*y keys:
            ``{"x1y1":{"x":1,"y":1}, "x1y2":{"x":1,"y":2}, etc}``

         Obviously there are situations where a json object or array
         will be faster just because its smarter coding or much easier
         to use them. So only give value to this test if you want to do
         something similar as done with this test.

         .. rubric:: functions
            :name: functions

         .. rubric:: Nested functions
            :name: nested-functions

         It seems I had it wrong before. I had it from hearsay, now I've
         benchmarked it myself. Nested is much faster then unnested.
         First I tried one nested function vs unnested for 10,000 cycles
         the result was 10s for nested and 15s for unnested. Then next
         test I ran a really nested function:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                      [varsFromStrProp(json.toStrProp(json.fromStrProp(strPropFromVars(theList,"UNSUFFIXED")))]

         vs unnested

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                      [tmp = strPropFromVars(theList,"UNSUFFIXED")]
                      [testJson = json.fromStrProp(tmp)]
                      [tmp1  = json.toStrProp(testJson)]
                      [varsFromStrProp(tmp1)]

         Running both 10,000 times resulted in: Nested **14**\ s and
         Unnested **31**\ s. It might not help the readability of you
         code, but nesting your functions **can be more then twice as
         fast**!!!

         .. rubric:: Loop speeds
            :name: loop-speeds

         | The following loops:
         | `[count():] </rptools/wiki/count_(roll_option)>`__
         | `[for():] </rptools/wiki/for_(roll_option)>`__
         | `[foreach():] </rptools/wiki/foreach_(roll_option)>`__
         | take exactly the same amount of time to roll a 1d100 10000
           times. In other words, they're equally fast.

         -  CIF's stopwatch was used to measure this

         This means that you can and should use the right loop function
         for the right reason. Some examples of good use: Some examples
         of proper use:

         -  use `[foreach():] </rptools/wiki/foreach_(roll_option)>`__
            to loop through a list or json array
         -  use ``count(n)`` if you want to execute a routine n times
         -  use ``for(i, n, 0, -2)`` if you want to use an a-typical but
            regular countdown from ``n`` to ``0``, using ``i`` in your
            routine.

         .. rubric:: macros
            :name: macros

         When getting arguments within a UDF (user defined function):

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!-- Slow -->

               #. .. code-block:: none

                     [h: var1 = json.get(macro.args,0)]

               #. .. code-block:: none

                     [h: var2 = json.get(macro.args,1)]

               #. .. code-block:: none

                     <!-- Faster -->

               #. .. code:: de2

                     [h: var1 = arg(0)]

               #. .. code-block:: none

                     [h: var2 = arg(1)]

         **Notes:**

         -  If you use the
            `[macro():] </rptools/wiki/macro_(roll_option)>`__ function
            you can only make use of the ``macro.args`` method (the slow
            way).
         -  This method doesn't work the other way around, if you set
            ``macro.return`` within a UDF you cannot use ``arg(0)`` from
            within the function you called the UDF from. E.g.;

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     <!--after calling some UDF:-->

               #. .. code-block:: none

                     [h: doSomething(var)]

               #. .. code-block:: none

                     <!--this works-->

               #. .. code-block:: none

                     resultOfDoSomething = macro.return

               #. .. code:: de2

                     <!--this won't-->

               #. .. code-block:: none

                     [resultOfDoSomething = arg(0)]

               #. .. code-block:: none

                     <!--actually most likely it will 'work' but it won't contain the value you want -->

         .. rubric:: eval vs evalMacro
            :name: eval-vs-evalmacro

         Test `eval() </rptools/wiki/eval>`__ vs
         `evalMacro() </rptools/wiki/evalMacro>`__. Used the following
         two functions:

         ::

             [h:eval("table('tbl_Image',2)")]

         and

         ::

             [h:evalMacro("[table('tbl_Image',2)]")]

         not quite surprising result: eval was twice as fast as
         evalMacro. Actual execution times: eval: 0.8 ms evalMacro: 1.6
         ms

         Tested other things as well e.g. "2+2", which resulted in
         roughly the same times.

         Basically they're both very fast so it doesn't really matter
         which you use. However as soon as you start a loop using this
         then it might get relevant!

         .. rubric:: Tokens
            :name: tokens

         Though this isn't really about macros, it *is* about speed.
         What you put in your tokens will also effect the snappiness of
         the game play.

         -  Having a lot (guesstimation >100) of macrobuttons on a token
            will influence dragging it on the map (slow it down). Note:
            this issue has been partially fixed in MT by Rumble around
            b70-75. It still has impact on speed, but not, by a long
            shot, as much as it used to be.
         -  Having a token with lots of data stored on it, will effect
            the update of movement of a token on other pc's connected to
            the server.
         -  Large image on a token will also influence speed, try to
            keep them at 200x200 pixels or lower.
         -  Finally having a LOT of data on the token will influence the
            write speed for ALL properties. here a test result:

         ::

             setProperty on empty token        took 2.4 ms
             setProperty on 'lots of data token'    took 82 ms
             getProperty on empty token         took 2 ms
             getProperty on 'lots of data token'    took 2 ms

         .. rubric:: <!-- Comments -->
            :name: comments---

         There are two ways to put comment in MT script:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                    <!-- this is open comment -->

         Note the space ``" "`` after ``'<!--'``. This is essential or
         it won't be seen as comment. Or:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                    [H:'<!-- this is hidden comment -->']

         Note the quotes ``' '`` at the beginning and end, again you get
         errors if you forget them.

         These two methods both have a big pro and a big con. The open
         comment is processed very fast. On a moderately fast pc it
         takes about 100 ms to process 10,000 lines (100 ms is the
         border time you start to notice in macro execution). In short
         you can use these freely. Do keep in mind, though, that if you
         put comment in a e.g. ``count(1000):`` loop, then this adds
         1000 lines of comment to your code! The big con of the open
         comment however is stack. I've benchmarked this as well and it
         turns out to be completely system dependent, but I noticed that
         the text of about half a page of a book, ported straight to the
         chat, will render a stack overflow with a stack set to 5!!!
         That is not a lot of text. The best method to omit this issue
         is by setting the output of the macro standard to ``0`` in the
         UDF and use ``macro.return = result`` at the end. Another
         method is by making sure that at least all your loops are
         hidden ``[h,foreach(),CODE:{}]`` so all the comment you put
         inside can be open.

         The hidden comment thus has the big advantage that it does not
         add to the stack and the chances of a stack overflow are a lot
         less. However the big drawback is that its *relatively* slow.
         Mind you its still pretty fast, on (again a moderately fast pc)
         it takes 4 ms to execute, which means that it gets noticeable
         after around 250 lines. If however you keep slower systems in
         mind as well, this number might easily become half that!
         Another big advantage for the more experienced coder among use:
         if you use the console to check the running code
         ``[h:'<!-- -->']`` shows up, ``<!-- -->`` doesnt! So to track
         which routine is currently active I always start my macros with
         ``[h:'<!-- macro name -->']``.

         What I personally do is use ``[h:'<!-- -->']`` outside any
         loops and ``if()``,\ ``CODE`` statements and ``<!-- -->``
         inside these loops and ``if`` statements. I obviously make sure
         that these routines are all hidden.

         `Here <http://forums.rptools.net/viewtopic.php?f=20&t=20298&hilit=benchmark>`__
         a more in depth discussion on the subject.

         .. rubric:: To [h: or not to [h:
            :name: to-h-or-not-to-h

         In a routine like e.g.:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                    [h,count(100), CODE:{
                      some code
                    }]

         you can put in ``[h:some code]`` or ``[some code]`` which to
         the end result would make no difference. It turns out that no
         discernible difference between the two.

         .. rubric:: if(): or if(,,)
            :name: if-or-if

         There is the `if() </rptools/wiki/if>`__ and
         `[if():] </rptools/wiki/if_(roll_option)>`__. A simple test:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                    [tmp = if(1,1,0)]
                    [if(1): tmp = 1, tmp = 0]

         Resulted in the `[if():] </rptools/wiki/if_(roll_option)>`__ to
         be twice as slow. Although this is only 0.5 ms. Essentially
         they are both very fast. The `if() </rptools/wiki/if>`__ takes
         about 0.5 ms and the
         `[if():] </rptools/wiki/if_(roll_option)>`__ 0.9 ms. Do keep in
         mind that in the `if() </rptools/wiki/if>`__ evaluates BOTH
         TRUE AND FALSE and `[if():] </rptools/wiki/if_(roll_option)>`__
         only true OR false. So if you have a rather complex operation
         for the true and or false you might be faster of with
         `[if():] </rptools/wiki/if_(roll_option)>`__.

         .. rubric:: if(x<0,0,x) or max(0,x)
            :name: ifx00x-or-max0x

         A comparison between `if() </rptools/wiki/if>`__ and
         `max() </rptools/wiki/max>`__, where x was randomized (between
         -5 and 5) Resulted in both functions being equally fast.
         `max() </rptools/wiki/max>`__ occasionally turned out to be
         slightly faster, but we're talking 0,08ms (==0,00008 seconds)
         which really is negligible.

         .. rubric:: String concatenation, strformat, add, concat and +
            :name: string-concatenation-strformat-add-concat-and

         The following lines of code were tested 10,000 times:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                      [strformat("%{var1}%{var2}%{var3}%{var4}%{var5}%{var6}%{var7}%{var8}%{var9}")]     1.9377ms
                      [strformat("%s%s%s%s%s%s%s%s%s", var1, var2, var3, var4, var5, var6, var7, var8, var9)]    2.0979ms
                      [concat(var1, var2, var3, var4, var5, var6, var7, var8, var9)]                2.0056ms
                      [add(var1, var2, var3, var4, var5, var6, var7, var8, var9)]               2.018ms
                      [var1 + var2 + var3 + var4 + var5 + var6 + var7 + var8 + var9]               1.9944ms

         The realistic conclusion is that THEY ARE ALL EQUALLY FAST !!
         Looking at it at a more 'anal retentive' point of view:
         `strformat() </rptools/wiki/strformat>`__ is both the fastest
         and the slowest. This you start to notice when you have more
         then 600 lines of this type of code in one macro!! A second
         test made `add() </rptools/wiki/add>`__ the fastest, so there's
         also some marginal error...boiling down to the realistic fact
         that there is no difference!

         Of course, as is the general belief, you'll notice the real
         speed difference when using functions... so I tested that as
         well (different pc so different times, you can't derive
         anything between the speeds of test1 vs this test.):

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                      [h:var1 = getProperty("var1")]
                      [h:var2 = getProperty("var2")]
                      [h:var3 = getProperty("var3")]
                      [h:var4 = getProperty("var4")]
                      [h:var5 = getProperty("var5")]
                      [h:var6 = getProperty("var6")]
                      [h:var7 = getProperty("var7")]
                      [h:var8 = getProperty("var8")]
                      [h:var9 = getProperty("var9")]
                      [strformat("%{var1}%{var2}%{var3}%{var4}%{var5}%{var6}%{var7}%{var8}%{var9}")]
                   
                      [strformat("%s%s%s%s%s%s%s%s%s", getProperty("var1"), getProperty("var2"), getProperty("var3"), getProperty("var4"), getProperty("var5"), getProperty("var6"), getProperty("var7"), getProperty("var8"), getProperty("var9"))]
                   
                      [concat(getProperty("var1"), getProperty("var2"), getProperty("var3"), getProperty("var4"), getProperty("var5"), getProperty("var6"), getProperty("var7"), getProperty("var8"), getProperty("var9"))]
                   
                      [add(getProperty("var1"), getProperty("var2"), getProperty("var3"), getProperty("var4"), getProperty("var5"), getProperty("var6"), getProperty("var7"), getProperty("var8"), getProperty("var9"))]
                   
                      [getProperty("var1") + getProperty("var2") + getProperty("var3") + getProperty("var4") + getProperty("var5") + getProperty("var6") + getProperty("var7") + getProperty("var8") + getProperty("var9")]

         The respective times ('nothing' is an empty loop for
         reference):

         ::

             nothing count took            0.2203ms
             strformat("%{var1}%{var2}%{var3}etc")  3.5844ms
             strformat("%s%s etc", var1, var2, etc) 1.0036ms
             concat()               0.9629ms
             add()                  0.9591ms
             var1 + var2                0.9638ms

         The first `strformat() </rptools/wiki/strformat>`__ is
         obviously slower as the vars need to be defined each loop. So a
         bit more 'fair' is to move the ``[var1  = …][var2 = …] etc.``
         outside the first `strformat() </rptools/wiki/strformat>`__
         loop. If you do that and rerun then you get:

         ::

             strformat("%{var1}%{var2}%{var3}etc") 0.8833ms
             strformat("%s%s etc", var1, var2, etc) 0.9929ms
             concat()               0.9565ms
             add()                  0.9524ms
             var1 + var2                0.9509ms

         And here we see again that
         `strformat() </rptools/wiki/strformat>`__ is both the slowest
         and the fastest, but the speed difference is so insignificant
         that I would certainly not start rewriting my code. If you
         happen to have one macro that has 10,000 lines (indeed: *ten
         thousand* lines) of the slowest type then rewriting it to
         fastest type would save you 1 second execution time. In short:
         not worth the effort.

         .. rubric:: Assign Function result to Variable first or not
            (before multiple use)
            :name: assign-function-result-to-variable-first-or-not-before-multiple-use

         Sometimes these tests surprises me, like in this case. Lets say
         you need to retrieve the same x position of a token multiple
         times, for example in a more complex macro. From a coding
         perspective its always faster to assign it to a variable first
         and then use it. However the benchmark told me something
         completely different:

         The test code:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                      [h:bot_startTime()]
                   
                      <!-- empty loop, so you can extract the exact time it takes for the operation alone -->
                      [h,count(1000): 0]
                      [h:loopTime = bot_subTime()]
                   
                      [h:Tx       = getTokenX()]
                      [h:Ty       = getTokenY()]
                      [h,count(1000): y = Tx + Ty]
                      variable assignment: [r:bot_formatTime(bot_subTime() - loopTime)]<br>
                   
                      [h,count(1000): y = getTokenX() + getTokenY()]
                      multiple function call: [r:bot_formatTime(bot_subTime() - loopTime)]

         which surprisingly resulted in:

         variable assignment: 0.112s multiple function call: 0.039s

         So using variables takes nearly 3x as long !! Keep in mind
         though that this is tested for a relatively simple function.
         Stuff like json.get() might render quite some different
         results. Which is why I pasted the entire code block here for
         future use. (The bot\_ functions can be found in the `Bag of
         Tricks <http://forums.rptools.net/viewtopic.php?f=46&t=16066>`__).

         | 

         --`Wolph42 </rptools/wiki/User:Wolph42>`__ 08:52, 12 August
         2010 (UTC)

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Speed_Up_Your_Macros&oldid=6271"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Advanced </rptools/wiki/Category:Advanced>`__
            -  `Cookbook </rptools/wiki/Category:Cookbook>`__

         --------------

         `Advanced </rptools/wiki/Category:Advanced>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__ >
         `Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: visualClear

.. container::
   :name: mw-navigation

   .. rubric:: Navigation menu
      :name: navigation-menu

   .. container::
      :name: mw-head

      .. container::
         :name: p-personal

         .. rubric:: Personal tools
            :name: p-personal-label

         -  `Log
            in </maptool/index.php?title=Special:UserLogin&returnto=Speed+Up+Your+Macros>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Speed_Up_Your_Macros>`__
            -  `Discussion </maptool/index.php?title=Talk:Speed_Up_Your_Macros&action=edit&redlink=1>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-variants

            .. rubric:: Variants\ ` <#>`__
               :name: p-variants-label

            .. container:: menu

      .. container::
         :name: right-navigation

         .. container:: vectorTabs
            :name: p-views

            .. rubric:: Views
               :name: p-views-label

            -  `Read </rptools/wiki/Speed_Up_Your_Macros>`__
            -  `View
               source </maptool/index.php?title=Speed_Up_Your_Macros&action=edit>`__
            -  `View
               history </maptool/index.php?title=Speed_Up_Your_Macros&action=history>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-cactions

            .. rubric:: More\ ` <#>`__
               :name: p-cactions-label

            .. container:: menu

         .. container::
            :name: p-search

            .. rubric:: Search
               :name: search

            .. container::
               :name: simpleSearch

   .. container::
      :name: mw-panel

      .. container::
         :name: p-logo

         ` </rptools/wiki/Main_Page>`__

      .. container:: portal
         :name: p-navigation

         .. rubric:: Navigation
            :name: p-navigation-label

         .. container:: body

            -  `Main page </rptools/wiki/Main_Page>`__
            -  `Random page </rptools/wiki/Special:Random>`__
            -  `Help <https://www.mediawiki.org/wiki/Special:MyLanguage/Help:Contents>`__

      .. container:: portal
         :name: p-Basic_Usage

         .. rubric:: Basic Usage
            :name: p-Basic_Usage-label

         .. container:: body

            -  `Tutorials </rptools/wiki/Category:Tutorial>`__
            -  `Chat Commands </rptools/wiki/Chat_Commands>`__
            -  `Dice Expressions </rptools/wiki/Dice_Expressions>`__
            -  `Glossary </rptools/wiki/Glossary>`__

      .. container:: portal
         :name: p-Macro_Reference

         .. rubric:: Macro Reference
            :name: p-Macro_Reference-label

         .. container:: body

            -  `List of
               Functions </rptools/wiki/Category:Macro_Function>`__
            -  `Roll Options </rptools/wiki/Category:Roll_Option>`__
            -  `Special
               Variables </rptools/wiki/Category:Special_Variable>`__
            -  `Macro Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: portal
         :name: p-Editors

         .. rubric:: Editors
            :name: p-Editors-label

         .. container:: body

            -  `Editor Discussion </rptools/wiki/Editor>`__
            -  `Recent Changes </rptools/wiki/Special:RecentChanges>`__

      .. container:: portal
         :name: p-tb

         .. rubric:: Tools
            :name: p-tb-label

         .. container:: body

            -  `What links
               here </rptools/wiki/Special:WhatLinksHere/Speed_Up_Your_Macros>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Speed_Up_Your_Macros>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Speed_Up_Your_Macros&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Speed_Up_Your_Macros&oldid=6271>`__
            -  `Page
               information </maptool/index.php?title=Speed_Up_Your_Macros&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 29 January 2014, at 09:18.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |getsetpropertiesTime.jpg| image:: /maptool/images/4/4b/getsetpropertiesTime.jpg
   :width: 586px
   :height: 365px
   :target: /rptools/wiki/File:getsetpropertiesTime.jpg
.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
