===========================
Token Property - MapToolDoc
===========================

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

   .. rubric:: Token Property
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

         A *token property* is a variable (string or numeric) that
         resides on a particular `token <Token:token>`__
         within MapTool, and may be called upon or evaluated by macros.

         Token properties are tailored to fit each individual campaign
         file and the macros contained in that campaign. Multiple sets
         of token properties can be created (allowing them to be applied
         to different classes of token - for example, PC tokens versus
         NPC tokens). These multiple sets are called `token property
         types <Token:token_property_type>`__.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Default Token
               Properties <#Default_Token_Properties>`__
            -  `2 Setting Campaign
               Properties <#Setting_Campaign_Properties>`__

               -  `2.1 Token Property Format <#Token_Property_Format>`__
               -  `2.2 Example Token
                  Property <#Example_Token_Property>`__
               -  `2.3 Controlling Token Property
                  Display <#Controlling_Token_Property_Display>`__

         .. rubric:: Default Token Properties
            :name: default-token-properties

         By default, MapTool has the following set of token properties.

         ::

            Strength (Str)
            Dexterity (Dex)
            Constitution (Con)
            Intelligence (Int)
            Wisdom (Wis)
            Charisma (Char)
            *@HP
            *@AC
            Defense (Def)
            Movement (Mov)
            *Elevation (Elv)
            Description (Des)

         .. rubric:: Setting Campaign Properties
            :name: setting-campaign-properties

         Campaign properties are edited using the Campaign Properties
         dialog, which is found under **Edit -> Campaign Properties** on
         the MapTool menu. They can be directly edited in the Campaign
         Properties dialog, or pasted in from a text editor of choice.

         .. rubric:: Token Property Format
            :name: token-property-format

         The format for all token properties.

         ::

            #*@PropertyName(ShortName):default value

         .. rubric:: Example Token Property
            :name: example-token-property

         ::

            *@HealingSurges(Surges):9

         Will display **Surges: 9** in the statsheet.

         .. rubric:: Controlling Token Property Display
            :name: controlling-token-property-display

         There are three "switches" (shown in the format string above)
         that control how campaign properties are displayed in the popup
         *statsheet* when the user hovers his mouse over a token:

         \* - Displays the property on the *statsheet*

         @ - Property will be visible only to the owner of that token

         # - Property will be visible only to the GM

         Note that the **\*** switch is essential for the property to be
         displayed on the statsheet; the **@** and **#** are optional
         modifiers to that display. If no switch is set in the property
         string, the property will be present on the token and
         accessible to macros but will *not* be displayed in the popup
         statsheet.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Token_Property&oldid=2240"

