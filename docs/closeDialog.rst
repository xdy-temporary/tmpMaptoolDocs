.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=closeDialog
   |version=1.3b49
   |description=Closes the specified macro dialog that was previously created using {{roll | dialog}}.  If the 
   [[dialog|dialog]] is not open then the function has no effect. 

   The most common use for this function is closing a [[dialog|dialog]] based from a macro that is run when clicking on a link or button for the 
   [[dialog|dialog]] that has no close button. 

   '''NOTE''' In later versions of maptool (tested in b74) this works only for dialogs opened with {{roll|dialog}}. Frames cant be closed with this. But there is a new analog function available for that, too. See {{func|closeFrame}}


   |usage=
   <source lang="mtmacro" line>
   [h: closeDialog(name)]
   </source>

   |example=
   <source lang="mtmacro" line>
   [h: closeDialog("CharacterSheet")]  
   </source>

   Assuming a [[dialog|dialog]] called "Name Entry" has been created without the input flag but containing a form. In the macro called when the
   form is submitted you can use the following logic to check that the "name" field is not blank and close the [[dialog|dialog]].
   <source lang="mtmacro" line>
   [h, if(listGet(macro.args, "name")), code: {
       [closeDialog("Name Entry")]
   } ; {
       <!-- otherwise we would do something here to tell the user to provide a name -->
   }]
   </source>
   }}

`Category:Dialog Function <Category:Dialog_Function>`__
