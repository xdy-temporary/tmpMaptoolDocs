===========================
onCampaignLoad - MapToolDoc
===========================

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

   .. rubric:: onCampaignLoad
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

            -  `1 onCampaignLoad Macro <#onCampaignLoad_Macro>`__

               -  `1.1 How to Create an onCampaignLoad
                  Macro <#How_to_Create_an_onCampaignLoad_Macro>`__
               -  `1.2 Limitations <#Limitations>`__
               -  `1.3 Example of Deferred Function
                  Calls <#Example_of_Deferred_Function_Calls>`__

         .. rubric:: onCampaignLoad Macro
            :name: oncampaignload-macro

         **• Introduced in version 1.3b51**

         A special macro that can be created on `library
         tokens </rptools/wiki/Library_Token>`__ to have macro code
         automatically execute when a campaign is loaded. A campaign is
         considered to have been loaded if it is opened via the File
         menu, or upon connecting to a server running that campaign. All
         output from an ``onCampaignLoad`` macro is discarded, when it
         is executed automatically.

         This special macro is ideally suited for loading your User
         Defined Functions (UDFs) via
         `defineFunction() </rptools/wiki/defineFunction>`__.

         When an onCampaignLoad macro is executed automatically, it is
         considered a `Trusted Macro </rptools/wiki/Trusted_Macro>`__.
         If you wish to use trusted functions within ``onCampaignLoad``
         and execute it manually (e.g. while developing macros), you
         will have to make sure that it follows all of the rules of
         `Trusted Macros </rptools/wiki/Trusted_Macro>`__.

         .. rubric:: How to Create an onCampaignLoad Macro
            :name: how-to-create-an-oncampaignload-macro

         You can create an ``onCampaignLoad`` macro on any `library
         token </rptools/wiki/Library_Token>`__; simply create a macro
         that is specifically named ``onCampaignLoad``.

         .. rubric:: Limitations
            :name: limitations

         -  Do not make changes within the ``onCampaignLoad`` macro to
            the library token it resides upon. This is not supported by
            MapTool. A duplicate lib token can/will appear and this
            will/can break stuff.
         -  Some macro functions may not work as expected if run in
            ``onCampaignLoad`` without deferring their execution by
            using the defer option of
            `execLink() </rptools/wiki/execLink>`__.

            -  `goto() </rptools/wiki/goto>`__,
               `setZoom() </rptools/wiki/setZoom>`__ and similar
               function calls should be placed in a separate macro to be
               called via `execLink() </rptools/wiki/execLink>`__

         .. rubric:: Example of Deferred Function Calls
            :name: example-of-deferred-function-calls

         Inside the ``onCampaignLoad`` macro place code like this:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: link = macroLinkText("deferredCalls@"+getMacroLocation())]

               #. .. code-block:: none

                     [h: execLink(link,1)]

         And in the deferredCalls() macro place the functions to be
         deferred.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: goto("2")]

               #. .. code-block:: none

                     [h: setZoom(2)]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=onCampaignLoad&oldid=7004"

