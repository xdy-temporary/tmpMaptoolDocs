========================
json.unique - MapToolDoc
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

   .. rubric:: json.unique
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

            -  `1 json.unique()
               Function <#json.unique.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: json.unique() Function
            :name: json.unique-function

         .. container:: template_version

            • **Introduced in version 1.3b53**

         .. container:: template_description

            Returns a `JSON Array </rptools/wiki/JSON_Array>`__ with
            each value that occurs in the source `JSON
            Array </rptools/wiki/JSON_Array>`__ occurring only once. The
            relative order of the values in the array may not be
            preserved.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     json.unique(array)

         **Parameters**

         -  ``array`` - The `JSON Array </rptools/wiki/JSON_Array>`__ to
            return only unique values from.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Lets say you have a `JSON
            Array </rptools/wiki/JSON_Array>`__ that contains the
            following `Token </rptools/wiki/Token>`__ names:
            ``["Hero", "Dragon"]``, and you use ``getPCNames()`` to
            return the names of
            the `PC
            Tokens </maptool/index.php?title=PC_Token&action=edit&redlink=1>`__,
            you could use the following code to generate a `JSON
            Array </rptools/wiki/JSON_Array>`__ that contains the values
            in both `JSON Arrays </rptools/wiki/JSON_Array>`__ with no
            value present more than once.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: names1 = '["Hero", "Dragon"]']

                  #. .. code-block:: none

                        [h: names2 = getNPCNames()]

                  #. .. code-block:: none

                        [h: names = json.merge(names1, names2)]

                  #. .. code-block:: none

                        [r: json.unique(names)]

            If ``getPCNames()`` returns
            ``["Hero", "Sidekick", "Policeman"]`` then the result of the
            above code will be
            ``["Policeman","Sidekick","Hero","Dragon"]``

            While the above example demonstrates the output of
            ``json.unique()`` if you want to merge two or more arrays
            and get the unique values in one step you can use the
            ``json.union()``

            function.

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `json.merge() </rptools/wiki/json.merge>`__
            `json.union() </rptools/wiki/json.union>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=json.unique&oldid=2520"

