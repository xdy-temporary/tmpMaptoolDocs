.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=listFormat
   |description=
   Returns a custom-formatted version of the list.

   |usage=
   <source lang="mtmacro" line>
   [ listFormat(list, listFormat, itemFormat, separator) ]
   [ listFormat(list, listFormat, itemFormat, separator, delim) ]
   </source>
   * listFormat is a string that is emitted once. It should contain the text "%list", which is replaced with the formatted items.
   * itemFormat is emitted once per item. Each instance of "%item" in the string is replaced with the value of the list item.
   * separator is emitted in between the formatted items.

   |example=
   <source lang="mtmacro" line>
   [ listFormat("apple,bear,cat", "BEGIN LIST<br>%list<br>END LIST", "This item is: %item", "<br>") ]
   </source>
   (prints items on separate lines)

   Convert a string list to html list:<source lang="mtmacro" line>
   [R: listFormat( "apple, bear, cat", "<ul>%list</ul>", "<li>%item</li>", "" ) ]
   </source>
   Produces:<ul>
   <li>apple</li>
   <li>bear</li>
   <li>cat</li>
   </ul>


   Create an option list input (drop-down list selection) for an html form, with the names of selected tokens:
   <source lang="mtmacro" line>
   [R: listFormat( getSelectedNames( "%%" ), 
       "<select name='test'>%list</select>", 
       "<option value='%item'>%item</option>", 
       "",  
       "%%" ) 
   ]
   </source>
   The first argument is the list, returned by {{func|getSelectedNames}}: it has a delimiter specified ("%%"), to avoid PC names with commas or anything other than "%%" from appearing as more than one item.  The second argument specifies html (text) to go around the entire formatted ''list'', and the third is html to wrap around each ''item'' in the list.  The fourth argument is blank (empty), since no separator between items is needed in this case.  The fifth argument is usually optional, but in this case is the same delimiter specified in getSelectedNames(), to allow listFormat to find each item in the list.
   }}

`Category:String List Function <Category:String_List_Function>`__
