======================
strformat - MapToolDoc
======================

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

   .. rubric:: strformat
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

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 strformat() Function <#strformat.28.29_Function>`__

               -  `1.1 Simple words <#Simple_words>`__
               -  `1.2 Formatting by Data
                  Type <#Formatting_by_Data_Type>`__
               -  `1.3 Format Types (conversion
                  characters) <#Format_Types_.28conversion_characters.29>`__
               -  `1.4 Formatting by Embedding
                  Variables <#Formatting_by_Embedding_Variables>`__
               -  `1.5 Usage <#Usage>`__
               -  `1.6 Examples <#Examples>`__

         .. rubric:: strformat() Function
            :name: strformat-function

         .. container:: template_version

            • **Introduced in version 1.3b48**

         .. container:: template_description

            Returns a string formatted based on the escape sequences in
            the passed string and optional arguments.
            The format string can contain special instructions that are
            introduced with the ``%`` symbol. There are two different
            approaches to using ``strformat``.

            (This function is directly implemented by Java. You can find
            more details on the syntax of the format
            `here <http://docs.oracle.com/javase/6/docs/api/java/util/Formatter.html#syntax>`__.
            In particular, that page documents the **argument_index**
            modifier which isn't specified here, and MapTool numbers are
            converted to ``BigInteger``'s when formatting integers and
            ``BigDecimal``'s when formatting floating point values.)

            .. rubric:: Simple words
               :name: simple-words

            Simply said this means that it facilitates creating a string
            (sentences) which consists out of variables or even string
            operations. Its especially useful if you want to store the
            string first into a variable. The most common method is
            concatenation:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h:target = "Orc"]

                  #. .. code-block:: none

                          [h:tok = token.name]

                  #. .. code-block:: none

                          [h:hit = 2d6]

                  #. .. code-block:: none

                          [h:output = tok + "hits the " + target + " for: " + hit + "wounds."]

                  #. .. code:: de2

                          [r:output]

            Using ``strformat`` this becomes (just replacing line 4):

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  .. code-block:: none

                       [h:output = strformat("%{tok} hits the %{target} for: %{hit} wounds.")]

            Or the other method if you do not wish to create variables
            first:

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                          [h:target = "Orc"]

                  #. .. code-block:: none

                          [h:output = strformat("%s hits the %{target} for: %d wounds.", token.name, 2d6)]

            So why would you use this over the concatenation method?
            Four reasons:

            #. its cleaner (easier to read),
            #. its faster (though barely noticeable),
            #. you can embed the whole operation inside a function call
               and
            #. it has lots and lots of formatting options.

            .. rubric:: Formatting by Data Type
               :name: formatting-by-data-type

            The most general use of ``strformat`` is to pass a format
            string first, followed by a list of parameters. Each
            parameter is matched against the corresponding marker in the
            format string. Any characters in the format string that are
            not markers are treated as literal text to be output.

            ::

                %(+0x

            The first character is the percent sign (``%``). This
            denotes a format marker. All text up to the next alphabetic
            character is part of the marker. In the string above (the
            ``%(+0x``), each character represents one type of option.

            Option Representation

Applies to...

Literal Values

**%**

All

``%`` identifies the beginning of a format marker.

**(**

Numeric

``(`` will cause the numeric value to be enclosed in parentheses if it's
negative.

**+**

Numeric

``+`` indicates that all numeric values, positive or negative, will have
a preceding sign.

All

``-`` indicates that the value to be formatted should be left-justified
within the specified field.

**0**

String

*digits* indicates the field width for this format marker. This field
may contain a decimal point and additional digits to signify the maximum
number of characters from the parameter that will be used.

Numeric

*digits* indicates the field width for this format marker. If *digits*
starts with a literal **0** (zero), the numeric value being formatted
will be zero-filled within the field instead of space-filled. If the
format type is floating point, this field may contain a decimal point
and additional digits to signify the number of digits after the decimal
in the output.

**x**

All

*type* is one of the alphabetic characters from the table below. The
*type* identifies the basic characteristics of how the corresponding
parameter will be displayed.

Format Types (conversion characters)
====================================

The following format types are supported (lower case format arguments
perform the same conversion as the lowercase letters but return the
result in uppercase).

================== ========= ===========================================================================================================
Format Type        Data Type Description
================== ========= ===========================================================================================================
**%h, %H, %x, %X** Integer   Inserts the hexadecimal representation.
**%s, %S**         String    Inserts the string representation.
**%d**             Integer   Inserts the decimal representation.
**%e, %E**         Numeric   Inserts the floating point value in scientific notation.
**%f**             Numeric   Inserts the floating point value in fixed-point notation.
**%g, %G**         Numeric   Inserts the floating point value in computerized scientific notion or fixed-point format.
**%a, %A**         Numeric   Inserts the floating point value as a hexadecimal floating-point number with a significand and an exponent.
**%%**             -         Inserts a literal percent symbol.
**%n**             -         Inserts a newline.
================== ========= ===========================================================================================================

Formatting by Embedding Variables
=================================

This type of formatting does not control how the contents of a variable
are displayed except that those contents are put into the output at a
specific point in the data.

In this style, a single ``%`` is followed by a set of braces ``"{"`` and
``"}"`` with a variable name inside them.

This technique can be mixed with the usage of ``strformat`` as shown
above.

Usage
=====

.. container:: mw-geshi mw-code mw-content-ltr

   .. container:: mtmacro source-mtmacro

      #. .. code-block:: none

            strformat(string)

.. container:: mw-geshi mw-code mw-content-ltr

   .. container:: mtmacro source-mtmacro

      #. .. code-block:: none

            strformat(string, arg, ...)

Examples
========

.. container:: template_examples

   .. container:: mw-geshi mw-code mw-content-ltr

      .. container:: mtmacro source-mtmacro

         #. .. code-block:: none

                   [h: weaponName = "Long Sword"]

         #. .. code-block:: none

                   [h: maxDam = 8]

         #. .. code-block:: none

                   [r: strformat("Weapon Name=%{weaponName}; Max Damage=%{maxDam}")]

   Returns:

   ::

      Weapon Name=Long Sword; Max Damage=8

   | 

   .. container:: mw-geshi mw-code mw-content-ltr

      .. container:: mtmacro source-mtmacro

         #. .. code-block:: none

                   [h: weaponName = "Long Sword"]

         #. .. code-block:: none

                   [h: maxDam = 8]

         #. .. code-block:: none

                   [r: strformat("Weapon Name=%s; Max Damage=%d", weaponName, maxDam)]

   Returns the same result as the previous:

   ::

      Weapon Name=Long Sword; Max Damage=8

   | 

   .. container:: mw-geshi mw-code mw-content-ltr

      .. container:: mtmacro source-mtmacro

         #. .. code-block:: none

                   [h: weaponName = "Long Sword"]

         #. .. code-block:: none

                   [h: maxDam = 8]

         #. .. code-block:: none

                   [r: strformat("Weapon Name='%12s'; Max Damage=%04d", weaponName, maxDam)]

   Returns the same data but formatted. Note how there are two
   additional spaces in front of the weapon name this time? That's
   because the field width was specified as ``12`` in the format marker
   so the function generated 2 spaces and then the 10 characters from
   the variable. Also note that ``04`` caused the damage field to be 4
   digits filled with leading zeroes. Take out the ``0`` from ``04`` and
   the output would still include 4 characters, but it would've been
   space-filled instead of zero-filled.

   ::

      Weapon Name='  Long Sword'; Max Damage=0008

   | 

   .. container:: mw-geshi mw-code mw-content-ltr

      .. container:: mtmacro source-mtmacro

         #. .. code-block:: none

                   [h: weaponName = "Long Sword"]

         #. .. code-block:: none

                   [h: maxDam = 8]

         #. .. code-block:: none

                   [h: style="background-color: yellow" ]

         #. .. code-block:: none

                   [r: strformat("<table><tr style='%{style}'><td>%{weaponName}</td></tr><tr><td>%.0f</td></tr></table>",

         #. .. code:: de2

                          maxDam*1.5)]

   Combining the two techniques is often convenient as show here. Note
   that ``maxDam`` is multiplied by 1½ and this could result in a
   fractional component. Such floating point values **must** be
   displayed using one of the floating point format types. (Otherwise
   the error will be ``f != java.lang.BigInteger`` because an integer
   was provided where a float was expected and it's telling you that the
   ``f`` type doesn't apply to integers. A similar message is displayed
   if you try to display a floating point value as a decimal.)

   | 

   .. container:: mw-geshi mw-code mw-content-ltr

      .. container:: mtmacro source-mtmacro

         #. .. code-block:: none

                   [strformat("%f", -10.502)] [strformat("%g", -10.502)]

         #. .. code-block:: none

                   [strformat("%+e", -10.502)] [strformat("%5.1f", -10.502)]

         #. .. code-block:: none

                   [strformat("%(5.1f", -10.502)]

   Returns:

   ::

         -10.502000 
         -10.5020 
          -1.050200e+01 
         -10.5 

   (10.5)

.. container:: printfooter

   Retrieved from
   "http://lmwcs.com/maptool/index.php?title=strformat&oldid=6162"

.. container:: catlinks
   :name: catlinks

   .. container:: mw-normal-catlinks
      :name: mw-normal-catlinks

      `Categories </rptools/wiki/Special:Categories>`__:

      -  `Macro Function </rptools/wiki/Category:Macro_Function>`__
      -  `String Function </rptools/wiki/Category:String_Function>`__

   --------------

   `MapTool </rptools/wiki/Category:MapTool>`__ >
   `Macro </rptools/wiki/Category:Macro>`__ > `Macro
   Function </rptools/wiki/Category:Macro_Function>`__
   `MapTool </rptools/wiki/Category:MapTool>`__ >
   `Macro </rptools/wiki/Category:Macro>`__ > `Macro
   Function </rptools/wiki/Category:Macro_Function>`__ > `String
   Function </rptools/wiki/Category:String_Function>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=strformat>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/strformat>`__
            -  `Discussion </maptool/index.php?title=Talk:strformat&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/strformat>`__
            -  `View
               source </maptool/index.php?title=strformat&action=edit>`__
            -  `View
               history </maptool/index.php?title=strformat&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/strformat>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/strformat>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=strformat&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=strformat&oldid=6162>`__
            -  `Page
               information </maptool/index.php?title=strformat&action=info>`__

.. container::
   :name: footer

   -  This page was last modified on 29 June 2013, at 20:44.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
