.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Caution|This was for resolving issues with Java installs a long time ago and should never be done with current (Java 8+) Java.}}

Open a Command Prompt as Administrator.

CD into your C:\Windows\SysWOW64 directory.

Check for any java executables there. There shouldn't be any since the
launcher isn't working.

Then type in:

mklink java.exe ..\system32\java.exe

mklink javaw.exe ..\system32\javaw.exe

mklink javaws.exe ..\system32\javaws.exe

And try the Launcher again.
