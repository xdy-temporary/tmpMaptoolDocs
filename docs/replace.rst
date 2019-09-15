====================
replace - MapToolDoc
====================

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

   .. rubric:: replace
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

         .. rubric:: replace() Function
            :name: replace-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the string with the occurrences of a pattern
            replaced by the specified value. If the number of times to
            perform the replacement is not specified then all
            occurrences of the pattern are replaced. Pattern can be a
            `regular
            expression <Macros:regular_expression>`__.
            This means if the pattern string contains any regular
            expression special characters they must be escaped.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     replace(str, pattern, value)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     replace(str, pattern, value, times)

         .. rubric:: Example
            :name: example

         .. container:: template_example

            **Example 1**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                            [r: replace("This is a test", " ", "-")]

                  #. .. code-block:: none

                            [r: replace("This is a test", " ", "-", 2)]

            Returns:

            ::

                  This-is-a-test
                  This-is-a test

            | **Example 2**
            | This is useful for search+replace of any string you feed
              to ``replace()`` that might have regex codes in it like
              parenthesis:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                            [r: tString = "is (a) t"]

                  #. .. code-block:: none

                            [r: replace("This is (a) test", "\\Q" + tString + "\\E", "-")]

            Returns:

            ::

                  This-est

            **Example 3**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                            [r: name = replace("wolph 5","(.*?) [0-9]+","\$1 42")]

            returns:

            ::

                  wolph 42

            The ``$`` normally means to match end-of-line, but only when
            it's at the end of the pattern. In this case, it's at the
            beginning of the pattern. And that means if the character
            immediately following is a digit (such as ``$1``), those
            characters are replaced by the source string matched by the
            corresponding set of parentheses in the regular expression.

            | **Example 4**
            | Note that multiple ``.*`` in the search string correspond
              with multiple ``$#``:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h:lastPath = [{"x":1,"y":0},{"x":1,"y":1},{"x":1,"y":2}]]

                  #. .. code-block:: none

                          [r:result = replace(lastPath, '\\{"x":(.*?),"y":(.*?)\\}', '"X\$1Y\$2"')]

            returns:

            ["X1Y0","X1Y1","X1Y2"]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=replace&oldid=6009"

