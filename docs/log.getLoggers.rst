.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{MacroFunction
   |name=exampleFunction
   |trusted=true
   |version=1.5.2
   |description=
   Returns a JSON array of available loggers and the current logging level for each.

   |usage=
   <source lang="mtmacro" line>
   log.getLoggers()
   </source>
   '''Parameters'''
   None.

   |example=
   Get a list of available loggers and format the JSON result.
   <source lang="mtmacro" line>
   <pre>[r: json.indent(log.getLoggers())]</pre>
   </source>
   Returns:
   <source lang="javascript" line>

   [
           {
           "name": "macro-logger",
           "level": "ERROR"
       },
           {
           "name": "net.rptools.lib.io.PackedFile",
           "level": "ERROR"
       },
           {
           "name": "net.rptools.maptool.client.swing.AbeillePanel",
           "level": "ERROR"
       },
       ...
   ]
   </source>

   |also=
   [[log.setLevel|log.setLevel]]

   }}

`Category:Log Function <Category:Log_Function>`__
