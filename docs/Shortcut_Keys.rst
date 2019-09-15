.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Shortcut Keys}}

Most of the Shortcut Keys in Maptool 1.3b76+ can be found in the menu;
some however are not listed. These "stealth" keys are marked in
*italic*.

Here is a comprehensive list of all known keystrokes. Most keystrokes
require that the map window have the keyboard focus.

Note that **Meta** means **Ctrl** on Windows and Linux, and **Cmd** on
OSX. Also note that most of these can be changed in the translation
files, so these settings are primarily for the English locale.

.. _lightvision_related:

Light/Vision Related
====================

================ ===================================================================================
Keystroke        Description
================ ===================================================================================
**Meta+K**       Toggle display of light source icons
**Meta+I**       Clear fog visible by selected token(s)
**Meta+P**       Clear fog visible by selected token(s) along last moved path
**Meta+Shift+O** Restore fog-of-war to entire map except area currently visible to selected token(s)
**Meta+W**       Toggle fog-of-war on/off (GM only)
================ ===================================================================================

.. _drawing_tools_related:

Drawing Tools Related
=====================

========================= ======================================
Keystroke                 Description
========================= ======================================
**Meta+LeftMouseButton**  Snap to grid while drawing
**Alt+LeftMouseButton**   Draw from centre (vs corner to corner)
**Shift+LeftMouseButton** Erase
========================= ======================================

.. _map_related:

Map Related
===========

================== ==========================================================
Keystroke          Description
================== ==========================================================
**Spacebar**       Show a pointer (arrow) on the map
**Meta+Spacebar**  Show a pointer (talk-balloon)
**Shift+Spacebar** Show a pointer (think-balloon)
**Spacebar**       Adds a waypoint while moving (as does middle mouse button)
**Meta+G**         Toggle grid on/off (current client only)
**Meta+Shift+S**   Create screenshot
**Meta+Shift+D**   Clear all drawings
**Meta+Z**         Undo last drawing
**Meta+R**         Redo last drawing (only when drawing tool is active)
**Meta+Alt+Enter** Toggle full screen map
**=**              Set zoom to 1:1 and back on second press
**-**              Zoom out
**+**              Zoom in
**Z**              (keep it pressed) inverse mouse scroll zoom
**Meta+H**         Toggle map (in)visible to player(s) (GM only)
**Meta+Shift+A**   Grid settings (spacing, alignment, color) (GM only)
**Meta+N**         New map (GM only)
**Meta+Shift+P**   Toggle player view (GM only)
**Meta+Shift+F**   Center players on current view continuously (GM only)
**Meta+F**         Center players on current view (GM only)
**Meta+E**         Force players to current map (GM only)
================== ==========================================================

.. _token_related:

Token Related
=============

============================================ ===============================================================================================================================================================================================================================================================================================
Keystroke                                    Description
============================================ ===============================================================================================================================================================================================================================================================================================
**Meta+T**                                   Toggle token name display.
**T**                                        select next token (Shift=previous) on map.
Digits on numeric keypad                     Move in the direction of the digit (7=NW, 9=NE, 1=SW, 3=SE).
**D**, **NumPad5**, or **Home**              Drop selected tokens after moving (when using arrow keys).
**Shift+MouseWheel**                         Rotate facing of token. **MouseWheel_Up** = clockwise. **Ctrl**\ =rotate by 1 degree. Otherwise angle controlled by **Preferences**. When the token is set to **TOP_DOWN** (double-click on token > **Config** tab > **Shape**) the whole token will rotate instead of the yellow facing arrow.
**Shift+LeftArrow** and **Shift+RightArrow** On *TOKEN* layer: Same as **Shift+MouseWheel**: rotate token.
                                            
                                             On all other layers: Move token per pixel instead of per cell.
**Meta+R**                                   Turn on token facing. With a mouse click set the facing in the direction of the mouse pointer. Angle controlled as for **Shift+MouseWheel**. Use **Delete** to remove facing.
**Shift+MouseOver**                          Mouseover on a token normally displays a statsheet; holding down **Shift** turns off the statsheet.
============================================ ===============================================================================================================================================================================================================================================================================================

.. _chat_related:

Chat Related
============

See `Chat Commands <Chat_Commands>`__ for specifics on the **/**
commands.

============== ===========================================
Keystroke      Description
============== ===========================================
**/**          Macro command (press **Enter** to complete)
**Meta+Enter** Toggle chat frame visibility
============== ===========================================

Standard
========

========== =====================
Keystroke  Description
========== =====================
**Meta+O** Open Campaign File...
**Meta+S** Save Campaign
**Meta+A** Save Campaign As...
**Meta+X** Cut (tokens only)
**Meta+C** Copy (tokens only)
**Meta+V** Paste (tokens only)
========== =====================

`Category:MapTool <Category:MapTool>`__
