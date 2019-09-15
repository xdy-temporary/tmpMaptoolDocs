.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=log.warn
   |trusted=true
   |version=1.5.2
   |description=
   Writes a message to the log file at the WARN logging level. Use {{func|log.setLevel}} to set the appropriate level for the {{code|macro-logger}}.

   |usage=
   <source lang="mtmacro" line>
   log.warn(message)
   </source>
   '''Parameters'''
   {{param|message|A string containing the message to be logged.}}

   |example=
   Output a message to the {{code|macro-logger}} at the WARN level.

   <source lang="mtmacro" line>
   [h: log.warn("Go away or I shall taunt you a second time!")]
   </source>
   '''Returns:'''

   Empty string to calling macro.  Output is in log file.
   <source lang="mtmacro" line>
   1975-03-14 08:59:39.211 [AWT-EventQueue-0] WARN  macro-logger - Go away or I shall taunt you a second time!
   </source>
   |also=
   {{func|log.getLoggers}}  {{func|log.setLevel}}

   }}

`Category:Log Function <Category:Log_Function>`__
