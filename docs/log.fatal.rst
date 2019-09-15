.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=log.fatal
   |trusted=true
   |version=1.5.2
   |description=
   Writes a message to the log at the FATAL logging level. Use {{func|log.setLevel}} to set the appropriate level for the {{code|macro-logger}}.

   |usage=
   <source lang="mtmacro" line>
   log.fatal(message)
   </source>
   '''Parameters'''
   {{param|message|A string containing the message to be logged.}}

   |example=
   Output a message to the {{code|macro-logger}} at the FATAL level.

   <source lang="mtmacro" line>
   [h: log.fatal("Well I'd say she certainly had marvelous judgement, Albert, if not particularly good taste.")]
   </source>
   '''Returns:'''

   Empty string to calling macro.  Output is in log file.
   <source lang="mtmacro" line>
   1975-03-15 09:19:22.846 [AWT-EventQueue-0] FATAL macro-logger - Well I'd say she certainly had marvelous judgement, Albert, if not particularly good taste.</source>
   |also=
   {{func|log.getLoggers}}  {{func|log.setLevel}}

   }}

`Category:Log Function <Category:Log_Function>`__
