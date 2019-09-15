.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=log.info
   |trusted=true
   |version=1.5.2
   |description=
   Writes a message to the log file at the INFO logging level. Use {{func|log.setLevel}} to set the appropriate level for the {{code|macro-logger}}.

   |usage=
   <source lang="mtmacro" line>
   log.info(message)
   </source>
   '''Parameters'''
   {{param|message|A string containing the message to be logged.}}

   |example=
   Output a message to the {{code|macro-logger}} at the INFO level.

   <source lang="mtmacro" line>
   [h: log.info("There's no place like home.")]
   </source>
   '''Returns:'''

   Empty string to calling macro.  Output is in log file.
   <source lang="mtmacro" line>
   1939-08-25 09:19:22.844 [AWT-EventQueue-0] INFO  macro-logger - There's no place like home.
   </source>
   |also=
   {{func|log.getLoggers}}  {{func|log.setLevel}}

   }}

`Category:Log Function <Category:Log_Function>`__
