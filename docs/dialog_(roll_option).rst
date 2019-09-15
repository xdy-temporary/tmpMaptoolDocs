.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{RollOption
   |name=dialog
   |description=Opens a dialog window.  This window can be named; attempts to open another dialog with the same name cause the old contents to be removed and new contents displayed.  The initial size of the dialog can be specified as well, but once the named dialog is opened and resized by the user, that size becomes its default opening size in the future.

   Dialogs are not dockable panels as a {{roll|frame}} is.  Dialogs also have at least one button for dismissing the dialog.

   |usage=
   <source lang="mtmacro" line>
   [h, dialog(dialogName [,size; input; temporary; title; noframe; value] )]
   </source>

   The first parameter, shown as '''dialogName''', should be a double-quoted string that specifies the internal name of the dialog window.  (Note that the title that appears in the titlebar of the window is set separately, using HTML that appears inside the dialog itself.) (use '''title''' parameter from b50 forward)

   The second parameter is optional, it is a semicolon separated [[String_Property_List|String Property List]], which could include the following parameters:

   The '''size''' parameter is a [[String_Property_List|String Property List]] that contains two values, ''width'' and ''height''.  Those values can be measured in pixels ('''px''' and the default) or other HTML units, such as ems ('''em''') or screen width percentages ('''%''').

   The following parameters work from v1.3b50 forward:

   The '''input''' parameter dictates whether the dialog has a ''close'' button or is closed with an <input submit> button custom coded into the dialog.  '''input''' is set to 1 or 0 within double quotes.  example: "input=1"

   The '''temporary''' parameter dictates whether Maptool remembers the size of the dialog window between displays.  Setting this value to 1 causes Maptool to forget the window size.  Example "temporary=1"

   The '''noframe''' parameter dictates whether the window has a frame or not.  Example "noframe=1" removes the frame from the dialog window.

   The '''title''' parameter sets the title of the dialog box and replaces the need to set the title from within the HTML code.

   The following parameter work from 1.5.4 forward:

   The '''value''' parameter associates arbitrary data to the frame. The data can be recovered through the [[getDialogProperties|getDialogProperties]] function.

   |examples=
   The following code opens up a dialog window that contains the HTML as shown here:

   [[Image:DialogEx1.png|Image:DialogEx1.png]]

   <source lang="mtmacro" line>
   [dialog("Dialog Test"): {
     <html>
       <head>
         <title>Test of Dialog Windows</title>
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

   To create a dialog that initially opens with a width of 300 pixels and height of 200 pixels, change the first line of the previous example to:
   <source lang="mtmacro" line>
   [dialog("Dialog Test", "width=300; height=200; temporary=1; input=0; noframe=1"): {
   </source>

   Did you try it?  It didn't change size from the previous example, did it?  Do you remember why?  If not, go back to the top of the page and read that first paragraph again!
   }}

`Category:Display Roll Option <Category:Display_Roll_Option>`__