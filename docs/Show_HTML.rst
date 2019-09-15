======================
Show HTML - MapToolDoc
======================

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

   .. rubric:: Show HTML
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

         .. rubric:: How to show html code
            :name: how-to-show-html-code

         Sometimes you want to show html code in chat or in a frame.
         Sadly MapTool always interprets the html markup. This is
         sometimes unwanted, especially if you try to debug complex
         output.

         | 
         | Luckily its quite easy to trick MapTool to leave yout html as
           it is - you just have to break it. Replace all left brackets
           in the tags by the html entity for that bracket. The result
           isnt valid html anymore, so MapTool cannot format it - but it
           looks all the same to you. You can even copy it and use it as
           valid html code.

         | 

         .. rubric:: Example
            :name: example

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: output = "<h1>This is a headline</h1><p>but <em>this</em> is not</p>"]

               #. .. code-block:: none

                     [h: output = replace(output, "<", "&lt;")]

               #. .. code-block:: none

                     [r: output]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Show_HTML&oldid=5695"

