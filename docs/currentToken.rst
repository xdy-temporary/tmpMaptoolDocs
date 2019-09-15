=========================
currentToken - MapToolDoc
=========================

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

   .. rubric:: currentToken
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

         .. rubric:: currentToken() Function
            :name: currenttoken-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns the id of the `Current
            Token <Current_Token>`__. In most cases this
            will return the same as
            `getImpersonated() <Macros:Functions:getImpersonated>`__
            function. The difference is when it is called in a
            `[token():] <token_(roll_option)>`__ or after
            a call to the
            `switchToken() <Macros:Functions:switchToken>`__
            function, in both these cases it will return the id of the
            `token <token>`__ being operated on, while
            `getImpersonated() <Macros:Functions:getImpersonated>`__
            will return the id of the `impersonated
            token </maptool/index.php?title=impersonated_token&action=edit&redlink=1>`__.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     currentToken()

         | 

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - No longer a trusted function.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=currentToken&oldid=5624"

