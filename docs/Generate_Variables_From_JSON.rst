=========================================
Generate Variables From JSON - MapToolDoc
=========================================

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

   .. rubric:: Generate Variables From JSON
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

         When working with string properties, the
         `varsFromStrProp() </rptools/wiki/varsFromStrProp>`__ function
         is an automated way to generate variables from the keys within
         a string property. For example, if you have the following
         string property:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [prop = "name=Axe; damage=1d12; proficiency=2;"]

         You can use
         `varsFromStrProp() </rptools/wiki/varsFromStrProp>`__ to
         generate a variable for each key - in other words, using the
         function to generate a list of locally accessible variables
         ``name``, ``damage``, and ``proficiency``.

         There is no equivalent function for JSON objects. However, the
         following routine can be inserted into any macro to efficiently
         generate the variables in question.

         --------------

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h:varList=json.fields(testObj)]
                   
                  [h,foreach(var,varList),CODE:
                  {
                       [value = json.get(testObj,var)]
                       [set(var,value)]
                  }]

         --------------

         The variable ``testObj`` represents the JSON object that is fed
         into the routine. The variables generated will be available
         within the scope of the running macro (but not outside).

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Generate_Variables_From_JSON&oldid=3145"

