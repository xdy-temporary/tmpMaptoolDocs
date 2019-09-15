=======================
exportData - MapToolDoc
=======================

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

   .. rubric:: exportData
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

            | ** This article is a stub, you can help the RPTools Wiki
              project by contributing content to expand this article.**
            | ** This article needs:** *Examples of usage.*

         .. rubric:: exportData() Function
            :name: exportdata-function

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         .. container:: template_version

            • **Introduced in version 1.5.0**

         .. container:: template_description

            Allows the storage of string data into an external file.

            .. container:: template_caution

               | **Caution:**
               | This function is considered experimental and its
                 implementation and parameters may change.

            The **Allow External Macro Access** option in MapTool's
            Preferences must be enabled or this macro aborts with an
            error.

            If MapTool is started with a particular character encoding
            in force, it will write the ``data`` using that encoding. If
            an existing file was created with a different encoding and
            is being appended to, the results when an application later
            attempts to read the file are undefined. (This is an
            artifact of how character encoding works, not something that
            MapTool can control.)

            Due to the use of a pathname, this function is inherently
            system and platform-specific. There is no way to determine
            whether the pathname used refers a directory that doesn't
            exist or for which the proper permissions are not available.
            The only test that can be done is to attempt to access a
            file with ``append`` turned off and see if it fails. This
            would indicate that the directory path cannot be accessed
            (doesn't exist or incorrect permissions), but if it succeeds
            there is now a file at the pathname given.

            It's recommended that pathnames NOT use backslashes (``\``),
            but use forward slashes (``/``) as the directory separator
            character. While forward slashes will work on Windows,
            Linux, and other Unix systems, backslashes will work only on
            Windows. In addition, it may be troublesome to use
            characters which the filesystem could interpret incorrectly
            (such as ``C:\topdir\mydir\filename`` interpreting the
            ``\t`` as a tab character and the ``\f`` as a form feed.
            Hence, our recommendation to use forward slashes for all
            filenames on all platforms.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     exportData(pathname, data, append)

         **Parameter**

         -  ``pathname`` - A string representing the pathname that
            ``data`` will be written to; this file will be created if it
            doesn't already exist.
         -  ``data`` - The string written to the file. MapTool does not
            impose an arbitrary limit on the length of this string, but
            the operating system might. Occurrences of ``\r`` inside the
            string will be interpreted as line breaks, and ``\t`` will
            be replaced by the tab character (Unicode/ASCII character
            code 9). (Note that in order to put a ``\`` into the string,
            two backslashes are needed, i.e. ``\r`` must be represented
            as ``\\r``.)
         -  ``append`` - This boolean value indicates whether the file
            is opened in append mode. If ``append`` is
            ``false``\ (``0``), any existing contents of the file will
            be overwritten.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=exportData&oldid=7058"

