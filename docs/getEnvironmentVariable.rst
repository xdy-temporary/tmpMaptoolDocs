.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name= getEnvironmentVariable
   |trusted=true
   |version=1.5.0
   |description=Retrieves an operating system environment variable as a string.

   This function is useful for situations where the script may wish to interact with the environment outside of MapTool, such as using the {{func|exportData}} function to write a string to an external file.

   {{Caution|This function is considered experimental and its implementation and parameters may change.}}

   The '''Allow External Macro Access''' option on the Application tab of MapTool's Preferences must be enabled or this macro aborts with an error.

   |usage=
   <source lang="mtmacro" line>
   getEnvironmentVariable(varname)
   </source>

   The value of {{code|varname}} specifies which environment variable is queried.  On most operating systems, environment variables are all uppercase letters, but this is a naming convention and not required.  Note that no way exists to query what all of the environment variables are, so the script writer must know which variable they want to retrieve.

   |example=
   You can use the following code to print the value of the PATH environment variable (which exists on most systems).  Knowing the list of directories where an operating system searches for compiled executables could be considered a security vulnerability.  See the above note about the '''Allow External Macro Access''' option.
   <source lang="mtmacro" line>
   [getEnvironmentVariable("PATH")]
   </source>
   }}

`Category:Miscellaneous Function <Category:Miscellaneous_Function>`__
