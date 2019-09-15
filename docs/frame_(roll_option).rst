================================
frame (roll option) - MapToolDoc
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

   .. rubric:: frame (roll option)
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

            -  `1 [frame():] Roll
               Option <#.5Bframe.28.29:.5D_Roll_Option>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 See Also <#See_Also>`__
               -  `1.4 Version Changes <#Version_Changes>`__

         .. rubric:: [frame():] Roll Option
            :name: frame-roll-option

         Opens a frame window. Unlike the modeless
         `[dialog():] </rptools/wiki/dialog_(roll_option)>`__, frames
         are dockable panels that are usually intended to remain open.
         Frames can be closed with a button located in the title bar or
         via the `closeDialog() </rptools/wiki/closeDialog>`__ macro
         function.

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: frame(frameName [,"width; height; temporary; title; tabtitle; value"] )]

         The first parameter, shown as **frameName**, should be a
         double-quoted string that specifies the internal name of the
         frame window. The visible title that appears in the title bar
         of the window is set separately, either by using HTML that
         appears inside the frame itself or use of the **title**
         parameter from b50 forward. Any attempts to open another frame
         with the same name instead cause the old contents to be removed
         and new contents displayed. Note this behavior relates to the
         internal name of the frame, not the displayed title of the
         frame as multiple frames can share a title. Once the named
         frame is opened and resized by the user, that size becomes its
         default opening size in the future, unless the temporary option
         is set to "1".

         | 
         | The second parameter is optional, it is a semicolon separated
           `String Property
           List </rptools/wiki/String_Property_List>`__, which could
           include the following options:

         The **temporary** option dictates whether Maptool remembers the
         size of the frame between displays. Setting this value to 1
         causes Maptool to forget the window size. Example "temporary=1"

         The **title** option sets the title of the frame and replaces
         the need to set the title from within the HTML code.

         The **tabtitle** is the title shown when the frame is
         minimized. If not used as a parameter, the tabtitle is the same
         as the frame's title.

         The **width** and **height** options determine the (initial)
         size of the frame. Depending whether **temporary** has been set
         or not the frame will always open with these dimensions.

         The last parameter is **value**. It can be used to store some
         data inside the frame. For example, if a frame display the
         equipment of a character, the value parameter can be set to the
         token id of that character, so that you can know which
         character's equipment is being displayed.

         Prior to 1.5.4, using the **title** parameter when opening up a
         new frame could break the frame. Calls to the macro after
         closing the frame would not show the frame. This was remedied
         by adding a line to the calling macro before running the macro.
         The line below could be used, substituting your own frame name.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [ if( isFrameVisible("YourFrame") ), code: {}; { [resetFrame("YourFrame")] } ]

         This checks if the bugged frame is visible or not. If the frame
         is open it does nothing, but if it is closed it resets the
         frame, which forces it to be shown. The bug is fixed from 1.5.4
         onward.

         .. rubric:: Examples
            :name: examples

         Sample header

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [frame("Frame Test", "width=300; height=200; temporary=1;"): {

         The following code opens up a frame that contains the HTML as
         shown here:

         +-----------------------------------+-----------------------------------+
         | |FrameDemo.png|                   | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container::                 |
         |                                   |    mtmacro source-mtmacro         |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |             [frame("Frame Test"): |
         |                                   |  {                                |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |               <html>              |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |                 <head>            |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |                   <title>Test of  |
         |                                   | Frame Windows</title>             |
         |                                   |                                   |
         |                                   |       #. .. code:: de2            |
         |                                   |                                   |
         |                                   |                 </head>           |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |                 <body>            |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |                 <table border="1" |
         |                                   | >                                 |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |                 <tr><th>Column 1< |
         |                                   | /th><th>Column 2</th><th>Column 3 |
         |                                   | </th></tr>                        |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |                 <tr><td>Line 1, C |
         |                                   | ol 1</td><td colspan="2">Line 1,  |
         |                                   | Cols 2 and 3</td></tr>            |
         |                                   |                                   |
         |                                   |       #. .. code:: de2            |
         |                                   |                                   |
         |                                   |                 <tr><td rowspan=" |
         |                                   | 2">Lines 2 and 3, Col 1</td><td>L |
         |                                   | ine 2, Col 2</td><td>Line 2, Col  |
         |                                   | 3</td></tr>                       |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |                 <tr><td>Line 3, C |
         |                                   | ol 3</td><td>Line 3, Col 3</td></ |
         |                                   | tr>                               |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |                 </table>          |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |                 </body>           |
         |                                   |                                   |
         |                                   |       #. .. code-block:: none            |
         |                                   |                                   |
         |                                   |               </html>             |
         |                                   |                                   |
         |                                   |       #. .. code:: de2            |
         |                                   |                                   |
         |                                   |             } ]                   |
         +-----------------------------------+-----------------------------------+

         .. rubric:: See Also
            :name: see-also

         | `[dialog():] </rptools/wiki/dialog_(roll_option)>`__
         | `isFrameVisible() </rptools/wiki/isFrameVisible>`__
         | `Introduction to Dialogs and
           Frames </rptools/wiki/Introduction_to_Dialogs_and_Frames>`__
         | `Forms tutorial </rptools/wiki/Forms_tutorial>`__

         .. rubric:: Version Changes
            :name: version-changes

         -  **1.3b50** - Added **title** parameter option.
         -  **1.5.4** - Added **temporary**, **tabtitle** and **value**
            parameter options.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=frame_(roll_option)&oldid=7584"

