.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{stub|Examples of usage.}}

.. raw:: mediawiki

   {{MacroFunction
   |name=exportData
   |trusted=true
   |version=1.5.0
   |description=
   Allows the storage of string data into an external file.

   {{Caution|This function is considered experimental and its implementation and parameters may change.}}

   The <b>Allow External Macro Access</b> option in MapTool's Preferences must be enabled or this macro aborts with an error.

   If MapTool is started with a particular character encoding in force, it will write the {{code|data}} using that encoding.  If an existing file was created with a different encoding and is being appended to, the results when an application later attempts to read the file are undefined.  (This is an artifact of how character encoding works, not something that MapTool can control.)

   Due to the use of a pathname, this function is inherently system and platform-specific.  There is no way to determine whether the pathname used refers a directory that doesn't exist or for which the proper permissions are not available.  The only test that can be done is to attempt to access a file with {{code|append}} turned off and see if it fails.  This would indicate that the directory path cannot be accessed (doesn't exist or incorrect permissions), but if it succeeds there is now a file at the pathname given.

   It's recommended that pathnames NOT use backslashes ({{code|\}}), but use forward slashes ({{code|/}}) as the directory separator character.  While forward slashes will work on Windows, Linux, and other Unix systems, backslashes will work only on Windows.  In addition, it may be troublesome to use characters which the filesystem could interpret incorrectly (such as {{code|C:\topdir\mydir\filename}} interpreting the {{code|\t}} as a tab character and the {{code|\f}} as a form feed.  Hence, our recommendation to use forward slashes for all filenames on all platforms.

   |usage=
   <source lang="mtmacro" line>
   exportData(pathname, data, append)
   </source>
   '''Parameter'''
   {{param|pathname|A string representing the pathname that {{code|data}} will be written to; this file will be created if it doesn't already exist.}}
   {{param|data|The string written to the file.  MapTool does not impose an arbitrary limit on the length of this string, but the operating system might.  Occurrences of {{code|\r}} inside the string will be interpreted as line breaks, and {{code|\t}} will be replaced by the tab character (Unicode/ASCII character code 9).  (Note that in order to put a {{code|\}} into the string, two backslashes are needed, i.e. {{code|\r}} must be represented as {{code|\\r}}.)}}
   {{param|append|This boolean value indicates whether the file is opened in append mode.  If {{code|append}} is {{false}}, any existing contents of the file will be overwritten.}}

   |examples=

   |also=
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
