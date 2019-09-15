===========================
Sample Ruleset - MapToolDoc
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

   .. rubric:: Sample Ruleset
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

         This is a small roleplaying game system created by Phergus for
         use in examples and samples for RPTools applications. As noted
         on the original thread, this is not meant to be a mature and
         balanced system, but rather a system that contains enough
         aspects to highlight a good selection of application features.
         See the `original
         thread <http://forums.rptools.net/viewtopic.php?f=12&t=6343>`__
         for more details.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Characters <#Characters>`__

               -  `1.1 Primary Attributes <#Primary_Attributes>`__
               -  `1.2 Derived Attributes <#Derived_Attributes>`__
               -  `1.3 Classes <#Classes>`__

            -  `2 Combat <#Combat>`__

               -  `2.1 Initiative <#Initiative>`__
               -  `2.2 Movement <#Movement>`__
               -  `2.3 Attack Roll <#Attack_Roll>`__
               -  `2.4 Damage Roll <#Damage_Roll>`__

            -  `3 Powers <#Powers>`__

               -  `3.1 Attack Powers <#Attack_Powers>`__
               -  `3.2 Other Powers <#Other_Powers>`__

         .. rubric:: Characters
            :name: characters

         .. rubric:: Primary Attributes
            :name: primary-attributes

         Primary attributes are determined using a point system.
         Starting characters are given ``14`` points to distribute among
         their four primary attributes. Each primary attribute must at
         least have a value of ``1``, but can be no higher than ``6``.

         -  **Strength (Str)**
         -  **Dexterity (Dex)**
         -  **Intelligence (Int)**
         -  **Endurance (End)**

         **Summary:** Total of ``14`` points. Minimum of ``1``. Maximum
         of ``6``.

         .. rubric:: Derived Attributes
            :name: derived-attributes

         Character possess three derived attributes. *Hit Points* are
         determined multiplying *Endurance* by ``6``. Each character
         class has a different *Armor* score; *Armor* can also be
         increased by powers. Base *Movement* is equal to a character's
         *Dexterity*.

         -  **Hit Points (HP)**
         -  **Armor (AR)**
         -  **Movement (MV)**

         **Summary:** (*Endurance*)x\ ``6`` *Hit Points*. *Armor*
         determined by class. *Movement* equals *Dexterity*.

         .. rubric:: Classes
            :name: classes

         At character creation, players get to choose a class for their
         character. The chosen class determines beginning powers and
         *Armor*.

         ======= =============================================== =====
         Class   Beginning Powers                                Armor
         ======= =============================================== =====
         Warrior Sword, Shield Bash, Bow, Shield, Torch          6
         Rogue   Dagger, Hide, Backstab, Pick Lock, Torch        2
         Wizard  Dagger, Staff, Light, Lightning Bolt, Fire Ball 1
         Priest  Mace, Heal, Protect, Banish Undead, Torch       4
         ======= =============================================== =====

         .. rubric:: Combat
            :name: combat

         .. rubric:: Initiative
            :name: initiative

         Each combatant rolls for initiative at the beginning of each
         round. Initiative roll is ``1d6`` + *Dexterity*. Each combatant
         acts in order of initiative, highest to lowest, each round.

         .. rubric:: Movement
            :name: movement

         Combatants can use a power or move each round. When moving, a
         combatant can move a number of squares/hexes equal to their
         *Movement*.

         .. rubric:: Attack Roll
            :name: attack-roll

         An attack power requires a roll to determine if it succeeds. If
         the roll is ``15`` or higher after applying any bonuses, the
         attack power succeeds.

         -  **Melee Attacks** - Roll ``1d20`` + *Strength* + Power
            Attack Bonus
         -  **Ranged Attack** - Roll ``1d20`` + *Dexterity* + Power
            Attack Bonus
         -  **Spell Attack** - Roll ``1d10`` + *Intelligence* + Power
            Attack Bonus

         **Summary:** A ``15+`` on the attack roll succeeds.

         .. rubric:: Damage Roll
            :name: damage-roll

         | If an attack power succeeds in hitting the target, determined
           damage by rolling ``1d6``, apply the power damage bonus, add
           the relevant attack attribute, and finally subtract the
           target's *Armor*. Subtract the result from the target's *Hit
           Points*.
         | **Summary:** ``1d6`` + (Power Damage Bonus) + (Attack
           Attribute Bonus) - Armor

         .. rubric:: Powers
            :name: powers

         PCs/NPCs have Powers that represent their attacks and
         abilities. Beginnning PCs have 5 powers. NPCs will have a
         variable number but at least 1. Two types of powers: Attack &
         Other. During any combat round a PC/NPC may have 1 non-attack
         Power active and may use 1 Power to attack.

         .. rubric:: Attack Powers
            :name: attack-powers

         ============== ============ ============ ===== ======================================================================================================
         Name           Attack Bonus Damage Bonus Range Special
         ============== ============ ============ ===== ======================================================================================================
         Backstab       +4           2x           -     Must attack from rear and have been hidden previous round.
         Banish Undead  +0           +8           4     Only works on Undead. With a roll of 6 on a d6 the Undead is Enraged and gains +2 damage for 3 rounds.
         Bite I         -1           -2           -    
         Bite II        -1           -1           -     Infects target on a roll of 5+, reduces Strength by 2.
         Bow            +0           +1           8    
         Chilling Touch -1           +2           -     Freezing touch does damage and reduces Dexterity by 2.
         Claw           -2           +2           -    
         Curse          +0           +0           3     Pain from attack reduces Intelligence by 2.
         Dagger         +0           -1           2     Melee or ranged.
         Fire Ball      -1           +0           4     Does damage to target and all in the immediately adjacent squares/hexes.
         Heal           \*           -            4     Heals target (self/other) for 2d6. \*No roll to hit.
         Lightning Bolt +1           +4           6     Single target
         Mace           +1           +1           -    
         Shield Bash    -1           1/2          -     Stuns foe with a 4+ on a d6 for 3 rounds.
         Staff          +0           +0           -    
         Summon Undead  -            -            2     Summons 1 zombie.
         Sword          +2           +2           -    
         ============== ============ ============ ===== ======================================================================================================

         .. rubric:: Other Powers
            :name: other-powers

         ========= ===== ============================================================
         Name      Range Special
         ========= ===== ============================================================
         Hide      -     Hides Rogue from enemies. Cannot attack except for Backstab.
         Light     -     Illuminates a 6 square/hex radius around Wizard.
         Pick Lock -     Opens Lock on 1d6 + Dexterity > Lock Difficulty.
         Protect   4     Gives +4 Armor to target. (self/other)
         Shield    -     Adds +2 Armor. Can't be used with Shield Bash.
         Torch     -     Illuminates a 3 square/hex radius around character.
         ========= ===== ============================================================

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Sample_Ruleset&oldid=2595"

      .. container:: catlinks
         :name: catlinks

         .. container:: mw-normal-catlinks
            :name: mw-normal-catlinks

            `Category </rptools/wiki/Special:Categories>`__:

            -  `MapTool </rptools/wiki/Category:MapTool>`__

         --------------

         `MapTool </rptools/wiki/Category:MapTool>`__

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
            in </maptool/index.php?title=Special:UserLogin&returnto=Sample+Ruleset>`__

      .. container::
         :name: left-navigation

         .. container:: vectorTabs
            :name: p-namespaces

            .. rubric:: Namespaces
               :name: p-namespaces-label

            -  `Page </rptools/wiki/Sample_Ruleset>`__
            -  `Discussion </maptool/index.php?title=Talk:Sample_Ruleset&action=edit&redlink=1>`__

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

            -  `Read </rptools/wiki/Sample_Ruleset>`__
            -  `View
               source </maptool/index.php?title=Sample_Ruleset&action=edit>`__
            -  `View
               history </maptool/index.php?title=Sample_Ruleset&action=history>`__

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
               here </rptools/wiki/Special:WhatLinksHere/Sample_Ruleset>`__
            -  `Related
               changes </rptools/wiki/Special:RecentChangesLinked/Sample_Ruleset>`__
            -  `Special pages </rptools/wiki/Special:SpecialPages>`__
            -  `Printable
               version </maptool/index.php?title=Sample_Ruleset&printable=yes>`__
            -  `Permanent
               link </maptool/index.php?title=Sample_Ruleset&oldid=2595>`__
            -  `Page
               information </maptool/index.php?title=Sample_Ruleset&action=info>`__

      .. container:: portal
         :name: p-lang

         .. rubric:: In other languages
            :name: p-lang-label

         .. container:: body

            -  `italiano <http://lmwcs.com/rptools/wiki/Sample_Ruleset/it>`__

.. container::
   :name: footer

   -  This page was last modified on 1 April 2009, at 13:39.

   -  `Privacy policy </rptools/wiki/MapToolDoc:Privacy_policy>`__
   -  `About MapToolDoc </rptools/wiki/MapToolDoc:About>`__
   -  `Disclaimers </rptools/wiki/MapToolDoc:General_disclaimer>`__

   -  |Powered by MediaWiki|

   .. container::

.. |Powered by MediaWiki| image:: /maptool/resources/assets/poweredby_mediawiki_88x31.png
   :width: 88px
   :height: 31px
   :target: //www.mediawiki.org/
