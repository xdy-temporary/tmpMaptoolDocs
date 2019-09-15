=========================
Help:Editing - MapToolDoc
=========================

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

   .. rubric:: Help:Editing
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

         This article contains documentation on specific features of our
         wiki, see MediaWiki's `help on
         editing <http://meta.wikimedia.org/wiki/Help:Editing>`__
         article for details of basic formatting and markup.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Miscellaneous
               Formatting <#Miscellaneous_Formatting>`__

               -  `1.1 Macro Code
                  Highlighting <#Macro_Code_Highlighting>`__
               -  `1.2 Inline Code <#Inline_Code>`__
               -  `1.3 Marking Articles <#Marking_Articles>`__

                  -  `1.3.1 Stub <#Stub>`__
                  -  `1.3.2 Clarification <#Clarification>`__

               -  `1.4 Function Linking <#Function_Linking>`__
               -  `1.5 Roll Option Linking <#Roll_Option_Linking>`__

            -  `2 Function Formatting <#Function_Formatting>`__

               -  `2.1 Notes <#Notes>`__
               -  `2.2 Parameters <#Parameters>`__
               -  `2.3 Example <#Example>`__

         .. rubric:: Miscellaneous Formatting
            :name: miscellaneous-formatting

         .. rubric:: Macro Code Highlighting
            :name: macro-code-highlighting

         To perform syntax highlighting on your macro code enclose it in
         the following tags:

         **Syntax:**

         ::

              <source lang="mtmacro" line>
              </source>

         **Example:**

         ::

              <source lang="mtmacro" line>
                [h: name = getName()]
                [r: name]
              </source>

         **Produces:**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: name = getName()]

               #. .. code-block:: none

                     [r: name]

         | 
         | You can also change the number that the line number starts
           at:

         **Example:**

         ::

              <source lang="mtmacro" line start=10>
                [h: name = getName()]
                [r: name]
              </source>

         **Produces:**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               10. .. code-block:: none

                      [h: name = getName()]

               11. .. code-block:: none

                      [r: name]

         This is useful for breaking up long chunks of example code, yet
         still maintaining proper line numbering.

         | 

         .. rubric:: Inline Code
            :name: inline-code

         There are a number of ways to include ``inline code``, but
         we've created a small template that makes it easier than ever.
         The syntax below produces: ``example``

         ::

            {{code|example}}

         You can replace ``example`` with anything you want to be shown
         as inline code. This is useful if you're referencing a
         variable, function, or anything else that would be more
         appropriate in a monospaced typeface. This template works
         inside wiki-links as well, the following syntax produces:
         ```abort()`` </rptools/wiki/abort>`__

         ::

            [[abort|{{code|abort()}}]]

         .. rubric:: Marking Articles
            :name: marking-articles

         .. rubric:: Stub
            :name: stub

         If you come across an article that looks like little more than
         a placeholder, please mark it as a stub so that we can easily
         find it in the future and expand it.

         To mark an article as a stub, edit it and add the following tag
         to the top of the article:

         ::

            {{stub}}

         Optionally, you may add a note about why the article is
         considered a stub.

         ::

            {{stub|What this article needs so that it wouldn't be a stub.}}

         .. rubric:: Clarification
            :name: clarification

         If you come across an article that doesn't seem clear enough on
         a particular point, you can mark it for clarification which
         allows a knowledgeable editor to find it easier in the future.

         To mark an article for clarification, edit the article and add
         a note near the section that needs clarification. Use
         {{Clarify\| followed by a short note about what needs to be
         clarified, then end your note with }}.

         **Example**

         ::

            {{Clarify|How is this function supposed to be used in the event that such and such occurs?}}

         .. rubric:: Function Linking
            :name: function-linking

         We often find ourselves linking to functions, and function
         links look better with parenthesis after the function name, but
         the function articles themselves do not contain the
         parenthesis. This prevents us from simply creating a
         [[functionName]] wikilink, and instead forces us to type the
         function name twice: [[functionName|functionName()]]. To make
         it easier to link to functions, while still having the
         parenthesis attached, we've created the {{func\| template.

         **Example**

         ::

            {{func|functionName}}

         Will result in the link to the function having the necessary
         parenthesis added automatically.

         .. rubric:: Roll Option Linking
            :name: roll-option-linking

         Formats the roll option link as [rolloption:] or
         [rolloption():] depending on the type. The type is determined
         by a list inside the roll template, so be sure to add new roll
         options there. To use, {{roll\| followed by the roll option's
         article name not including the \_(roll_option) that you would
         normally have to include, then closed with }} template.

         **Examples**

         ::

            {{roll|expanded}}

         Results in a link as if you had entered [[expanded (roll
         option)|[expanded:] ]]
         ::

            {{roll|foreach}}

         Results in a link as if you had entered [[foreach (roll
         option)|[foreach():] ]]
         .. rubric:: Function Formatting
            :name: function-formatting

         A template has been created to assist with writing articles for
         macro functions. To use the template, begin with
         ``{{MacroFunction``, followed by any parameters you might use,
         and then end with ``}}``. See Mediawiki's `template
         help <http://meta.wikimedia.org/wiki/Help:Template>`__ for more
         documentation on using templates.

         .. rubric:: Notes
            :name: notes

         -  This template only adds the function to the `Macro
            Function </rptools/wiki/Category:Macro_Function>`__
            category, you should manually add any other categories it
            belongs in. Categories can be added by including
            [[Category:Example]], where Example is the name of the
            category you with to add. You can include this code anywhere
            within the article, but preferably at the end to make it
            easier for other editors to find.

         -  The broken bar \| is a special character inside templates;
            this presents problems when trying to build wiki tables
            inside a template. There is a special template that allows
            you to work around this problem: using {{!}} in place of all
            broken bars will allow your table to work properly inside a
            template.

         .. rubric:: Parameters
            :name: parameters

         All parameters are optional, except **\|name=** and
         **\|usage=**. Although the parameters can be used in any order,
         using them in the order presented will make it easier for other
         editors that might work on the function article.

         -  **\|name=** • Case-sensitive name of the function.

         -  **\|proposed=true** • Adds a note that the article refers to
            a proposed change that has not yet been implemented in the
            main code base. If this parameter is missing, or contains a
            value that is not ``true``, it will be treated as ``false``
            and not displayed.

         -  **\|deprecated=** • Adds a note that the function has been
            deprecated and a link to the function that should be used
            instead.

         -  **\|trusted=true** • Adds a note that the function can only
            be used in a `trusted
            macro </rptools/wiki/Trusted_Macro>`__. If this parameter is
            missing, or contains a value that is not ``true``, it will
            be treated as ``false`` and not displayed.

         -  **\|version=** • Adds a note for which version of MapTool
            included the addition of this function. The value should be
            the exact version number, e.g. ``1.3b50``

         -  **\|compatibility=** • Adds a note stating the version of
            MapTool that this function's article is about. This is
            primarily used if a function has received changes since its
            first inclusion that could cause the usage and/or examples
            to not work with the version in which it was first
            introduced. The value should be the exact version number,
            e.g. ``1.3b50``

         -  **\|description=** • This should contain a brief description
            on the purpose of the function.

         -  **\|usage=** • The usage block should contain the various
            syntax that the function accepts.

         -  **\|examples=** • Examples should be the majority of a
            function's page content. The more examples there are, the
            more of a complete understanding the reader will have.

         -  **\|also=** • If you use other functions in any examples, or
            if there are other articles that are related to this one,
            you should include links to them in this block.

         -  **\|changes=** • A place to record changes that function has
            received in various versions of MapTool.

         .. rubric:: Example
            :name: example

         ::

            {{MacroFunction
            |name=exampleFunction
            |proposed=true
            |deprecated=[[newFunction|newFunction()]]
            |trusted=true
            |version=1.3b50
            |compatibility=1.3b52
            |description=
            This is an example function.  It doesn't actually exist as a function in MapTool.

            |usage=
            <source lang="mtmacro" line>
            exampleFunction(param1, param2)
            </source>
            '''Parameters'''
            {{param|param1|Describe parameter}}
            {{param|param2|Describe parameter}}

            |example=
            This example doesn't really do anything.
            <source lang="mtmacro" line>
            [h: exampleVariable = "a,b,c"]
            [r: exampleFunction(exampleVariable, reverse)]
            </source>
            Returns:
            <source lang="mtmacro" line>
            c,b,a
            </source>

            |also=
            [[linkToRelatedArticle|Display Name of Related Article]]

            |changes=
            * '''1.3b52''' - Added reverse parameter.
            }}

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Help:Editing&oldid=7327"

