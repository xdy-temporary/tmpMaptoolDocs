==========================
herolab.XPath - MapToolDoc
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

   .. rubric:: herolab.XPath
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

            -  `1 herolab.XPath()
               Function <#herolab.XPath.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: herolab.XPath() Function
            :name: herolab.xpath-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro </rptools/wiki/Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Returns data results based on the passed in XPath expression
            from the XML statblock. This is a reliable and easier way to
            get stat data from a character than using regular expression
            parsing of Text stat blocks.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     herolab.XPath(XPath)

               #. .. code-block:: none

                     herolab.XPath(XPath, id)

         **Parameters**

         -  ``XPath`` - The XPath expression to evaluate against the XML
            statblock.
         -  ``id`` - The id of the token. Defaults to the Current Token.

         Returns the requested data.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Get various values from Hero Lab data (which is in XML).

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [race = herolab.XPath('/document/public/character/race/@name')]

                  #. .. code-block:: none

                        [alignment = herolab.XPath('/document/public/character/alignment/@name')]

                  #. .. code-block:: none

                        [improvedInit = herolab.XPath('boolean(/document/public/character/feats/feat[starts-with(@name,"Improved Initiative")])')]

            Returns:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                     Human Neutral Good 1

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `Hero Lab
            Integration </maptool/index.php?title=Hero_Lab_Integration&action=edit&redlink=1>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=herolab.XPath&oldid=7214"

