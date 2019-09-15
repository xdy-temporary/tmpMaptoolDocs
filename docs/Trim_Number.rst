========================
Trim Number - MapToolDoc
========================

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

   .. rubric:: Trim Number
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

         | **Requires MapTool 1.3b56**
         | The following is a user defined function that allows you to
           trim any trailing zeros from a floating point number(a number
           with decimal places). It also allows you to truncate the
           decimal places to a certain length and round any truncated
           decimal places in a certain direction.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     trimNumber(number)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     trimNumber(number, length)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     trimNumber(number, length, direction)

         **Parameters:**

         -  ``number`` - The number to be trimmed.
         -  ``length`` - How many decimal places the trimmed number
            should retain, defaults to ``10``.
         -  ``direction`` - A string containing the direction that any
            truncated decimals placed should be rounded it. Accepts
            ``"up"``, ``"u"``, ``"down"``, and ``"d"``, defaults to
            rounding to the nearest.

         .. rubric:: Macros
            :name: macros

         Place the following macros on the same library token(or on
         different library tokens if you're know what you're doing and
         what to change).

         --------------

         **onCampaignLoad**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [defineFunction("trimNumber", "trimNumber@this", 1)]

         --------------

         --------------

         **trimNumber**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [assert(argCount() != 0, "trimNumber() requires at least one parameter.")]
                  [assert(argCount() <= 3, "trimNumber() accepts a maximum of three parameters.")]
                  [NumberToTrim = arg(0)]
                  <!-- Set truncation depth -->
                  [if(argCount() >= 2), code:
                  {
                      [TruncationDepth = power(10, arg(1))]
                  };{
                      [TruncationDepth = power(10, 10)]
                  }]
                  <!-- Set rounding method -->
                  [if(argCount() == 3), code:
                  {
                      [RoundingMethod = substring(arg(2), 0 , 1)]
                  };{
                      [RoundingMethod = 0]
                  }]
                  <!-- Perform trim -->
                  [switch(RoundingMethod):
                      case "u": NumberToTrim = ceiling(NumberToTrim*TruncationDepth)/TruncationDepth;
                      case "d": NumberToTrim = floor(NumberToTrim*TruncationDepth)/TruncationDepth;
                      default: NumberToTrim = round(NumberToTrim*TruncationDepth)/TruncationDepth
                  ]
                  [macro.return = NumberToTrim]

         --------------

         .. rubric:: Examples
            :name: examples

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.125000)]

         Returns ``1.125``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.125000, 2)]

         Returns ``1.13``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.124000, 2)]

         Returns ``1.12``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.123000, 2, "up")]

         Returns ``1.13``

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: trimNumber(1.128000, 2, "down")]

         Returns ``1.12``

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Trim_Number&oldid=3355"

