.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{RollOption
   |name=frame
   |description=
   Opens a frame window.  Unlike the modeless {{roll|dialog}}, frames are dockable panels that are usually intended to remain open.  Frames can be closed with a button located in the title bar or via the [[closeDialog|closeDialog()]] macro function.

   |usage=
   <source lang="mtmacro" line>
   [h: frame(frameName [,"width; height; temporary; title; tabtitle; value"] )]
   </source>

   The first parameter, shown as '''frameName''', should be a double-quoted string that specifies the internal name of the frame window.  The visible title that appears in the title bar of the window is set separately, either by using HTML that appears inside the frame itself or use of the '''title''' parameter from b50 forward.  Any attempts to open another frame with the same name instead cause the old contents to be removed and new contents displayed.  Note this behavior relates to the internal name of the frame, not the displayed title of the frame as multiple frames can share a title.  Once the named frame is opened and resized by the user, that size becomes its default opening size in the future, unless the temporary option is set to "1".


   The second parameter is optional, it is a semicolon separated [[String_Property_List|String Property List]], which could include the following options:

   The '''temporary''' option dictates whether Maptool remembers the size of the frame between displays.  Setting this value to 1 causes Maptool to forget the window size.  Example "temporary=1"

   The '''title''' option sets the title of the frame and replaces the need to set the title from within the HTML code.

   The '''tabtitle''' is the title shown when the frame is minimized. If not used as a parameter, the tabtitle is the same as the frame's title.

   The '''width''' and '''height''' options determine the (initial) size of the frame. Depending whether '''temporary''' has been set or not the frame will always open with these dimensions.

   The last parameter is '''value'''. It can be used to store some data inside the frame. For example, if a frame display the equipment of a character, the value parameter can be set to the token id of that character, so that you can know which character's equipment is being displayed. 

   Prior to 1.5.4, using the '''title''' parameter when opening up a new frame could break the frame. Calls to the macro after closing the frame would not show the frame. This was remedied by adding a line to the calling macro before running the macro. The line below could be used, substituting your own frame name.
   <source lang="mtmacro" line>
   [ if( isFrameVisible("YourFrame") ), code: {}; { [resetFrame("YourFrame")] } ]
   </source>
   This checks if the bugged frame is visible or not. If the frame is open it does nothing, but if it is closed it resets the frame, which forces it to be shown. The bug is fixed from 1.5.4 onward.

   |examples=
   Sample header
   <source lang="mtmacro" line>
   [frame("Frame Test", "width=300; height=200; temporary=1;"): {
   </source>

   The following code opens up a frame that contains the HTML as shown here:
   <table>
   <tr>
   <td>
   [[Image:FrameDemo.png|Image:FrameDemo.png]]
   </td>
   <td>
   <source lang="mtmacro" line>
   [frame("Frame Test"): {
     <html>
       <head>
         <title>Test of Frame Windows</title>
       </head>
       <body>
       <table border="1">
       <tr><th>Column 1</th><th>Column 2</th><th>Column 3</th></tr>
       <tr><td>Line 1, Col 1</td><td colspan="2">Line 1, Cols 2 and 3</td></tr>
       <tr><td rowspan="2">Lines 2 and 3, Col 1</td><td>Line 2, Col 2</td><td>Line 2, Col 3</td></tr>
       <tr><td>Line 3, Col 3</td><td>Line 3, Col 3</td></tr>
       </table>
       </body>
     </html>
   } ]
   </source>
   </td>
   </tr>
   </table>

   |also=
   {{roll|dialog}} <br>
   {{func|isFrameVisible}} <br>
   [[Introduction_to_Dialogs_and_Frames|Introduction to Dialogs and Frames]]<br>
   [[Forms_tutorial|Forms tutorial]]

   |changes=
   {{change|1.3b50|Added '''title''' parameter option.}}
   {{change|1.5.4|Added '''temporary''', '''tabtitle''' and '''value''' parameter options.}}

   }}

`Category:Display Roll Option <Category:Display_Roll_Option>`__
`Category:Frame Function <Category:Frame_Function>`__
