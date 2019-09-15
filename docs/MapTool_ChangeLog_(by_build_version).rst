.. contents::
   :depth: 3
..

.. _maptool_changelog_for_the_source_code:

MapTool ChangeLog (for the source code)
=======================================

Note: This ChangeLog is for the 1.3 versions of MapTool. MapTool source
code is now housed on GitHub. Newer versions of MapTool and their
associated changelogs can be found on the `GitHub MapTool
Page <https://github.com/RPTools/maptool>`__.

This page will attempt to document the on-going changes to the
**MapTool** source code by those individuals who have Commit authority
to the Subversion repository on Sourceforge.net.

Ideally, I'd like to see an actual ChangeLog for each build of MapTool
as well as an "in my queue right now" list, but the latter is unlikely
to be kept up to date (even by me!) so I'll settle for just a ChangeLog.
:)

Since the RPTools team has not been using the SourceForge bug tracker
for 1.3 there hasn't been a comprehensive list of bugs/features being
worked on (long story, but we **will** be using the Mantis bug tracker
for 1.4). I have provided a list of `Things I'd Like to See
Fixed <Things_I'd_Like_to_See_Fixed>`__ for 1.3 but there is no
guarantee expressed or implied that any of them will come to fruition!

.. _where_to_find_more_information:

Where to find more information
------------------------------

For information about how to download (a.k.a. checkout) the source code,
please see the thread on our forum that discusses that topic: `How to
get RPTools source via Eclipse and
subversion <http://forums.rptools.net/viewtopic.php?f=7&t=421>`__.
Another topic worth reviewing is a *stream of consciousness* thread by
Azhrei regarding notes on how to build the application using Eclipse:
`MapTool build notes for
Eclipse <http://forums.rptools.net/viewtopic.php?f=7&t=14196>`__.

.. _changelog_entries:

ChangeLog entries
-----------------

.. _final_p07_1.3.b90_released_soon:

1.3 Final p07 (1.3.b90; released [soon])
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  replaced a lot of calls to System.err with logging to .error() or
   .warn()

-  commented out a lot of System.out.println() statements!

-  simple VBL line thickness fix (Jamz);
   http://forums.rptools.net/viewtopic.php?f=60&t=23850&view=unread#p242498

-  updated formatting preferences for Eclipse

-  latest VBL functions from Jamz;
   http://forums.rptools.net/viewtopic.php?f=60&t=23849

-  fixed handling of spaces in <key,value> pairs for varsFromStrProp
   since spaces are allowed in keys now; added javadoc

-  fix for setSize() not working when token is Native or Free size;
   http://forums.rptools.net/viewtopic.php?f=27&t=23843

-  removed MapToolLauncher written in C++ -- superseded by Java version
   in new project

-  updated logging XML files; fix for i18n in drawVBL/eraseVBL; updates
   to StringUtil

-  formatting; removed System.out debugging call

-  added drawVBL/eraseVB functions; added get/setTokenShape() and
   getTokenWidth/Height() functions

-  fix for canSeeToken() when token is !snapToGrid; (Jamz)

-  fix for how VBL line segments join; (Jamz)

-  added X as topology (VBL) drawing shape; (CoveredInFish)

-  added image to use in Help menu

-  allow setLayer() and copyToken() to take optional parameter that
   prevents token shape change; (Azhrei)
   http://forums.rptools.net/viewtopic.php?f=20&t=23610

-  formatting; regex change looking for Help keys in properties; "import
   map" code test

-  fixed typo in reference to i18n.properties key

-  added Help menu item for Networking Setup (points to NFAQ); added
   confirmation of ImportMap menu function;
   http://forums.rptools.net/viewtopic.php?f=3&t=23614

-  fix removeFacing() parameter count; (Jamz)
   http://forums.rptools.net/viewtopic.php?f=60&t=23802

-  new UPNP library; added "-Xdock:name" to Debug configurations (will
   it work on non-OSX?)

-  sorry, I believe the only changes are licensing and some fixed
   warnings but not guaranteed :(

-  general cleanup, license change, warnings fixed in prep for end of
   1.3 and beginning of 1.4

-  added licensing details; some code is Apache, some is LGPL, some is
   AGPL

-  reformatting; license update to LGPL

-  fix NPE for macrokeys in J7 but not J6 (Lee);
   http://forums.rptools.net/viewtopic.php?f=60&t=23568

-  updated list of logging configuration options

-  added OOM handling during campaign IO so a better message is provided

-  added InputMap debugging (trying to track down NPE);
   http://forums.rptools.net/viewtopic.php?f=3&t=23541

-  fix missing/incorrect translation keys (found by looking at log.txt)

-  attempt to standardize calls to getInputMap() to help track down NPE

-  updated fix for drawVBL/eraseVBL feature (Jamz);
   http://forums.rptools.net/viewtopic.php?f=60&t=23545

-  backed out the fix for better smiley parsing in the HTML chat (caused
   duplicate text); http://forums.rptools.net/viewtopic.php?f=3&t=23543

-  added "all.xml" file to turn on all available logging

-  fix for autosaving not clearing the AppState flag (final fix?)

-  fix action.undoMapDrawing (remove "Map"), test version of new
   autosave code

-  fix filenames (remove spaces) and update logging info

-  fix to VBL macro boundary checks (Jamz);
   http://forums.rptools.net/viewtopic.php?f=60&t=23521

-  added logging in AppState to help isolate problems with autosave
   deadlocks

-  switch to new Windows-based batch file setup (Vhex);
   http://forums.rptools.net/viewtopic.php?f=3&t=21856&p=239330#p239304

-  cleanup of Windows batch files; move towards making them more generic

.. _final_p06_1.3.b89_released_2013_04_05:

1.3 Final p06 (1.3.b89; released 2013-04-05)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  removed unneeded JAR file
-  removed stupid files auto-created by OSX's File Manager
-  added rplib-1.0.b134 for maptool-1.3.b89
-  fix smiley parsing in chat output (tiorthan);
   http://forums.rptools.net/viewtopic.php?f=60&t=22591
-  fix handling of exceptions that could have caused exceptions
   (tiorthan); http://forums.rptools.net/viewtopic.php?f=60&t=22547
-  added text from "Help > Gather Sys Info..." to the getInfo() macro
   result (CiF); http://forums.rptools.net/viewtopic.php?f=60&t=23442
-  fix token highlighting after grid adjustment (Lee);
   http://forums.rptools.net/viewtopic.php?f=60&t=23080
-  corrects how paths are calculated for tokens under certain
   circumstances (Lee);
   http://forums.rptools.net/viewtopic.php?f=60&t=22924
-  fix movement of token group when snapped token follows unsnapped
   token on map with snap-to-grid turned on (Lee);
   http://forums.rptools.net/viewtopic.php?f=60&t=22920#p234014
-  add macro functions for drawing/erasing VBL (JamzTheMan);
   http://forums.rptools.net/viewtopic.php?f=3&t=22624
-  last piece of VisibleAreaSegment cleanup
-  added Apache commons-net-3.2.jar to the build path for FTP fix
-  sometimes input() panels are too large; this patch constrains the
   height to 5/8 the screen height
-  fixes problem where loading a campaign would delete straight lines
   made with the drawing tools
-  modify getTokenImage() so it returns an empty string instead of
   causing an error for invalid token identifiers
-  fix HTML form submission; patch based on Lee's code
-  fix "Comparator violates contract!" exception without using Java 6
   legacy mode
-  using FTP to update an existing repository is being removed (slowly)
   as a feature
-  change broadcast() so empty list sends to no one;
   http://forums.rptools.net/viewtopic.php?f=3&t=23212
-  fixed handling of line terminators inside list string functions;
   http://forums.rptools.net/viewtopic.php?f=3&t=23223
-  new field suggested by wolph42;
   http://forums.rptools.net/viewtopic.php?f=26&t=23154
-  credit to yorick for finding a huge inefficiency!
   http://forums.rptools.net/viewtopic.php?f=3&t=23174
-  removed source file no longer used; cleaned up "Help > Gather Debug
   Info..." menu option
-  Help menu now dynamically builds menu items for external URLs by
   reading language-dependent property files
-  Fix "Comparable doesn't abide by contract" error in Java 7 (no
   testing by me as I don't have J7 on OSX -- yet)
-  json.type.patch.txt contributed by tiorthan
-  browserstartfix.txt contributed by tiorthan with some changes from
   azhrei_fje
-  colordisplayfix.txt as contributed by tiorthan
-  tiorthan/imageaspectfix.txt -- keep aspect ratio of image if only
   width or height change
-  Craig's patch to revert a previous patch which cleared the tokenCache
   prematurely in the Zone renderer
-  Problems encountered while closing the upnp port now log a warning
   message rather than producing a pop up with information that is not
   useful to the user.
-  Changed the way the MTscript strformat() works when a format string
   specifies an invalid variable name inside %{} -- should be backward
   compatible
-  Create import file for RegEdit on Windows that removes MapTool
   registry entries
-  Applied high resolution mouse wheel fix from RevenantBob.
-  Removed fix for map not displaying on first start up of campaign bug
   fix as it was causing a more serious bug with resizing of objects.
-  Applied patch from username that fixed a bug while dropping a second
   token.
-  Fix conversion of string list into json array via json.fromList()
-  Replaced DrawableUndoManager with UndoPerMap (the previous one was
   global); temporary commit -- needs a lot of testing
-  Remove block dot from center of Radius Template when drawn

.. _final_p05_1.3.b88_released_2012_03_16:

1.3 Final p05 (1.3.b88; released 2012-03-16)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  German translation updated
-  Spanish translation updated
-  Fix problem with color chooser not working in non-English locale
-  Ensure dialogs larger than the owner window are not positioned
   off-screen
-  Fix that leaves original **%{}** intact in `strformat <strformat>`__
   when unknown variable is used
   http://forums.rptools.net/viewtopic.php?f=20&t=21206
-  Fix NPE when autosaving and copying a map
-  Another attempt to correct the formatting of **Can't create data
   directory "{0}"** which somehow seems to always treat the "{0}"
   literally (sigh); added stacktrace to any error that causes that
   message to try to determine where it's coming from
-  Fix conic vision problem
   http://forums.rptools.net/viewtopic.php?f=1&t=20068&start=120#p215768
-  Fix inability to draw a second VBL line after drawing the first
   http://forums.rptools.net/viewtopic.php?f=7&t=19741#p215627
-  Hide exceptions used for `abort <abort>`__ and `assert <assert>`__
   from the user (they were hidden originally, but changes made them
   visible)
-  Added `assert <assert>`__ handling to look like `abort <abort>`__
   handling
-  Fix problem with new "title" being ignored when refreshing an HTML
   frame
   http://forums.rptools.net/viewtopic.php?f=1&t=20068&p=214990#p214990
-  Added StringUtil.parseBoolean() function that accepts a string and
   checks for "true" or non-zero (currently unused, but available for
   new MTscript function in the future)
-  Fix for campaign not refreshing properly on first load
   http://forums.rptools.net/viewtopic.php?f=7&t=19741&p=214883#p214883
-  Move rendering of labels after rendering of fog (so they are drawn on
   top of fog); needs more testing
-  MapTool.confirmTokenDelete() should default to YES instead of NO
   http://forums.rptools.net/viewtopic.php?f=1&t=20068&p=212306#p212306
-  Make sure **Map > Import Map...** is disabled whenever **File > Open
   Campaign...** is disabled, such as for a client logged in as GM
-  Move calls that render movement paths of owned tokens so they occur
   after fog is rendered; this should put them on top in all situations
-  Fix dropping of token doesn't use *Preferences* setting for
   **Filename vs. Creature** name
   http://forums.rptools.net/viewtopic.php?f=3&t=19202&p=202692
-  Changed "Green" to "Lime" to match HTML color names used elsewhere
   http://forums.rptools.net/viewtopic.php?f=1&t=20068#p214381
-  Remove debugging code that was **System.out**-related (ugh)
-  Don't add trailing delimiter to end of string in
   `setStrProp <setStrProp>`__ function
   http://forums.rptools.net/viewtopic.php?f=3&t=20517#p214422
-  Fix using an IF roll option with an empty ELSE block causes an NPE
   http://forums.rptools.net/viewtopic.php?f=20&t=19230&p=213725#p213725
-  Fix error in help docs for the **Campaign Properties > Light** tab
   http://forums.rptools.net/viewtopic.php?f=3&t=19240&p=203192
-  Fix oval VBL tool so that it correctly draws the rubberband image
   http://forums.rptools.net/viewtopic.php?f=1&t=20068&p=212044
-  Fix hitting the close button on an `input <input>`__ dialog causes
   NPE http://forums.rptools.net/viewtopic.php?f=20&t=20180&p=211624
-  Fix new HTMLFrames (frame/dialog roll option) appear in the center of
   the screen
   http://forums.rptools.net/viewtopic.php?f=1&t=20068&p=211716
-  Changed initial docked panel layout to only show **Resource
   Library**, **Map Explorer**, and **Chat** panel (others are hidden by
   default)
-  Added exception handling to downloading of art pack list (network IO
   exceptions)
-  Cleanup asset root handling (duplicates removed when asset is
   added/removed; removing is more efficient)
-  Fix IllegalArgumentException: Comparable does not adhere to contract
   (needs more testing)
-  Fix conversion of File object into URL for art packs; fixes some
   errors when downloading art packs
-  Updated the **Default.theme** and **README.wri** shipped in the ZIP
   file
-  Autosave manager should have been encased in try/finally block to
   prevent AppState from thinking autosave is in progress if an
   exception is thrown
-  Updated **sbbi-upnplib** to rebuilt source code with Generics support
   and JXPath interface fixed for JXPath-1.3; fixes UPNP not working
-  Fix so `input <input>`__ dialogs auto-scroll to the top on open
-  **OK** button should be set as default so closes dialog
-  Dialog window height set to 75% of screen height
-  Zone constructor for maps wasn't deep copying its contents
-  username -- Added a new public API that allows waiting for images to
   be available when using FileUtil.saveToken()
-  username -- Fix to avoid a concurrency issue (workaround; needs
   proper fix)
-  username -- Fixes on OpenJDK compatibility

.. _final_p04_1.3.b87_released_2011_10_06:

1.3 Final p04 (1.3.b87; released 2011-10-06)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Added menu item for **Help > Gather Debugging Information** (user
   debugging)
-  Fixed the zoom field so that typing in a number has better error
   handling
-  Fix for assets referenced in a campaign file but not included in it
   (would cause "Cannot load campaign" errors)
-  Fix MTscript **setSize()** and **copyToken()** to accept "free" or
   "native" to indicate original image size
-  Updated Spanish translation from **patoace**
-  Added some keystroke mappings for OSX (instead of requiring HOME and
   END, Meta-Left and Meta-Right will suffice now)
-  Fixed bug in the way MTscript function **copyToken()** initialized
   exposed fog for new tokens
   http://forums.rptools.net/viewtopic.php?f=3&t=20025
-  Change handling of token deletion dialog so that NO is the default
   when the window Close button is used
-  Add check to avoid NPE when exporting a screenshot
-  FoW fixes - selecting only an NPC works like not selecting any token
   at all
-  FoW fixes - no tokens selected shows the same as all owned tokens
   merged; global FoW added to individual fog
-  Fixed NPE when releasing the mouse and Object/Background token was
   being resized http://forums.rptools.net/viewtopic.php?f=21&t=19638
-  Defer image update to avoid deadlock
   http://forums.rptools.net/viewtopic.php?f=21&t=19325
-  Fix for crash when quitting MT and saying "Yes" to save and an
   autosave is currently running
   http://forums.rptools.net/viewtopic.php?f=3&t=18998&p=200564#p200564
-  Updated XStream library from 1.3.1 to 1.4.1 (fixes crash under Java
   7)
-  Halos on objects and footprints were drawn wrong on objects.
   http://forums.rptools.net/viewtopic.php?f=3&t=18878
-  Made sure Windows .BAT files had CR-LF terminators
-  Phergus' -- fix for keyboard movement of tokens on hex grids
-  Phergus' -- fix for hard fog appearing when no owned tokens are
   selected
-  Last (?) fix for NPE on movement when Lock Movement flag is set on
   init panel
-  Add ability for DEVELOPMENT version to act as client or server to any
   other version (but causes **properties.xml** to contain a version
   number of DEVELOPMENT in saved campaigns)
-  Changed hard-coded CTRL_DOWN_MASK to platform-specific key (Ctrl on
   Windows and Unix, Command on OSX)
-  Moved "Change To" on right-click menu for stamps so it appears in the
   same place as on tokens
-  Updated many third-party libraries (string handling, docking panels,
   TinyLAF, JSON)
-  Added **Default.theme** to the ZIP file -- may require copying it to
   your **.maptool/config** directory to enable it on some platforms

.. _final_p03_1.3.b86_released_2011_04_18:

1.3 Final p03 (1.3.b86; released 2011-04-18)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Tweak to token's context menu so that merging all tokens' TEA is
   faster (not used much anyway?)
-  Fixed a lot of warnings (about 70 out of 700!)
-  Better error/exception handling
-  Fixed timer not being stopped at the correct times
-  Tweaks to prevent exceptions and speed up rendering
-  Added Apache License statement to source files that didn't have it
   already

.. _final_p02_1.3.b85_released_2011_04_06:

1.3 Final p02 (1.3.b85; released 2011-04-06)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Easy to read update:

-  Added support for platform specific picture formats
-  Fixed hex grid movement
-  Bug Fixes

Patchlevel 02:

-  MRU campaign list wasn't being updated on OSX (flawed handling of
   special characters in campaign filenames fixed for all platforms).
-  Players dropping a token with a duplicate name now refuses to add the
   token at all (message to chat window).
-  Changed drag/drop handling again; split if-else into a series of IF
   statements.
-  Modified the token movement validation code to make debugging easier.
-  Added README to the **.maptool/resource** directory to warn users not
   to put their own files there!
-  Add warning when running MapTool on Java 5.
   http://forums.rptools.net/viewtopic.php?f=3&t=18045&p=190751#p190751
-  Revert call to String constructor that requires Java 6 (trying to
   keep MapTool as Java 5 compatible as possible).
-  Fix NPE when dragging tokens on hex map.
-  Added two Unix scripts to extract all possible logging objects
   directly from the source code (not directly useful for users).
-  Fixed some screenshot issues. However, no 100% fix is possible.
   http://forums.rptools.net/viewtopic.php?f=3&t=17984#p191059
-  Make **StackOverflow** messages look nicer and give the user a hint
   to solving it.
   http://forums.rptools.net/viewtopic.php?f=20&t=18089&p=191313#p191313
-  ConnectToServer reports error when the external address is used on
   the *Direct* tab.
   http://forums.rptools.net/viewtopic.php?f=3&t=12270&p=191318#p191318
-  Size limits on global macros are now reported if a saved macro is not
   read back as identical text.
   http://forums.rptools.net/viewtopic.php?f=20&t=18085&p=191317#p191317
-  **Edit>Clear Drawings** was always working on the Token layer instead
   of the currently selected layer; message box changed to report the
   layer to the user.
   http://forums.rptools.net/viewtopic.php?f=3&t=18151&p=192216#p192216
-  Loading a campaign now releases all drawables when only eraser
   drawables still remain after optimization.
-  Exporting campaign properties didn't properly save table images, so
   loading them later caused FileNotFound errors. Exported tables work
   fine. Related to this report?
   http://forums.rptools.net/viewtopic.php?f=21&t=15452&p=165978#p165955
-  Better handling of FileNotFound errors in general.
-  Fix for asset directory disappearing or not being accessible.
-  Add support for platform-specific image filetypes using conditional
   Java 6 code. On pre-Java 6 the list of filename extensions remains
   hard-coded to **gif**, **jpg**, **jpeg**, **bmp**, and **png** but
   Java 6 systems may have additional formats (**tiff** and **wbmp** are
   common).
-  Modified how performance data is reported by **Tools>Collect
   Performance Data**.
-  Renamed *README* to *README.wri* so it opens in Wordpad on Windows
   (it's still just an ordinary text file).
-  Movement on hex grids now checks properly for fog in both source and
   destination cells.
   http://forums.rptools.net/viewtopic.php?f=1&t=17914#p191030
-  Fix missing **Details** button of some exceptions.
-  Fix NPE bug in the States and Healthbar image handling.
-  Fix NPE bug when rendering tokens.
   http://forums.rptools.net/viewtopic.php?f=1&t=17914&p=193455#p193435
-  Fixed a NumberFormatException.
   http://forums.rptools.net/viewtopic.php?f=60&t=18288&p=193782#p193683
-  Some URLs still don't open properly when dropped on the map -- JRE
   bug?
-  Allow development version to have any client version connect to it
   (primarily for developer use).
-  Renamed PDF of documentation to match **MapToolLauncher.exe**.
-  Some fog performance issues cleaned up; hopefully less lag.
-  non-SnapToGrid tokens on hex map no longer snap to grid.
-  Add a comment to the chat window (and via popup) when fog toolbar is
   used the first time with no server running (a warning about using IF
   features with no server).
-  Add yes/no confirmation to clear fog when importing a map.
-  Holding down Shift when mousing over a token prevents stat sheet from
   being displayed (see window's statusbar help message).
-  Fixed how duplicate maps are named on import.
-  jay - InitiativePanel was not being handled properly during campaign
   load, causing the panel to be cleared sometimes.
-  jfrazierjr - updates to how fog is broken down into "global" vs.
   "token" and how they are merged for display purposes; small amount of
   other fog-related cleanup.
-  CoveredInFish - found a Java bug with the drag/drop support; not
   going to be fixed in 1.3. Drag the image to your desktop first, then
   from there to MapTool.
-  patoace - Spanish translation updated.

.. _final_p01_1.3.b84_released_2011_02_09:

1.3 Final p01 (1.3.b84; released 2011-02-09)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Patchlevel 01:

-  Fixed NPE when dragging a token on a gridless map (and certain
   conditions are met).
-  Updated documentation on Campaign Properties dialog **Light** tab.
-  Fixed NPE in setting token name regarding calling isTrusted().
-  Fix rendering of token names/labels on mouseover.
-  Removed dock badge from icon on OSX.
-  Fix bug with profiling window trying to open before main frame is
   open.
-  Fix NPE bug with moving token on gridless map.
-  Updated French translation (see credits)

.. _final_1.3.b83_released_2011_02_08:

1.3 Final (1.3.b83; released 2011-02-08)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Removed binary **Abeille** forms from SVN (not a user-visible
   change).
-  The *MapExplorer* was showing players too much information.
-  Resizing a rotated object image will ignore the Shift key (which
   constrains the size); I recommend setting the size first, then
   rotating.
-  Changing the token's image via the *EditTokenDialog* didn't update
   the token's native width/height.
-  Fixed "you are not the GM" dialog popping up during in a trusted
   function.
-  Fix bug in handling of non-existent images dropped onto a map (race
   condition).
-  Adding logging in *HTMLPane* to try to locate why mouseClick events
   are lost in frames.
-  Updated display of credits in the **About MapTool** dialog.
-  Added lots of comments to English translation file to describe how to
   do translations.
-  New Japanese translation added (based on SVN revision 5623 so very
   current).
-  Cause light sources and auras to be sorted alphabetically on the
   right-click menu.
-  Changed the algorithm that determines if a token may move into a
   particular location. Only works for square grids. New maps are
   constrained to a grid size of at least 9 pixels to support the new
   algorithm.
-  As part of the previous item, code has been refactored to make it
   easier to write similar algorithms for gridless and hex maps.
-  Added error trapping for corrupted campaign files to give users a
   better message.
-  Added data from the **Collect Performance Data** window to
   **log.txt** (must be enabled in the XML files that are part of the
   ZIP download).
-  Changed typing notification window status so it doesn't interfere
   with the mouse pointer shape when drawing VBL or templates.
-  Fix a couple of exceptions: IllegalStateException and add comment re:
   ConcurrentModificationException -
   http://forums.rptools.net/viewtopic.php?f=1&t=17651&p=187874#p187860
-  Added Meta-Shift-L as **Lock Player Movement** shortcut.
-  Fix token labels not appearing when moving a token in some cases.

.. _b82_rc5_released_2011_01_22:

1.3b82-RC5 (released 2011-01-22)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Fixed NPE when working with gridless maps and using the middle mouse
   button
   http://forums.rptools.net/viewtopic.php?f=1&t=17340&start=30#p184966
-  Changed the token editor dialog so that the *Size* dropdown field has
   the correct first entry (either or depending on whether the token is
   on the Token layer or another layer)
-  Fixed bug where the token editor dialog was only initializing the
   *Size* field once and populating it with the sizes for the grid type
   on that map so changing maps to a different grid type showed the
   wrong sizes!
-  Added the ability to double-click on the *Layout* panel image (on the
   token editor dialog's **Config** tab) to reset the position and zoom
-  Added a status bar message when the mouse enters the *Layout* panel
-  Fixed when multiple tokens with identical names are selected and a
   macro is executed that has ApplyToSelected active
   http://forums.rptools.net/viewtopic.php?f=1&t=17442&p=185550#p185550
-  Fixed bug in table handling that could cause an existing table to be
   deleted if it were to be renamed and had a syntax error in the range
   field, then the user **Cancel**-ed the dialog
-  Fixed text labels not appearing to players although they show up fine
   for the GM
-  Fixed MapExplorer showing NPC information that it didn't previously
-  Added support for the VisibleToOwnerOnly flag for drag/drop between
   CharacterTool and MapTool (implemented in MapTool only)
-  Removed small dot drawn at (0,0) by the RadiusTemplate (this bug goes
   back to at least 1.3b34!)
-  Token movement now occurs below fog so it's not visible to players
   unless the fog has been exposed
-  Data from "export screenshot" saved correctly in campaign file
   (previous fix was incomplete)
-  Fixed drag/drop of files from desktop onto map on Linux/OSX (now
   allows multiple files to be dropped at once)
-  Fix NPE when selected token is deleted by macro then moved by user
   without unselecting and re-selecting
-  Fix NPE when Impersonation panel tries to refresh without a map
   visible
-  Fix NPE when loading campaign from 1.3b45 (bug in macro button
   handling)
-  Change so the light source information is more detailed when is the
   topic being queried (should add somewhere as well)
-  Fix fog-of-war not being updated when a token was copy/pasted from
   another map
-  Entries in **i18n.properties** for slash commands now use the same
   key format as menu items (not a user-visible change)
-  All forms converted from **.jfrm** to **.xml** (not a user-visible
   change, but please report any display problems with dialog boxes)
-  Fix copy/paste of tokens so that relative offsets between tokens are
   preserved; works whether source or destination maps are gridless
-  Added audio feedback: **Copy** and **Cut** beep when no (owned)
   tokens are selected and **Paste** beeps if no tokens have yet been
   copied or cut
-  Change to allow token editor dialog's **Properties** tab to resize
   with the dialog window; this is a Java6-only change! We need a
   Java5-compatible method of doing this before **1.3 Final**
-  Halo colors are updated to the same list as button and font colors
-  aku - *huge* number of strings have been localized and now appear in
   the **i18n.properties** translation file
-  aPown - updated German translation
-  Natha - updated French translation
-  patoace - updated Spanish translation
-  (user?) - add new Japanese translation

.. _b81_rc4_released_2011_01_08:

1.3b81-RC4 (released 2011-01-08)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Clicking on server in **Connect To Server** dialog now copies server
   name to **Server Name** textfield
   http://forums.rptools.net/viewtopic.php?f=21&t=17346&p=184553#p184524
-  Change *Import Map* and *Export Map* to be always enabled and remove
   the checkbox from Preferences
-  *Export As...* settings are now persisted as part of the campaign
   (should be able to read old campaigns, although information will not
   be converted to the new dialog)
-  Updated macro font colors again; this time to compensate for color
   names that are unrecognized by CSS
-  Fixed typo in setLibProperty to correct Lib: tokens being copied
-  NPE fix
   http://forums.rptools.net/viewtopic.php?f=1&t=17340&p=184975#p184966
-  Added extra checks in assetpanel.Directory
   http://forums.rptools.net/viewtopic.php?f=3&t=17393#p184959
-  jfrazierjr - fix assignment for visibleOnlyToOwner field in token

.. _b80_rc3_released_2010_12_30:

1.3b80-RC3 (released 2010-12-30)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Fix bug similar to the one in b79 that prevents saved tokens from
   being loaded in some (most?) cases.
-  Fix copyToken's handling of hex grids
   http://forums.rptools.net/viewtopic.php?f=1&t=17331#p184385
-  Fix NPE (see SVN revision 5531 comment for details)
-  jfrazierjr - Individual FoW with Vision turned off (uncommitted
   patch)
-  Colors for macro button fonts weren't being recognized
-  Changed back to its previous definition

.. _b79_rc2_released_2010_12_29:

1.3b79-RC2 (released 2010-12-29)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Fix massive bug which prevented campaigns from being loaded
   http://forums.rptools.net/viewtopic.php?f=1&t=17329#p184351

.. _b78_rc1_released_2010_12_29:

1.3b78-RC1 (released 2010-12-29)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Fix handling of the font size for the macro buttons
   http://forums.rptools.net/viewtopic.php?f=21&t=17184#p183613
-  Start cleanup of code for hex grids by reverting meaning of so that
   old macros work again (sigh). We need regression tests written in
   MTscript!!
-  Fix token's (x,y) coords when snapToGrid is turned on (x,y coords
   were not being constrained to grid cell when snapToGrid was enabled).
   Hex grids appear to not snap correctly and never have;
   work-in-progress
   http://forums.rptools.net/viewtopic.php?f=60&t=16604&p=183236#p183223
-  Fix token.readResolve() so that pre-1.3b66 tokens (those without a
   CaseInsensitiveHashMap) can be read properly (warning: ugly backward
   compatibility code!)
-  Updated (and wiki) so that it checks for trusted context; includes
   small performance optimization
-  Fixed NPE in **InitiativeListCellRenderer.java** (line 174) so that
   the init panel doesn't try to render a token that doesn't exist
-  Menu option **Lock Zoom** didn't stop the -/= keys from zooming, only
   the mouse wheel
   http://forums.rptools.net/viewtopic.php?f=21&t=17192&p=183222#p183222
-  **Lock Zoom** also disables the zoom status bar field and **View >
   Zoom** menu options
-  Fixed bug when macro with used currentToken() which returned the same
   id multiple times when multiple tokens with the same name are
   selected
   http://forums.rptools.net/viewtopic.php?f=3&t=15904&p=169665#p169563
-  Fix not turning on **All Players**
-  Fix NPE in TokenImageOverlay when non-Boolean value is state value
   (shouldn't happen?)
-  MapExplorer did not check some token attributes correctly before
   adding to the various parts of the panel
-  Changed to for a couple of keys in the English translation file
   **i18n.properties**
-  Updated Polish translation (see the Credits inside MapTool)
-  Added Russian translation (see the Credits inside MapTool)

.. _b77_released_2010_12_07:

1.3b77 (released 2010-12-07)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Fixed error in check for number of parameters in
-  Added crosshairs to token editor dialog's Properties tab for the
   Layout image to allow easier alignment
   http://forums.rptools.net/viewtopic.php?f=26&t=14777
-  Fixed NPE caused when init panel was accessed after importing a map
   http://forums.rptools.net/viewtopic.php?f=3&t=15258&p=178021#p177947
-  Clients connecting to a server got the Campaign object from before
   the server was started?! Not sure this is actually fixed though.
   http://forums.rptools.net/viewtopic.php?f=21&t=16274&p=173423#p173423
-  Add support for variant fields to the autosave of the chatlog; for
   details see
   http://download.oracle.com/javase/1.5.0/docs/api/java/util/Formatter.html
   The default format is **chatlog-%1$tF-%1$tR.html** which produces a
   filename of the form **chatlog-YYYY-MM-DD-HH-MM.html** using a
   24-hour clock. Note that the filename is only evaluated once at
   startup or when the filename field is changed. We need some way of
   cleaning up old chatlogs as well.
-  Trim leading and trailing spaces from server names, passwords, player
   names, etc to prevent copy/paste errors for these fields
-  added field to the updates parameter of so that distances can be
   relative to the starting point
-  added field to and
   http://forums.rptools.net/viewtopic.php?f=20&t=16825&p=179535#p179535
-  Fixed **Light** tab of campaign properties dialog so that it displays
   the help screen properly
   http://forums.rptools.net/viewtopic.php?f=60&t=16604&p=180097#p180065
-  Fixed relative font sizes in macro editing by changing them to
   absolute sizes http://forums.rptools.net/viewtopic.php?f=21&t=16875
-  Changed button color and font color fields of the macro editor dialog
   to allow typed-in colors (still need ColorPicker and FontChooser for
   each)
-  Added default of to the font color in the macro editor dialog (value
   of for button color means a **null** background color)
-  Changed macro editor dialog to position the caret at the top of the
   command text area upon open
-  jfrazierjr - turn off Meta-Shift-O (fill in hard fog) for players
-  jfrazierjr - lots of Individual View work in combination with
   hard/soft fog of war **lots of testing needed!**
-  jfrazierjr/dorpond - added purple "blacklight" glow as a possible
   border; use yellow to indicate selected tokens when modifying group
   fog-of-war
-  CoveredInFish - Add support to for images to be set
   http://forums.rptools.net/viewtopic.php?f=26&t=15063
-  CoveredInFish - Add , ,
-  Gringoire - updated Italian translation
-  patoace - updated Spanish translation
-  Lukasz - created new Polish translation (work-in-progress)

.. _b76_released_2010_10_21:

1.3b76 (released 2010-10-21)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Added cleanup after saving resources (should help with "too many open
   files" error and with **.maptool/tmp** not being cleaned up properly)
-  The "Test Connection" button has been replaced with the "Network
   Help" button
-  The long-standing bug where the border around a selected token is
   drawn outside the map window is fixed!
-  Fixed Un*x start scripts to use **JAVA_HOME** if set; also fixed a
   typo in those scripts
-  jay - init panel no longer loses tokens that are dropped "outside"
   the area of the list
-  jfrazierjr/Rumble - fix for the "jumping template" bug; lots of
   testing needed.
-  jfrazierjr - MTscript functions for FoW manipulation ( and )
   http://forums.rptools.net/viewtopic.php?f=3&t=15950#p173912
-  jfrazierjr - Ignore client Preferences for FoW revealing
-  jfrazierjr - patch for ownerVisibleOnly setting on tokens
-  jfrazierjr - add movement metric to Start Server dialog to force it
   onto clients
-  jfrazierjr - added Lock Token Movement to the server policy(internal
   to the code) so that newly connected clients will get the value of
   the server's menu item checkbox.
-  jfrazierjr - added new move function: . This gets the last movement
   count in units using the movement metric defined by the server(see
   above for new server setting)
-  jfrazierjr - fixed path not showing to players when Use Individual
   Views is selected for tokens they do not own.
   http://forums.rptools.net/viewtopic.php?f=3&t=16451
-  CoveredInFish - patch to add **timeInMs** and **timeDate** to the
   MTscript function
-  CoveredInFish - patch for disabling macroLink tooltips in chat
-  Rumble - Selection Panel no longer repaints itself if it is not
   visible (performance improvement)
-  Rumble - building on the previous one, a new internal event was added
   that only fires on macro change which also speeds things up
-  patoace - new Spanish translation file

.. _b75_released_2010_09_27:

1.3b75 (released 2010-09-27)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Fix bug in return value of empty string for some MTscript functions
   that return JSON objects
   http://forums.rptools.net/viewtopic.php?f=21&t=16047&p=170771#p170765
-  Fix bug in which I/O streams were not being explicitly closed which
   caused "too many open files" error
   http://forums.rptools.net/viewtopic.php?f=21&t=16042&p=170772#p170685
-  Fix file handles being held after exporting data (this may be an
   on-going process but I think the majority of them have been caught)
-  Change the list of restricted characters in **AppHome** -- the only
   one specifically prohibited by Java is the **!** due to URLs using it
-  Fix to correctly check number of parameters
   http://forums.rptools.net/viewtopic.php?f=3&t=14823
-  Change **Test Connection** button on the **Start Server** dialog so
   that it gives the user a link to the NFAQ
   http://forums.rptools.net/viewtopic.php?f=1&t=16020&p=173003#p173003
-  Build rplib-1.0.b124 for distribution with MapTool (required by
   MetaGamer's work and other fixes)
-  whited - Fix how rotated images are resized -- not done yet?
   http://forums.rptools.net/viewtopic.php?f=21&t=13221
-  MetaGamer - add ability to export arbitrary size map screenshots;
   menu terminology still being discussed
   http://forums.rptools.net/viewtopic.php?f=7&t=15325
-  MetaGamer - added the **Map->Edit Map...** menu option for changing
   map parameters (lots of testing needed here)
-  jfrazierjr - Fixed CNTL+SHIFT+O to propagate to client's.
-  jfrazierjr - Fixed CNTL+SHIFT+O to enforce Server policy use
   individual views and not reveal FOW for non owned tokens
-  jfrazierjr - Finished up and functions
-  jfrazierjr - Added function.
-  jfrazierjr - various other small fixes

.. _b74_released_2010_09_07:

1.3b74 (released 2010-09-07)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  Change MapTool startup to check for bogus directory names (ones that
   contain punctuation for example)
   http://forums.rptools.net/viewtopic.php?f=4&t=15866#p169037
-  Fix tokens dropped from the Library panel: as GM they come in as
   their original type, as player they come in as PC
   http://forums.rptools.net/viewtopic.php?f=1&t=15817#p168884
-  Fix file I/O to properly use UTF-8 for all text-based resources
-  Modify UI property (for OSX) for Ctrl-Shift-O to ignore **'toggle
   component orientation**' (testing; if this works well it'll be added
   to Windows)
   http://forums.rptools.net/viewtopic.php?f=3&t=15326&p=163015#p163015
-  Modify UI properties (for OSX) so that Cmd-Left and Cmd-Right jump to
   beginning and end of line in text fields
-  jfrazierjr - *Visible to Owners Only* patch. Still needs MTscript
   support re: but also evaluation of how other script functions should
   change: , , etc.
   http://forums.rptools.net/viewtopic.php?f=26&t=15044&p=164509#p164163
-  jfrazierjr - *onTokenMove functions* patch. Still needs additional
   MTscript support. '''This feature should be considered beta and
   should only be used in a live game after very thorough testing. '''
   http://forums.rptools.net/viewtopic.php?f=3&t=15550
-  Fixed NPE in handling of Update/Delete/Move(Up|Down) when a health
   bar image isn't selected on the **'Bars**' tab of the campaign
   properties dialog
-  whited - Cleanup of warnings in rplib and maptool projects
-  whited - added JUnit tests for FileUtil and ModelVersionManager

1.3b73
~~~~~~

-  Fixed NullPointerException in new vision arc code
   http://forums.rptools.net/viewtopic.php?f=1&t=15817

1.3b72
~~~~~~

-  Fix sight types to be limited by the map settings by default
   http://forums.rptools.net/viewtopic.php?f=26&t=15549&p=165436#p165436
-  Vision arcs should only be visible to owners (if StrictOwner==true)
   or all PCs (if StrictOwner==false)
   http://forums.rptools.net/viewtopic.php?f=3&t=15790
-  The property 'macro.function.general.macro.function.number.invalid'
   wasn't defined in **i18n*.properties**
-  Updated macro script messages to include more information about
   errors
-  Add solution text to error message when out-of-memory error occurs
   while saving a campaign
   http://forums.rptools.net/viewtopic.php?f=3&t=15082#p160393
-  

   .. raw:: mediawiki

      {{func|getImpersonated}}

   now fails gracefully

-  

   .. raw:: mediawiki

      {{func|setPropertyType}}

   had bad parameter checking
   http://forums.rptools.net/viewtopic.php?f=1&t=14896#p160423

-  

   .. raw:: mediawiki

      {{func|getStrProp}}

   's wiki page was wrong (code was correct)

-  Fixed NullPointerExceptions with and similar (may not have gotten all
   of them) http://forums.rptools.net/viewtopic.php?f=20&t=15061#p160011
-  URLs should include the colon as valid in the path component (already
   fixed? MessagePanel.java)
-  Fix b71 bug by finishing rewrite of zip file I/O to handle
   localizations correctly (last set of fixes I hope!)
-  Fixed potential race condition with an autosave occurring while
   loading a campaign
-  When a campaign is loaded, set the map to the one that was current
   when the campaign was saved (bug was in AppActions.loadCampaign();
   does this work on clients now also?)
-  Add check for campaign file version number and alerts user when the
   version number is greater than the version of MT
   (ModelVersionManager.java for version number checks)
-  Found a few spots where Java I/O streams were not being closed
   immediately; could lead to inaccessible files on (broken) operating
   systems :)
-  Using the experimental "map import" feature could cause the
   initiative panel for the map to fail repeatedly; importing a map now
   correctly clears the initiative panel entirely

1.3b71
~~~~~~

-  Java 5 does not have String.isEmpty() started a poll because MANY of
   the libraries use this method :-/ In the mean time references to Java
   6 methods have been culled from the main MT source as much as
   possible
-  Wrong parameter count check for and
   http://forums.rptools.net/viewtopic.php?f=12&t=12516&p=158796
-  Updated Italian translation by Gringoire
-  

   .. raw:: mediawiki

      {{func|createMacro}}

   now properly takes 5 parameters (was only 4)
   http://forums.rptools.net/viewtopic.php?f=21&t=15108&start=0

-  

   .. raw:: mediawiki

      {{func|hasMacro}}

   wasn't accepting a second parameter correctly
   http://forums.rptools.net/viewtopic.php?f=21&t=15098&p=160584#p160502

-  Comments in campaign property types ("-----") still cause warnings
   when doing the case-insensitive comparison of property names but the
   message is hopefully better
   http://forums.rptools.net/viewtopic.php?f=53&t=15041&p=160469#p160469
-  (incomplete) Multilanguage support
   http://forums.rptools.net/viewtopic.php?f=26&t=14608#p156184
-  (incomplete) Need UTF-8 specification when reading/writing XML
   http://forums.rptools.net/viewtopic.php?f=26&t=15022
-  Jfrazierjr - patch to provide owner-only auras (overridden by "gm"
   when both flags are provided) campaign file save format has changed
-  Jfrazierjr - patch for queuing of chat notifications on-screen
   http://forums.rptools.net/viewtopic.php?f=26&t=8690&start=0
-  Rumble - chat notification moved to client-side
-  Updated campaign file version number to 1.3.70 (so that campaigns
   created in b70+ won't be loadable by earlier version due to
   Light.ownerOnly)

1.3b70
~~~~~~

-  Add trusted macro for (done by Craig in b69)
-  Rectangles drawn with zero width/height are removed and not added to
   the map (http://forums.rptools.net/viewtopic.php?f=21&t=14793)
-  Preferences dialog is clearer regarding how map defaults are only for
   new maps (http://forums.rptools.net/viewtopic.php?f=3&t=14797)
-  NPE due to stacked tokens on a map (not sure how an NPE happens
   though? http://forums.rptools.net/viewtopic.php?f=21&t=14865)
-  Drag/drop of filesystem objects (finished?
   http://forums.rptools.net/viewtopic.php?f=3&t=14068&p=154991)
-  Added help info for GM-only auras to the Abeille form for the
   Campaign Properties dialog
-  Craig - fixed bug in added by Azhrei :(
   (http://forums.rptools.net/viewtopic.php?f=3&t=14823)
-  Craig - added and a "campaign" parameter for the script function
-  Craig - fixed bug on "image" input type in html forms not working
   (http://forums.rptools.net/viewtopic.php?f=21&t=14789)
-  Craig - added "closeFrame()" function
   (http://forums.rptools.net/viewtopic.php?p=157814#p157814)
-  

   .. raw:: mediawiki

      {{func|getPropertyNames}}

   checked for the wrong number of parameters

-  Rumble - select unowned tokens patch

1.3b69
~~~~~~

-  When loading a campaign referenced assets are not found; assets are
   not saved when the asset isn't there
-  Fixed bug with MacroButtonProperties when saving to the GlobalPanel
   as a Player connected to a server
   (http://forums.rptools.net/viewtopic.php?f=1&t=14644&p=155439)
-  Fixed bug displaying macro button dialog in situation similar to
   above
-  Iain - Fix to allow code to compile on Eclipse when not running on
   OSX (http://forums.rptools.net/viewtopic.php?f=1&t=14644&p=156024)
-  Using Meta-Shift-O resets all fog so that only currently visible
   areas are exposed and everything else is hard fog
-  Rumble's chat notifier moved to upper left corner of map (overlay
   color can be set in Preferences)
-  Rumble's select-unowned-tokens patch
-  change Random() to SecureRandom()
-  Craig - added `getInfo <getInfo>`__\ () function

1.3b68
~~~~~~

-  Change Wiki: resetProperty() so that the property is actually removed
   from the token
-  A lot of token-related macro functions were cleaned up to ensure that
   they cause the token to be sent to other machines when modified.
   (example: http://forums.rptools.net/viewtopic.php?f=21&t=14139)
-  Add Preferences option that enables the map load/save menu options
   with the requisite "Are You Sure?" prompt when the checkbox is
   enabled.
-  Finished the autosave code for the chat log
-  Updated Italian translation
-  Ability to turn the map import/export feature on/off via a checkbox
   in Preferences (still considered a "beta" feature)
-  More updates to Rumble's select-unowned-tokens patch
-  Added support for changing the OSX dock icon inside MapTool (one more
   step towards eliminating the shell scripts)

1.3b67
~~~~~~

-  Added code to disable performance counters when the corresponding
   logger is turned off (might save us a few cpu cycles here and there)
-  Fix for autosave race condition (moved variable to avoid concurrency
   issues when an autosave occurs during a regular File > Save Campaign)
-  Fixed drawings on Hidden layer being "above" tokens on the same layer
   (should be below;
   http://forums.rptools.net/viewtopic.php?f=3&t=14344)
-  Some bug fixes for importing maps (correct GUID in Zone, for example;
   http://forums.rptools.net/viewtopic.php?f=3&t=11676&p=150989#p150989).
   Import/export feature still requires special command line parameter
   to enable. It'll become a Preferences setting in the next build.
-  Problem with importing a token macro with accented characters in it
   (http://forums.rptools.net/viewtopic.php?f=1&t=14322&p=151741#p151609;
   fix required restructuring PackedFile.putFile() methods)
-  Remove redundant entries from the resource library list upon startup,
   and prevent redundant entries from being saved
-  getTokenX() should return a BigDecimal value
   (http://forums.rptools.net/viewtopic.php?f=20&t=14546#p154261)
-  Assets marked as "broken" in the campaign file were not restored
   properly; warnings added to the log file -- change to popup box to
   alert GM instead?
-  Patch for turning on word wrapping in textareas (kkragenbrink)
-  Patch for preventing token names from being empty (Rumble)
-  Token stacks allow access to incorrect token (reported by aliasmask;
   fixed by Rumble)
-  Selection of unowned tokens is always allowed, even when Strict Token
   Ownership is enabled on the Start Server dialog (Rumble;
   http://forums.rptools.net/viewtopic.php?f=3&t=14547) this patch
   didn't make it into b67 :(
-  Chat notifiers -- messages that indicate someone else is typing
   (Rumble;
   http://forums.rptools.net/viewtopic.php?f=3&t=14355&start=45#p152754)
-  Four different opacity levels on Preferences dialog (halo, aura,
   light, fog). This effectively allows removal of soft fog by
   specifying a value of 255 for "fog".
-  Updated the German translation (aPown)
-  Updated Spanish translation (patoace)

1.3b66
~~~~~~

-  Deal with 64-bit vs. 32-bit JVMs

1.3b65
~~~~~~

-  Tooltips fixed on the Sound tab of the Preferences dialog (had text
   copied from other fields)
-  Add equals sign to URL parsing (following URL now parses correctly:
   http://forums.rptools.net/viewtopic.php?f=20&t=14274&view=unread#unread)
-  Macro tab removed from the Token Editor dialog (an old Abeille form
   snuck back in)
-  getPropertyType() again accepts a single default parameter (typo in
   parameter counting)
-  Short names for properties are no longer "variables" in MTscript, but
   still evaluate on the statsheet
-  Fixed map importing (internal data wasn't being updated)
-  Another stab at fixing assets being saved in binary but allowing
   loading in binary and XML

1.3b64
~~~~~~

-  Add confirmation dialog to right-click macro menu Reset option
-  Add check to Campaign Properties to disallow property names that
   differ only in their case
-  Add getPropertyNamesRaw new macro script function which returns mixed
   case variable names
-  Cleaned up all parameter checking in all of the macro token property
   functions (new translations needed).
-  Assets in RPToks are no longer being written out as MIME64 encoded
   text; instead they are binary images. Need lots of testing on this
   one for backward-compatibility
-  Don't merge old assets from PackedFile into new PackedFile. This
   should fix RPTOKs growing larger each time they're saved.
-  Remove the Macro tab and all references to macros on the token editor
   dialog
-  Disable the rest of the UI while the Test Connection is doing its
   thing
-  Change ImagePanel vertical scrollbar so that the BlockIncrement moves
   by an entire page height/width, minus one row; UnitIncrement is
   exactly one row
-  Fix URL regex's so that links pasted into the chat window grab the
   entire URL
-  Modify wording of Preferences->Application regarding auto-exposing
   fog
-  Added tooltips to every label on all four tabs of the Preferences
   dialog
-  fixed the problem with the fog of war paint getting reset back to
   black when a server is started (cheesethulu)
-  fixed the problem with players momentarily getting a GM view when
   they disconnect (cheesethulu)
-  support for GM-only auras (woohoo!) (jfrazier)
-  French translation updated (simonutp)
-  Spanish translation updated (patoace)
-  Italian translation updated (Gringoire)

1.3b63
~~~~~~

-  Fix bug: server locks up when player disconnects unexpectedly
-  Fix bug: typo in UPnP error message (Azhrei)
-  Update Spanish translation (Patricio)
-  Update French translation (Pierre)
-  Update German translation (aPown)
