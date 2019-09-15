==========================
formatStrProp - MapToolDoc
==========================

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

   .. rubric:: formatStrProp
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

         .. rubric:: formatStrProp() Function
            :name: formatstrprop-function

         .. container:: template_description

            Returns a custom-formatted version of the property string.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: formatStrProp(props, listFormat, entryFormat, separator) ]

         -  listFormat is a string that is emitted once. It should
            contain the text "%list", which is replaced with the
            formatted items.
         -  entryFormat is emitted once per item. Any instances of
            "%key" and "%value" in the string are replaced with the key
            or value for that setting.
         -  separator is emitted in between the formatted items.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: props = "Strength=14 ; Constitution=8 ; Dexterity=13 ; Intelligence=4 ; Wisdom=18 ; Charisma=9"]

                  #. .. code-block:: none

                        [formatStrProp(props, "<table border=1>%list</table>", "<tr> <td><b>%key</b></td> <td>%value</td> </tr>", "")]

            Outputs:

            ================ ==
            **Strength**     14
            **Constitution** 8
            **Dexterity**    13
            **Intelligence** 4
            **Wisdom**       18
            **Charisma**     9
            ================ ==

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=formatStrProp&oldid=4007"

