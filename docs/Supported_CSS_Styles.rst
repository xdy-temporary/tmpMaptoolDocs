=================================
Supported CSS Styles - MapToolDoc
=================================

.. contents::
   :depth: 3
..

.. container:: noprint
   :name: mw-page-base

.. container:: noprint
   :name: mw-head-base

.. container:: mw-body
   :name: content

   .. container:: mw-indicators

   .. rubric:: Supported CSS Styles
      :name: firstHeading
      :class: firstHeading

   .. container:: mw-body-content
      :name: bodyContent

      .. container::
         :name: siteSub

         From MapToolDoc

      .. container::
         :name: contentSub

      .. container:: mw-jump
         :name: jump-to-nav

         Jump to: `navigation <#mw-head>`__, `search <#p-search>`__

      .. container:: mw-content-ltr
         :name: mw-content-text

         .. container:: template_advanced

            ADVANCED
            THIS IS AN ADVANCED ARTICLE

         MapTool supports a subset of the CSS level 1 specification.
         These styles can be used in-line, and also as external styles
         within dialogs and frames. This is not meant to be an
         exhaustive reference, nor an introduction to CSS, this page is
         only a collection of which properties are supported and to what
         extent. If you are looking for an introduction to CSS, visit
         `W3Schools CSS
         Tutorial <http://www.w3schools.com/css/css_intro.asp>`__

         Also, note that some CSS attributes are modeled but not
         rendered, meaning that they can be used and will be recognized,
         they just won't have any effect on the rendered result. The
         list is available straight from the Java documentation: `CSS
         Styles <https://docs.oracle.com/javase/8/docs/api/javax/swing/text/html/CSS.html>`__

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Font Properties <#Font_Properties>`__

               -  `1.1 font <#font>`__
               -  `1.2 font-family <#font-family>`__
               -  `1.3 font-size <#font-size>`__
               -  `1.4 font-style <#font-style>`__
               -  `1.5 font-weight <#font-weight>`__

            -  `2 Color and Background
               Properties <#Color_and_Background_Properties>`__

               -  `2.1 color <#color>`__
               -  `2.2 background <#background>`__
               -  `2.3 background-color <#background-color>`__
               -  `2.4 background-image <#background-image>`__
               -  `2.5 background-repeat <#background-repeat>`__
               -  `2.6 background-position <#background-position>`__

            -  `3 Text Properties <#Text_Properties>`__

               -  `3.1 text-align <#text-align>`__
               -  `3.2 text-decoration <#text-decoration>`__
               -  `3.3 vertical-align <#vertical-align>`__

            -  `4 Box Properties <#Box_Properties>`__

               -  `4.1 border-style <#border-style>`__
               -  `4.2 margin <#margin>`__
               -  `4.3 margin-top <#margin-top>`__
               -  `4.4 margin-right <#margin-right>`__
               -  `4.5 margin-bottom <#margin-bottom>`__
               -  `4.6 margin-left <#margin-left>`__
               -  `4.7 padding <#padding>`__
               -  `4.8 padding-top <#padding-top>`__
               -  `4.9 padding-right <#padding-right>`__
               -  `4.10 padding-bottom <#padding-bottom>`__
               -  `4.11 padding-left <#padding-left>`__

            -  `5 Classification
               Properties <#Classification_Properties>`__

               -  `5.1 list-style-type <#list-style-type>`__
               -  `5.2 list-style-position <#list-style-position>`__

         .. rubric:: Font Properties
            :name: font-properties

         .. rubric:: font
            :name: font

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | font-style, font-weight,          |
         |                                   | font-size, font-family            |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | none                              |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | yes                               |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | only font-size                    |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          font: bold italic 12pt A |
         |                                   | rial, Helvetica, sans-serif;      |
         +-----------------------------------+-----------------------------------+

         .. rubric:: font-family
            :name: font-family

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *family-name*, *generic-name*     |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | system default                    |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | yes                               |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          font-family: Arial, Helv |
         |                                   | etica, sans-serif;                |
         +-----------------------------------+-----------------------------------+

         .. rubric:: font-size
            :name: font-size

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *absolute-size*, *relative-size*, |
         |                                   | *length*, *percentage*            |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | medium                            |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | yes                               |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | relative to parent element's      |
         |                                   | font-size                         |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          font-size: 12pt;         |
         +-----------------------------------+-----------------------------------+

         .. rubric:: font-style
            :name: font-style

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | normal, italic, oblique           |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | normal                            |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | yes                               |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          font-style: italic;      |
         +-----------------------------------+-----------------------------------+

         .. rubric:: font-weight
            :name: font-weight

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | normal, bold, bolder, lighter,    |
         |                                   | 100, 200, 300, 400, 500, 600,     |
         |                                   | 700, 800, 900                     |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | normal                            |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | yes                               |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          font-weight: bold;       |
         +-----------------------------------+-----------------------------------+

         .. rubric:: Color and Background Properties
            :name: color-and-background-properties

         .. rubric:: color
            :name: color

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *color name*, *color code*        |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | element specific                  |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | yes                               |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          color: #FF0000;          |
         +-----------------------------------+-----------------------------------+

         .. rubric:: background
            :name: background

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | background-color,                 |
         |                                   | background-image,                 |
         |                                   | background-repeat,                |
         |                                   | background-position               |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | none                              |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          background: #0000FF url( |
         |                                   | asset://de05e42d2eb43fe53a542db11 |
         |                                   | 6da8083) no-repeat right top;     |
         +-----------------------------------+-----------------------------------+

         .. rubric:: background-color
            :name: background-color

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *color name*, *color code*        |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | transparent                       |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          background-color: #0000F |
         |                                   | F;                                |
         +-----------------------------------+-----------------------------------+

         .. rubric:: background-image
            :name: background-image

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | none, *url*                       |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | none                              |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          background-image: url(as |
         |                                   | set://de05e42d2eb43fe53a542db116d |
         |                                   | a8083);                           |
         +-----------------------------------+-----------------------------------+

         .. rubric:: background-repeat
            :name: background-repeat

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | repeat, repeat-x, repeat-y,       |
         |                                   | no-repeat                         |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | repeat                            |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          background-repeat: no-re |
         |                                   | peat;                             |
         +-----------------------------------+-----------------------------------+

         .. rubric:: background-position
            :name: background-position

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | top, center, bottom, left,        |
         |                                   | center, right                     |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | top left                          |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | block-level and replaced elements |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          background-position: bot |
         |                                   | tom right;                        |
         +-----------------------------------+-----------------------------------+

         .. rubric:: Text Properties
            :name: text-properties

         .. rubric:: text-align
            :name: text-align

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | left, right, center               |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | element specific                  |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | block-level elements              |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | yes                               |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          text-align: right;       |
         +-----------------------------------+-----------------------------------+

         .. rubric:: text-decoration
            :name: text-decoration

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | none, underline, line-through     |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | none                              |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          text-decoration: line-th |
         |                                   | rough;                            |
         +-----------------------------------+-----------------------------------+

         .. rubric:: vertical-align
            :name: vertical-align

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | baseline, sub, super              |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | baseline                          |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | inline elements                   |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          vertical-align: super;   |
         +-----------------------------------+-----------------------------------+

         .. rubric:: Box Properties
            :name: box-properties

         .. rubric:: border-style
            :name: border-style

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | none, inset, outset               |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | none                              |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          border-style: inset;     |
         +-----------------------------------+-----------------------------------+

         .. rubric:: margin
            :name: margin

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*, auto                    |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | none                              |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          margin: 10px;            |
         +-----------------------------------+-----------------------------------+

         .. rubric:: margin-top
            :name: margin-top

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*, auto                    |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | 0                                 |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          margin-top: 10px;        |
         +-----------------------------------+-----------------------------------+

         .. rubric:: margin-right
            :name: margin-right

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*, auto                    |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | 0                                 |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          margin-right: 10px;      |
         +-----------------------------------+-----------------------------------+

         .. rubric:: margin-bottom
            :name: margin-bottom

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*, auto                    |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | 0                                 |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          margin-bottom: 10px;     |
         +-----------------------------------+-----------------------------------+

         .. rubric:: margin-left
            :name: margin-left

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*, auto                    |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | 0                                 |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          margin-left: 10px;       |
         +-----------------------------------+-----------------------------------+

         .. rubric:: padding
            :name: padding

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*                          |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | 0                                 |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          padding: 10px;           |
         +-----------------------------------+-----------------------------------+

         .. rubric:: padding-top
            :name: padding-top

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*                          |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | 0                                 |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          padding-top: 10px;       |
         +-----------------------------------+-----------------------------------+

         .. rubric:: padding-right
            :name: padding-right

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*                          |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | 0                                 |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          padding-right: 10px;     |
         +-----------------------------------+-----------------------------------+

         .. rubric:: padding-bottom
            :name: padding-bottom

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*                          |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | 0                                 |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          padding-bottom: 10px;    |
         +-----------------------------------+-----------------------------------+

         .. rubric:: padding-left
            :name: padding-left

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | *length*                          |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | 0                                 |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | all elements                      |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | no                                |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | no                                |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          padding-left: 10px;      |
         +-----------------------------------+-----------------------------------+

         .. rubric:: Classification Properties
            :name: classification-properties

         .. rubric:: list-style-type
            :name: list-style-type

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | none, disc, circle, square,       |
         |                                   | decimal, lower-roman,             |
         |                                   | upper-roman, lower-alpha,         |
         |                                   | upper-alpha                       |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | disc                              |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | list-item elements                |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | yes                               |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          list-style-type: square; |
         +-----------------------------------+-----------------------------------+

         .. rubric:: list-style-position
            :name: list-style-position

         +-----------------------------------+-----------------------------------+
         | **Value:**                        | inside, outside                   |
         +-----------------------------------+-----------------------------------+
         | **Initial:**                      | outside                           |
         +-----------------------------------+-----------------------------------+
         | **Applies To:**                   | list-item elements                |
         +-----------------------------------+-----------------------------------+
         | **Inherited:**                    | yes                               |
         +-----------------------------------+-----------------------------------+
         | **Relative Size:**                | N/A                               |
         +-----------------------------------+-----------------------------------+
         | **Example:**                      | .. container::                    |
         |                                   | mw-geshi mw-code mw-content-ltr   |
         |                                   |                                   |
         |                                   |    .. container:: css source-css  |
         |                                   |                                   |
         |                                   |       .. code:: de1               |
         |                                   |                                   |
         |                                   |          list-style-position: ins |
         |                                   | ide;                              |
         +-----------------------------------+-----------------------------------+

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Supported_CSS_Styles&oldid=7446"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Categories </rptools/wiki/Special:Categories>`__:

            -  `Macro </rptools/wiki/Category:Macro>`__
            -  `Advanced </rptools/wiki/Category:Advanced>`__

         --------------

         `Advanced </rptools/wiki/Category:Advanced>`__
         `MapTool </rptools/wiki/Category:MapTool>`__ >
         `Macro </rptools/wiki/Category:Macro>`__

      .. container:: visualClear

.. container::
   :name: mw-navigation

   .. rubric:: Navigation menu
      :name: navigation-menu

   .. container::
      :name: mw-head

      .. container::
         :name: p-personal

         .. rubric:: Personal tools
            :name: p-personal-label

         -  `Log
            in </maptool/index.php?title=Special:UserLogin&returnto=Supported+CSS+Styles>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Supported_CSS_Styles>`__
            -  `Discussion </maptool/index.php?title=Talk:Supported_CSS_Styles&action=edit&redlink=1>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-variants

            .. rubric:: Variants\ ` <#>`__
               :name: p-variants-label

            .. container:: menu

      .. container::
         :name: right-navigation

         .. container:: vectorTabs
            :name: p-views

            .. rubric:: Views
               :name: p-views-label

            -  `Read </rptools/wiki/Supported_CSS_Styles>`__
            -  `View
               source </maptool/index.php?title=Supported_CSS_Styles&action=edit>`__
            -  `View
               history </maptool/index.php?title=Supported_CSS_Styles&action=history>`__

         .. container:: vectorMenu emptyPortlet
            :name: p-cactions

            .. rubric:: More\ ` <#>`__
               :name: p-cactions-label

            .. container:: menu

         .. container::
            :name: p-search

            .. rubric:: Search
               :name: search

            .. container::
               :name: simpleSearch

   .. container::
      :name: mw-panel

      .. container::
         :name: p-logo

         ` </rptools/wiki/Main_Page>`__

      .. container:: portal
         :name: p-navigation

         .. rubric:: Navigation
            :name: p-navigation-label

         .. container:: body

            -  `Main page </rptools/wiki/Main_Page>`__
            -  `Random page </rptools/wiki/Special:Random>`__
            -  `Help <https://www.mediawiki.org/wiki/Special:MyLanguage/Help:Contents>`__

      .. container:: portal
         :name: p-Basic_Usage

         .. rubric:: Basic Usage
            :name: p-Basic_Usage-label

         .. container:: body

            -  `Tutorials </rptools/wiki/Category:Tutorial>`__
            -  `Chat Commands </rptools/wiki/Chat_Commands>`__
            -  `Dice Expressions </rptools/wiki/Dice_Expressions>`__
            -  `Glossary </rptools/wiki/Glossary>`__

      .. container:: portal
         :name: p-Macro_Reference

         .. rubric:: Macro Reference
            :name: p-Macro_Reference-label

         .. container:: body

            -  `List of
               Functions </rptools/wiki/Category:Macro_Function>`__
            -  `Roll Options </rptools/wiki/Category:Roll_Option>`__
            -  `Special
               Variables </rptools/wiki/Category:Special_Variable>`__
            -  `Macro Cookbook </rptools/wiki/Category:Cookbook>`__

      .. container:: portal
         :name: p-Editors

         .. rubric:: Editors
            :name: p-Editors-label

         .. container:: body

            -  `Editor Discussion </rptools/wiki/Editor>`__
            -  `Recent Changes </rptools/wiki/Special:RecentChanges>`__

      .. container:: portal
         :name: p-tb

         .. rubric:: Tools
            :name: p-tb-label

         .. container:: body

            -  `What links
               here </rptools/wiki/Special:WhatLinksHere/Supported_CSS_Styles>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Supported_CSS_Styles>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Supported_CSS_Styles&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Supported_CSS_Styles&oldid=7446>`__
            -  `Page
               information </maptool/index.php?title=Supported_CSS_Styles&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 25 July 2019, at 00:01.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
