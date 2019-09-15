==========================
base64.decode - MapToolDoc
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

   .. rubric:: base64.decode
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

            -  `1 base64.decode()
               Function <#base64.decode.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Example <#Example>`__
               -  `1.3 See Also <#See_Also>`__

         .. rubric:: base64.decode() Function
            :name: base64.decode-function

         .. container:: template_version

            • **Introduced in version 1.5.2**

         .. container:: template_description

            Accepts a `Base64 <https://en.wikipedia.org/wiki/Base64>`__
            encoded string and decodes it to plain text.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     base64.decode(string)

         **Parameters**

         -  ``string`` - The base64 encoded string to be decoded.

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

            `base64.encode() <base64.encode>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=base64.decode&oldid=7394"

