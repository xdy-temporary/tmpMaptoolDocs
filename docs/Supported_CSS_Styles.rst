.. contents::
   :depth: 3
..

MapTool supports a subset of the CSS level 1 specification. These styles
can be used in-line, and also as external styles within dialogs and
frames. This is not meant to be an exhaustive reference, nor an
introduction to CSS, this page is only a collection of which properties
are supported and to what extent. If you are looking for an introduction
to CSS, visit `W3Schools CSS
Tutorial <http://www.w3schools.com/css/css_intro.asp>`__

Also, note that some CSS attributes are modeled but not rendered,
meaning that they can be used and will be recognized, they just won't
have any effect on the rendered result. The list is available straight
from the Java documentation: `CSS
Styles <https://docs.oracle.com/javase/8/docs/api/javax/swing/text/html/CSS.html>`__

.. _font_properties:

Font Properties
===============

font
----

================== =======================================================
**Value:**         font-style, font-weight, font-size, font-family
**Initial:**       none
**Applies To:**    all elements
**Inherited:**     yes
**Relative Size:** only font-size
**Example:**       .. code:: css
                  
                      font: bold italic 12pt Arial, Helvetica, sans-serif;
================== =======================================================

.. _font_family:

font-family
-----------

================== =============================================
**Value:**         *family-name*, *generic-name*
**Initial:**       system default
**Applies To:**    all elements
**Inherited:**     yes
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      font-family: Arial, Helvetica, sans-serif;
================== =============================================

.. _font_size:

font-size
---------

================== ========================================================
**Value:**         *absolute-size*, *relative-size*, *length*, *percentage*
**Initial:**       medium
**Applies To:**    all elements
**Inherited:**     yes
**Relative Size:** relative to parent element's font-size
**Example:**       .. code:: css
                  
                      font-size: 12pt;
================== ========================================================

.. _font_style:

font-style
----------

================== =======================
**Value:**         normal, italic, oblique
**Initial:**       normal
**Applies To:**    all elements
**Inherited:**     yes
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      font-style: italic;
================== =======================

.. _font_weight:

font-weight
-----------

================== ==========================================================================
**Value:**         normal, bold, bolder, lighter, 100, 200, 300, 400, 500, 600, 700, 800, 900
**Initial:**       normal
**Applies To:**    all elements
**Inherited:**     yes
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      font-weight: bold;
================== ==========================================================================

.. _color_and_background_properties:

Color and Background Properties
===============================

color
-----

================== ==========================
**Value:**         *color name*, *color code*
**Initial:**       element specific
**Applies To:**    all elements
**Inherited:**     yes
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      color: #FF0000;
================== ==========================

background
----------

================== =========================================================================================
**Value:**         background-color, background-image, background-repeat, background-position
**Initial:**       none
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      background: #0000FF url(asset://de05e42d2eb43fe53a542db116da8083) no-repeat right top;
================== =========================================================================================

.. _background_color:

background-color
----------------

================== =============================
**Value:**         *color name*, *color code*
**Initial:**       transparent
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      background-color: #0000FF;
================== =============================

.. _background_image:

background-image
----------------

================== ===================================================================
**Value:**         none, *url*
**Initial:**       none
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      background-image: url(asset://de05e42d2eb43fe53a542db116da8083);
================== ===================================================================

.. _background_repeat:

background-repeat
-----------------

================== =====================================
**Value:**         repeat, repeat-x, repeat-y, no-repeat
**Initial:**       repeat
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      background-repeat: no-repeat;
================== =====================================

.. _background_position:

background-position
-------------------

================== ========================================
**Value:**         top, center, bottom, left, center, right
**Initial:**       top left
**Applies To:**    block-level and replaced elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      background-position: bottom right;
================== ========================================

.. _text_properties:

Text Properties
===============

.. _text_align:

text-align
----------

================== =====================
**Value:**         left, right, center
**Initial:**       element specific
**Applies To:**    block-level elements
**Inherited:**     yes
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      text-align: right;
================== =====================

.. _text_decoration:

text-decoration
---------------

================== =================================
**Value:**         none, underline, line-through
**Initial:**       none
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      text-decoration: line-through;
================== =================================

.. _vertical_align:

vertical-align
--------------

================== =========================
**Value:**         baseline, sub, super
**Initial:**       baseline
**Applies To:**    inline elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      vertical-align: super;
================== =========================

.. _box_properties:

Box Properties
==============

.. _border_style:

border-style
------------

================== =======================
**Value:**         none, inset, outset
**Initial:**       none
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      border-style: inset;
================== =======================

margin
------

================== ================
**Value:**         *length*, auto
**Initial:**       none
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      margin: 10px;
================== ================

.. _margin_top:

margin-top
----------

================== ====================
**Value:**         *length*, auto
**Initial:**       0
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      margin-top: 10px;
================== ====================

.. _margin_right:

margin-right
------------

================== ======================
**Value:**         *length*, auto
**Initial:**       0
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      margin-right: 10px;
================== ======================

.. _margin_bottom:

margin-bottom
-------------

================== =======================
**Value:**         *length*, auto
**Initial:**       0
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      margin-bottom: 10px;
================== =======================

.. _margin_left:

margin-left
-----------

================== =====================
**Value:**         *length*, auto
**Initial:**       0
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      margin-left: 10px;
================== =====================

padding
-------

================== =================
**Value:**         *length*
**Initial:**       0
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      padding: 10px;
================== =================

.. _padding_top:

padding-top
-----------

================== =====================
**Value:**         *length*
**Initial:**       0
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      padding-top: 10px;
================== =====================

.. _padding_right:

padding-right
-------------

================== =======================
**Value:**         *length*
**Initial:**       0
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      padding-right: 10px;
================== =======================

.. _padding_bottom:

padding-bottom
--------------

================== ========================
**Value:**         *length*
**Initial:**       0
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      padding-bottom: 10px;
================== ========================

.. _padding_left:

padding-left
------------

================== ======================
**Value:**         *length*
**Initial:**       0
**Applies To:**    all elements
**Inherited:**     no
**Relative Size:** no
**Example:**       .. code:: css
                  
                      padding-left: 10px;
================== ======================

.. _classification_properties:

Classification Properties
=========================

.. _list_style_type:

list-style-type
---------------

================== =======================================================================================
**Value:**         none, disc, circle, square, decimal, lower-roman, upper-roman, lower-alpha, upper-alpha
**Initial:**       disc
**Applies To:**    list-item elements
**Inherited:**     yes
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      list-style-type: square;
================== =======================================================================================

.. _list_style_position:

list-style-position
-------------------

================== ===============================
**Value:**         inside, outside
**Initial:**       outside
**Applies To:**    list-item elements
**Inherited:**     yes
**Relative Size:** N/A
**Example:**       .. code:: css
                  
                      list-style-position: inside;
================== ===============================

`Category:Macro <Category:Macro>`__
