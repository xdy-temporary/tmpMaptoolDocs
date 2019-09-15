=================
math - MapToolDoc
=================

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

   .. rubric:: math
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 math() Function <#math.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__

                  -  `1.2.1 mod <#mod>`__
                  -  `1.2.2 pow <#pow>`__

         .. rubric:: math() Function
            :name: math-function

         .. container:: template_version

            • **Introduced in version 1.4.0.5**

         .. container:: template_description

            This is NOT a single MapTool function but a collection of
            math functions in MapTool. **Important Note**: All of these
            functions return a floating-point number (e.g.: \`3.0`).

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     Numbers:

               #. .. code-block:: none

                     [r:val = math.pi()]

               #. .. code-block:: none

                     [r:val = math.e()]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     Trigonomotry:

               #. .. code-block:: none

                     [r:val = math.acos(degrees)]

               #. .. code-block:: none

                     [r:val = math.acos_r(radians)]

               #. .. code-block:: none

                     [r:val = math.asin(degrees)]

               #. .. code-block:: none

                     [r:val = math.asin_r(radians)]

               #. .. code:: de2

                     [r:val = math.atan(degrees)]

               #. .. code-block:: none

                     [r:val = math.atan_r(radians)]

               #. .. code-block:: none

                     [r:val = math.atan2(degrees)]

               #. .. code-block:: none

                     [r:val = math.atan2_r(radians)]

               #. .. code-block:: none

                     [r:val = math.cos(degrees)]

               #. .. code:: de2

                     [r:val = math.cos_r(num)]

               #. .. code-block:: none

                     [r:val = math.sin(degrees)]

               #. .. code-block:: none

                     [r:val = math.sin_r(num)]

               #. .. code-block:: none

                     [r:val = math.tan(degrees)]

               #. .. code-block:: none

                     [r:val = math.tan_r(num)]

               #. .. code:: de2

                     [r:val = math.toDegrees(num)]

               #. .. code-block:: none

                     [r:val = math.toRadians(degrees)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     Power and root:

               #. .. code-block:: none

                     [r:val = math.sqrt(num)]

               #. .. code:: de2

                     [r:val = math.squareroot(num)]

               #. .. code-block:: none

                     [r:val = math.cbrt(num)]

               #. .. code-block:: none

                     [r:val = math.cuberoot(num)]

               #. .. code-block:: none

                     [r:val = math.pow(num1,num2)]

               #. .. code-block:: none

                      

               #. .. code:: de2

                     Logarithmic

               #. .. code-block:: none

                     [r:val = math.log(num)] (this is loge())

               #. .. code-block:: none

                     [r:val = math.log10(num)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     Pythagorean:

               #. .. code:: de2

                     [r:val = math.hypot(num1,num2)]

               #. .. code-block:: none

                     [r:val = math.hypotenuse(num1,num2)]

               #. .. code-block:: none

                      

               #. .. code-block:: none

                     Simple operations

               #. .. code-block:: none

                     [r:val = math.abs(num)]

               #. .. code:: de2

                     [r:val = math.ceil(num)]

               #. .. code-block:: none

                     [r:val = math.floor(num)]

               #. .. code-block:: none

                     [r:val = math.isEven(num)]

               #. .. code-block:: none

                     [r:val = math.isInt(num)]

               #. .. code-block:: none

                     [r:val = math.isOdd(num)]

               #. .. code:: de2

                     [r:val = math.max(num1, num2, num2, etc.)]

               #. .. code-block:: none

                     [r:val = math.min(num1, num2, num2, etc.)]

               #. .. code-block:: none

                     [r:val = math.mod(num1,num2)]

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            ====abs====

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:val =  math.abs(-3)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  2. .. code-block:: none

                        3.0

            .. rubric:: mod
               :name: mod

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:val =  math.mod(6,3)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  2. .. code-block:: none

                        0

            .. rubric:: pow
               :name: pow

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r:val =  math.pow(2,3)]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  2. .. code-block:: none

                        8.0

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=math&oldid=7132"

