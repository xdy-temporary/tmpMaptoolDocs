=======================
Stack Size - MapToolDoc
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

   .. rubric:: Stack Size
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

         .. container:: template_intermediate

            | INTERMEDIATE
            | THIS IS AN INTERMEDIATE ARTICLE

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 How Maptool Uses Memory <#How_Maptool_Uses_Memory>`__

               -  `1.1 Heap memory <#Heap_memory>`__
               -  `1.2 Stack memory <#Stack_memory>`__

            -  `2 Configuring memory allocation for
               MapTool <#Configuring_memory_allocation_for_MapTool>`__

               -  `2.1 Setting the memory allocation in a batch
                  file <#Setting_the_memory_allocation_in_a_batch_file>`__

                  -  `2.1.1 Editing a .bat
                     file <#Editing_a_.bat_file>`__
                  -  `2.1.2 Editing the .sh or .command
                     file <#Editing_the_.sh_or_.command_file>`__

               -  `2.2 Setting the memory allocation when using
                  MapToolLauncher
                  (Windows-only) <#Setting_the_memory_allocation_when_using_MapToolLauncher_.28Windows-only.29>`__
               -  `2.3 Setting the memory allocation for Java WebStart
                  (any
                  platform) <#Setting_the_memory_allocation_for_Java_WebStart_.28any_platform.29>`__
               -  `2.4 Setting the memory allocation in the Mac OS X
                  application
                  bundle <#Setting_the_memory_allocation_in_the_Mac_OS_X_application_bundle>`__

                  -  `2.4.1 If you want to run MapTool twice on OS X
                     ... <#If_you_want_to_run_MapTool_twice_on_OS_X_...>`__

         .. rubric:: How Maptool Uses Memory
            :name: how-maptool-uses-memory

         When MapTool starts, the Java virtual machine (the program that
         lets MapTool run on your computer!) configures a number of
         settings for the program. Three of these settings affect the
         memory given to MapTool: *heap memory* (the memory MapTool uses
         to store data and resources), and *stack memory* (the amount of
         memory threads are allowed to use).

         .. rubric:: Heap memory
            :name: heap-memory

         The heap memory allocated to MapTool indicates how much memory
         MapTool uses to store objects (maps, tokens, image files,
         macros, etc.) Heap memory allocation is controlled by two
         options: ``-Xms`` sets the *starting heap size* (the initial
         amount of memory MapTool is allocated) and ``-Xmx`` sets the
         *maximum heap size* (the maximum amount of memory MapTool is
         allowed to access).

         If you set the maximum heap size too low, MapTool may run out
         of memory and crash, freeze, or have other problems. MapTool
         clients that are connecting to a server should use the same
         memory settings as the server when possible; otherwise clients
         may freeze or lose connection when using larger or more complex
         maps.

         .. rubric:: Stack memory
            :name: stack-memory

         The stack memory is the amount of memory each *thread* is
         given; threads are sub-processes that handle application
         functions like network access, macro execution, and drawing the
         UI. Stack memory allocation is controlled by one option:
         ``-Xss`` sets the *stack size* (each thread is given exactly
         the amount specified; there is no starting or maximum stack
         size).

         Some macro frameworks will require larger stack sizes as they
         perform more complex calculations and functions; they will
         usually specify their stack requirements. If a thread runs out
         of stack memory you will see a **StackOverflow** error and the
         macro will not work.

         .. rubric:: Configuring memory allocation for MapTool
            :name: configuring-memory-allocation-for-maptool

         In the beginning, MapTool used whatever default stack size and
         heap size Java felt like setting. The actual amount varied from
         operating system to operating system, but it was generally
         enough for the simple macros that were in use at the time. As
         the power and flexibility of the macro code increased, macros
         began to bump up against the limits of the default stack, and
         users began adjusting the stack size to compensate. As
         frameworks and maps became larger and more complex, users began
         adjusting the maximum heap size.

         The amount of memory is specified in kilobytes or megabytes;
         "512K" is 512 kilobytes, while "512M" is 512 megabytes.

         **WARNING**: **Stack memory is allocated in addition to heap
         memory and each thread receives the same amount of stack
         memory. If you set the stack memory allocation too high, the
         Java VM can consume far more memory than is necessary which
         will affect overall computer performance.**

         .. rubric:: Setting the memory allocation in a batch file
            :name: setting-the-memory-allocation-in-a-batch-file

         One of the ways to start MapTool is via the various script or
         *batch files* that are included when you download and unzip a
         copy of MapTool. There are three different types of script
         files included with MapTool as of 1.3.v77:

         -  ``Launch MapTool.bat``, ``Launch MapTool-512M-Memory.bat``
            and ``Launch MapTool-1G-Memory.bat`` for Windows; the
            different names refer to different maximum heap allocations
         -  ``Launch MapTool.sh`` for Linux and Mac OS X
         -  ``Launch MapTool.command`` for Mac OS X; this file can be
            double-clicked to start MapTool.

         .. rubric:: Editing a .bat file
            :name: editing-a-.bat-file

         Though each batch file has different heap sizes specified, the
         format is the same:

         ::

            javaw -Xmx512M -Xss512K -jar maptool-*.jar run

         To set the maximum heap size, change the ``-Xmx`` option. To
         set the stack size, change the ``-Xss`` option.

         .. rubric:: Editing the .sh or .command file
            :name: editing-the-.sh-or-.command-file

         At the top of the shell script file are three variables:

         ::

            MAXMEMSZ="768m"
            MINMEMSZ="32m"
            STACKSZ="2m"

         You can set the starting heap (MINMEMSZ), maximum heap
         (MAXMEMSZ), and stack size (STACKSZ) by changing these
         variables.

         .. rubric:: Setting the memory allocation when using
            MapToolLauncher (Windows-only)
            :name: setting-the-memory-allocation-when-using-maptoollauncher-windows-only

         If you start MapTool with the Windows launcher, you can set the
         starting heap (Min Mem), maximum heap (Max Mem), and stack
         (Stack Size) sizes.

         The Windows launcher defaults to a 2MB stack which is
         acceptable for many environments. If you change the memory
         values, the new values will be saved for the next launch. To
         reset the values, simply remove the **MT.CFG** file where they
         are saved.

         .. rubric:: Setting the memory allocation for Java WebStart
            (any platform)
            :name: setting-the-memory-allocation-for-java-webstart-any-platform

         If you start MapTool using the Java WebStart option, you can
         change the settings here, too.

         #. Go to `the MapTool Launch
            page <http://www.rptools.net/index.php?page=launch>`__
         #. Click the **CUSTOMIZATION** link; three fields for setting
            memory options will be exposed
         #. You can set the starting heap (Minimum memory), maximum heap
            (Maximum memory), and stack size (Stack size) by changing
            these variables
         #. Click on the links above to start the application you wish
            to use.

         If you have a saved **.jnlp** (Web Start) file, you can edit
         the memory settings by hand.

         -  Open the **.jnlp** file in a text editor
         -  Look for the following section (the actual memory values may
            differ in your copy):

         ::

               <j2se version="1.5+"
                   initial-heap-size="64m"
                   max-heap-size="512m"
                   java-vm-args="-Xmx512m -Xms64m -Xss2m"/>

         -  To change the starting heap size, change the
            ``initial-heap-size`` entry and the ``-Xms`` entry
         -  To change the maximum heap size, change the
            ``max-heap-size`` entry and the ``-Xmx`` entry
         -  To change the stack memory size, change the ``-Xss`` entry
         -  Save the **.jnlp** file

         .. rubric:: Setting the memory allocation in the Mac OS X
            application bundle
            :name: setting-the-memory-allocation-in-the-mac-os-x-application-bundle

         Users who download the **.dmg** (disk image) file from the
         `RPTools download
         page <http://www.rptools.net/index.php?page=downloads>`__ and
         installed MapTool from it will see MapTool as a Mac OS X
         application bundle. MapTool can be launched by double-clicking
         it like any other Mac OS application.

         #. Ctrl-click (or right-click) on MapTool application icon.
         #. Choose *Show Package Contents* and a new Finder window will
            open.
         #. Open the **Contents** folder and locate the **Info.plist**
            file.
         #. Double-click that file to open the Property List Editor.
         #. Expand the entry for *Java* so it looks like the one below
            (it's at the bottom of the image, below).
         #. To set the maximum heap size, change the ``-Xmx`` option. To
            set the stack size, change the ``-Xss`` option. To set the
            starting heap size, change the ``-Xms`` option (not depicted
            in the above image).
         #. Save the file. The next time you double-click the MapTool
            icon, it will launch using the new memory settings.

         |Property List Editor.png|

         .. rubric:: If you want to run MapTool twice on OS X ...
            :name: if-you-want-to-run-maptool-twice-on-os-x-...

         You might want this for testing purposes, or perhaps you're
         using a dual-monitor setup where one screen shows MapTool
         running as a GM and the other shows MapTool running as a Player
         (such as a HDTV or LCD projector). In other words, you open
         MapTool once and start a server, then open it again and connect
         to the server as a client.

         #. Open **Terminal**
         #. Type ``open -n "MapTool.app"`` (or whatever name your
            MapTool is saved as) and press **Enter**

         Otherwise, when you double-click an application on OS X it
         simply re-activates the application window that's already
         running. I don't know of any way of running ``open -n`` from
         the GUI although it would be a pretty simple AppleScript
         program. (It looks like it's solved here:
         http://superuser.com/questions/67190/how-can-i-get-an-dock-icon-to-launch-a-program-multiple-times
         And then this page has a description of how to do the same
         thing with a Ctrl-Click menu option:
         http://lifehacker.com/#!5766390/how-to-open-two-instances-of-an-application-in-os-x
         )

         As MapTool is quite a small program, another way to do it is
         just duplicating and renaming the program (as "MapTool-client"
         for instance). This would not usually be a clean way to handle
         it, but again, it's a small software. The good point is you now
         have two programs with different names. Once the two are
         launched, it's easy to tell which is which in the Dock or when
         command-tabbing to switch from one to the other.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Stack_Size&oldid=5633"

