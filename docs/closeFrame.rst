.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=closeFrame
   |version=1.3b70
   |description=Closes the specified macro frame that was previously created using {{roll|frame}}. If the 
   frame is not open then the function has no effect. 

   The most common use for this function is closing a frame based from a macro that is run when clicking on a link or button for the 
   frame that has no close button. 

   '''NOTE''' this function can not close dialogs opened with {{roll|dialog}}. Use {{func|closeDialog}} for that.

   |usage=
   <source lang="mtmacro" line>
   [h: closeFrame(name)]
   </source>
   }}

`Category:Frame Function <Category:Frame_Function>`__
