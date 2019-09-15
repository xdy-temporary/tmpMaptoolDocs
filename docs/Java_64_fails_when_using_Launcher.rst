==============================================
Java 64 fails when using Launcher - MapToolDoc
==============================================

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

   .. rubric:: Java 64 fails when using Launcher
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

         .. container:: template_caution

            | **Caution:**
            | This was for resolving issues with Java installs a long
              time ago and should never be done with current (Java 8+)
              Java.

         Open a Command Prompt as Administrator.

         CD into your C:\Windows\SysWOW64 directory.

         Check for any java executables there. There shouldn't be any
         since the launcher isn't working.

         Then type in:

         mklink java.exe ..\system32\java.exe

         mklink javaw.exe ..\system32\javaw.exe

         mklink javaws.exe ..\system32\javaws.exe

         And try the Launcher again.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Java_64_fails_when_using_Launcher&oldid=7338"

