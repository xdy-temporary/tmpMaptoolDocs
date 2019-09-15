.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=formatStrProp
   |description=Returns a custom-formatted version of the property string.

   |usage=
   <source lang="mtmacro" line>
   [h: formatStrProp(props, listFormat, entryFormat, separator) ]
   </source>
   * listFormat is a string that is emitted once. It should contain the text "%list", which is replaced with the formatted items.
   * entryFormat is emitted once per item. Any instances of "%key" and "%value" in the string are replaced with the key or value for that setting.
   * separator is emitted in between the formatted items.

   |example=
   <source lang="mtmacro" line>
   [h: props = "Strength=14 ; Constitution=8 ; Dexterity=13 ; Intelligence=4 ; Wisdom=18 ; Charisma=9"]
   [formatStrProp(props, "<table border=1>%list</table>", "<tr> <td><b>%key</b></td> <td>%value</td> </tr>", "")]  
   </source>

   Outputs:

   <table border=1>
   <tr><td><b>Strength</b></td><td>14</td></tr>
   <tr><td><b>Constitution</b></td><td>8</td></tr>
   <tr><td><b>Dexterity</b></td><td>13</td></tr>
   <tr><td><b>Intelligence</b></td><td>4</td></tr>
   <tr><td><b>Wisdom</b></td><td>18</td></tr>
   <tr><td><b>Charisma</b></td><td>9</td></tr>
   </table>

   }}

`Category:String Property List
Function <Category:String_Property_List_Function>`__
