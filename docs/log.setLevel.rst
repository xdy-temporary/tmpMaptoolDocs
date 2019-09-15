.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=log.setLevel
   |trusted=true
   |version=1.5.2
   |description=
   Set the logging level for the specified logger.

   <br>The log file will be found in your user directory under {{code|.maptool-rptools/logs}}.
   |usage=
   <source lang="mtmacro" line>
   log.setLevel(logger, loglevel)
   </source>
   '''Parameters'''
   {{param|logger|String containing a logger name.}}
   {{param|loglevel|String containing a log level: DEBUG,INFO,WARN,ERROR,FATAL}}

   The default level for all loggers is ERROR which means that only messages at ERROR or FATAL log level will be output.  The levels noted above are in verbosity order from most(DEBUG) to least(FATAL).

   |example=
   Set the logging level for the MapToolLineParser to '''WARN'''.
   <source lang="mtmacro" line>
   [r: log.setLevel("net.rptools.maptool.client.MapToolLineParser","WARN")]
   </source>
   '''Returns:'''
   <source lang="mtmacro" line>
   WARN
   </source>

   Get a list of loggers and then, using {{func|input}}, select a logging level for it.
   <source lang="mtmacro" line>
   [h: loggers = json.sort(log.getLoggers(),"a","name")]
   [h: loggerList = ""]
   [h, FOREACH(logger, loggers), CODE: {
       [h: loggerList = listAppend(loggerList,json.get(logger,"name"))]
   }]
   [h:status=input(
       "junkVar|Select a Logger and Level||LABEL|SPAN=TRUE",
       "lname|"+loggerList+"|Logger|LIST|VALUE=STRING",
       "level|DEBUG,INFO,WARN,ERROR,FATAL|Level|LIST|VALUE=STRING")]
   [h:abort(status)]
   [r: "Setting <i><b>" + lname + "</b></i> to <b>" + level + "</b>."]
   [h: log.setLevel(lname,level)]
   </source>
   <br/>
   [[File:SelectLoggerLevel.png|File:SelectLoggerLevel.png]]

   |also=
   {{func|log.getLoggers}}   [[Available_Loggers|Available Loggers]]
   }}

`Category:Log Function <Category:Log_Function>`__
