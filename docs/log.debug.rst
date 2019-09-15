.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=log.debug
   |trusted=true
   |version=1.5.2
   |description=
   Writes a message to the log at the DEBUG logging level. Use {{func|log.setLevel}} to set the appropriate level for the {{code|macro-logger}}.

   |usage=
   <source lang="mtmacro" line>
   log.debug(message)
   </source>
   '''Parameters'''
   {{param|message|A string containing the message to be logged.}}

   |example=
   Output a message to the {{code|macro-logger}} at the DEBUG level.

   <source lang="mtmacro" line>
   [h: log.debug("Switched to map " + getCurrentMapName())]
   </source>
   '''Returns:'''

   Empty string to calling macro.  Output is in log file.
   <source lang="mtmacro" line>
   1987-09-25 08:52:18.853 [AWT-EventQueue-0] DEBUG macro-logger - Switched to map Pit of Despair
   </source>
   |also=
   {{func|log.getLoggers}}  {{func|log.setLevel}}

   }}

`Category:Log Function <Category:Log_Function>`__
