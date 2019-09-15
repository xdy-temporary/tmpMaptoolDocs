.. contents::
   :depth: 3
..

The RESTful macro functions in MapTool are for advanced users. This is
merely an overview of the MapTool implementation of RESTful functions
and not a tutorial covering REST and REST APIs. Those can be readily
found on the web such as `REST API
Tutorial <https://restfulapi.net/>`__.

.. _what_is_rest:

What is REST?
=============

REST is acronym for REpresentational State Transfer. It is an
architectural style for distributed hypermedia systems and was first
presented by Roy Fielding in 2000 in his `famous
dissertation <https://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm>`__.

(*Definition from tutorial linked above.*)

.. _maptool_rest_operations:

MapTool REST Operations
=======================

MapTool supports the following REST requests:

-  Get -
-  Post -
-  Put -
-  Patch -
-  Delete -

See the entry for each macro function for details about their use.

.. _rest_status_codes:

REST Status Codes
=================

Each request can return the server response or a full response with data
typically in a XML or JSON format. Note that XML data can be more easily
processed using (the prefix is but it's a general purpose function).

The full response will include a status code. A partial list of status
codes:

=== ===========
200 OK
201 Created
202 Accepted
204 No Content
400 Bad Request
404 Not Found
=== ===========
