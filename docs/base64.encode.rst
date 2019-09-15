==========================
base64.encode - MapToolDoc
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

   .. rubric:: base64.encode
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

            -  `1 base64.encode()
               Function <#base64.encode.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: base64.encode() Function
            :name: base64.encode-function

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Takes the supplied text string and encodes it to
            `Base64 <https://en.wikipedia.org/wiki/Base64>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     base64.encode(string)

         **Parameters**

         -  ``string`` - The text string to be encoded.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Encode a string and then decode it.

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [r: txt = "Four score and seven years ago..."]<br>

                  #. .. code-block:: none

                        [r: encTxt = base64.encode(txt)]<br>

                  #. .. code-block:: none

                        [r: base64.decode(encTxt)]<br>

            **Returns:**

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        Four score and seven years ago... 

                  #. .. code-block:: none

                        Rm91ciBzY29yZSBhbmQgc2V2ZW4geWVhcnMgYWdvLi4u 

                  #. .. code-block:: none

                        Four score and seven years ago...

         .. rubric:: See Also
            :name: see-also

         .. container:: template_also

            `base64.decode() </rptools/wiki/base64.decode>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=base64.encode&oldid=7393"

