.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=log.error
   |trusted=true
   |version=1.5.2
   |description=
   Writes a message to the log file at the ERROR logging level. Use {{func|log.setLevel}} to set the appropriate level for the {{code|macro-logger}}.

   |usage=
   <source lang="mtmacro" line>
   log.error(message)
   </source>
   '''Parameters'''
   {{param|message|A string containing the message to be logged.}}

   |example=
   Output a message to the {{code|macro-logger}} at the ERROR level.

   <source lang="mtmacro" line>
   [h: log.error(getPlayerName() + " chose poorly")]
   </source>
   '''Returns:'''

   Empty string to calling macro.  Output is to log file.
   <source lang="mtmacro" line>
   1989-05-24 08:13:32.911 [AWT-EventQueue-0] ERROR macro-logger - Bob chose poorly.
   </source>
   |also=
   {{func|log.getLoggers}}  {{func|log.setLevel}}

   }}

`Category:Log Function <Category:Log_Function>`__
