================================
getDialogProperties - MapToolDoc
================================

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

   .. rubric:: getDialogProperties
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

         .. container:: template_stub

            ** This article is a stub, you can help the RPTools Wiki
            project by contributing content to expand this article.**

         .. rubric:: getDialogProperties() Function
            :name: getdialogproperties-function

         .. container:: template_version

            • **Introduced in version 1.5.4**

         .. container:: template_description

            Returns a json object holding the properties associated with
            a given dialog. The properties are ``width``, ``height``,
            ``temporary``, ``title``, and ``value``.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getDialogProperties(name)

         **Parameters**

         -  ``name`` - The name of the dialog.

         .. rubric:: Example
            :name: example

         .. container:: template_example

            Opening up a dialog

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [dialog("Dialog Test", "width=300; height=200; temporary=0; title=A new title; value=data of relevance"): {test}]

            Getting the properties of the dialog:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [getDialogProperties("Dialog Test")]

            The output will be:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                         {"width":300,"height":200,"temporary":0,"title":"A new title","value":"data of relevance"}

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getDialogProperties&oldid=7572"

