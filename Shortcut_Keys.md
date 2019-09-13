Most of the Shortcut Keys in Maptool 1.3b76+ can be found in the menu;
some however are not listed. These "stealth" keys are marked in
*italic*.

Here is a comprehensive list of all known keystrokes. Most keystrokes
require that the map window have the keyboard focus.

Note that **Meta** means **Ctrl** on Windows and Linux, and **Cmd** on
OSX. Also note that most of these can be changed in the translation
files, so these settings are primarily for the English locale.

## Light/Vision Related

| Keystroke        | Description                                                                         |
| ---------------- | ----------------------------------------------------------------------------------- |
| **Meta+K**       | Toggle display of light source icons                                                |
| **Meta+I**       | Clear fog visible by selected token(s)                                              |
| **Meta+P**       | Clear fog visible by selected token(s) along last moved path                        |
| **Meta+Shift+O** | Restore fog-of-war to entire map except area currently visible to selected token(s) |
| **Meta+W**       | Toggle fog-of-war on/off (GM only)                                                  |

## Drawing Tools Related

| Keystroke                 | Description                            |
| ------------------------- | -------------------------------------- |
| **Meta+LeftMouseButton**  | Snap to grid while drawing             |
| **Alt+LeftMouseButton**   | Draw from centre (vs corner to corner) |
| **Shift+LeftMouseButton** | Erase                                  |

## Map Related

| Keystroke          | Description                                                |
| ------------------ | ---------------------------------------------------------- |
| **Spacebar**       | Show a pointer (arrow) on the map                          |
| **Meta+Spacebar**  | Show a pointer (talk-balloon)                              |
| **Shift+Spacebar** | Show a pointer (think-balloon)                             |
| **Spacebar**       | Adds a waypoint while moving (as does middle mouse button) |
| **Meta+G**         | Toggle grid on/off (current client only)                   |
| **Meta+Shift+S**   | Create screenshot                                          |
| **Meta+Shift+D**   | Clear all drawings                                         |
| **Meta+Z**         | Undo last drawing                                          |
| **Meta+R**         | Redo last drawing (only when drawing tool is active)       |
| **Meta+Alt+Enter** | Toggle full screen map                                     |
| **=**              | Set zoom to 1:1 and back on second press                   |
| **-**              | Zoom out                                                   |
| **+**              | Zoom in                                                    |
| **Z**              | (keep it pressed) inverse mouse scroll zoom                |
| **Meta+H**         | Toggle map (in)visible to player(s) (GM only)              |
| **Meta+Shift+A**   | Grid settings (spacing, alignment, color) (GM only)        |
| **Meta+N**         | New map (GM only)                                          |
| **Meta+Shift+P**   | Toggle player view (GM only)                               |
| **Meta+Shift+F**   | Center players on current view continuously (GM only)      |
| **Meta+F**         | Center players on current view (GM only)                   |
| **Meta+E**         | Force players to current map (GM only)                     |

## Token Related

<table>
<thead>
<tr class="header">
<th><p>Keystroke</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Meta+T</strong></p></td>
<td><p>Toggle token name display.</p></td>
</tr>
<tr class="even">
<td><p><strong>T</strong></p></td>
<td><p>select next token (Shift=previous) on map.</p></td>
</tr>
<tr class="odd">
<td><p>Digits on numeric keypad</p></td>
<td><p>Move in the direction of the digit (7=NW, 9=NE, 1=SW, 3=SE).</p></td>
</tr>
<tr class="even">
<td><p><strong>D</strong>, <strong>NumPad5</strong>, or <strong>Home</strong></p></td>
<td><p>Drop selected tokens after moving (when using arrow keys).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Shift+MouseWheel</strong></p></td>
<td><p>Rotate facing of token. <strong>MouseWheel_Up</strong> = clockwise. <strong>Ctrl</strong>=rotate by 1 degree. Otherwise angle controlled by <strong>Preferences</strong>. When the token is set to <strong>TOP_DOWN</strong> (double-click on token &gt; <strong>Config</strong> tab &gt; <strong>Shape</strong>) the whole token will rotate instead of the yellow facing arrow.</p></td>
</tr>
<tr class="even">
<td><p><strong>Shift+LeftArrow</strong> and <strong>Shift+RightArrow</strong></p></td>
<td><p>On <em>TOKEN</em> layer: Same as <strong>Shift+MouseWheel</strong>: rotate token.</p>
<p>On all other layers: Move token per pixel instead of per cell.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Meta+R</strong></p></td>
<td><p>Turn on token facing. With a mouse click set the facing in the direction of the mouse pointer. Angle controlled as for <strong>Shift+MouseWheel</strong>. Use <strong>Delete</strong> to remove facing.</p></td>
</tr>
<tr class="even">
<td><p><strong>Shift+MouseOver</strong></p></td>
<td><p>Mouseover on a token normally displays a statsheet; holding down <strong>Shift</strong> turns off the statsheet.</p></td>
</tr>
</tbody>
</table>

## Chat Related

See [Chat Commands](Chat_Commands "wikilink") for specifics on the **/**
commands.

| Keystroke      | Description                                 |
| -------------- | ------------------------------------------- |
| **/**          | Macro command (press **Enter** to complete) |
| **Meta+Enter** | Toggle chat frame visibility                |

## Standard

| Keystroke  | Description           |
| ---------- | --------------------- |
| **Meta+O** | Open Campaign File... |
| **Meta+S** | Save Campaign         |
| **Meta+A** | Save Campaign As...   |
| **Meta+X** | Cut (tokens only)     |
| **Meta+C** | Copy (tokens only)    |
| **Meta+V** | Paste (tokens only)   |

[Category:MapTool](Category:MapTool "wikilink")