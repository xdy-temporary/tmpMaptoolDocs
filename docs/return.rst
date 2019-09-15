.. contents::
   :depth: 3
..

{{MacroFunction \|name=return \|version=1.5.0 \|description=

Is used to conditionally return from the execution of a macro like an
abort, but not stopping further macro execution. Optionally also
returning a value by automatically assigning
`macro.return <macro.return>`__. If the first argument to is 0 then the
return is happening. If the first argument to is non zero then the macro
continues. The optional second argument of defines if there is a value
that should be returned to a calling macro. Any other output is
discarded when using .

Common uses for this function are

-  Ending a macro with or without a return value to stop the further
   execution of the following lines in the current macro.
-  The macro has conditions and based on these you want to return
   different values and not continue further in the current macro.

If you prefer to display an error message when exiting the macro see the
`{{code <assert>`__ function or if you want to abort the flow of overall
macro execution (e.g. in case of an error) see the [[abort\|

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
