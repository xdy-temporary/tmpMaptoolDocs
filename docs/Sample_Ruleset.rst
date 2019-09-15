.. contents::
   :depth: 3
..

This is a small roleplaying game system created by Phergus for use in
examples and samples for RPTools applications. As noted on the original
thread, this is not meant to be a mature and balanced system, but rather
a system that contains enough aspects to highlight a good selection of
application features. See the `original
thread <http://forums.rptools.net/viewtopic.php?f=12&t=6343>`__ for more
details.

Characters
==========

.. _primary_attributes:

Primary Attributes
------------------

Primary attributes are determined using a point system. Starting
characters are given points to distribute among their four primary
attributes. Each primary attribute must at least have a value of , but
can be no higher than .

-  **Strength (Str)**
-  **Dexterity (Dex)**
-  **Intelligence (Int)**
-  **Endurance (End)**

**Summary:** Total of points. Minimum of . Maximum of .

.. _derived_attributes:

Derived Attributes
------------------

Character possess three derived attributes. *Hit Points* are determined
multiplying *Endurance* by . Each character class has a different
*Armor* score; *Armor* can also be increased by powers. Base *Movement*
is equal to a character's *Dexterity*.

-  **Hit Points (HP)**
-  **Armor (AR)**
-  **Movement (MV)**

**Summary:** (*Endurance*)x *Hit Points*. *Armor* determined by class.
*Movement* equals *Dexterity*.

Classes
-------

At character creation, players get to choose a class for their
character. The chosen class determines beginning powers and *Armor*.

======= =============================================== =====
Class   Beginning Powers                                Armor
======= =============================================== =====
Warrior Sword, Shield Bash, Bow, Shield, Torch          6
Rogue   Dagger, Hide, Backstab, Pick Lock, Torch        2
Wizard  Dagger, Staff, Light, Lightning Bolt, Fire Ball 1
Priest  Mace, Heal, Protect, Banish Undead, Torch       4
======= =============================================== =====

Combat
======

Initiative
----------

Each combatant rolls for initiative at the beginning of each round.
Initiative roll is + *Dexterity*. Each combatant acts in order of
initiative, highest to lowest, each round.

Movement
--------

Combatants can use a power or move each round. When moving, a combatant
can move a number of squares/hexes equal to their *Movement*.

.. _attack_roll:

Attack Roll
-----------

An attack power requires a roll to determine if it succeeds. If the roll
is or higher after applying any bonuses, the attack power succeeds.

-  **Melee Attacks** - Roll + *Strength* + Power Attack Bonus
-  **Ranged Attack** - Roll + *Dexterity* + Power Attack Bonus
-  **Spell Attack** - Roll + *Intelligence* + Power Attack Bonus

**Summary:** A on the attack roll succeeds.

.. _damage_roll:

Damage Roll
-----------

| If an attack power succeeds in hitting the target, determined damage
  by rolling , apply the power damage bonus, add the relevant attack
  attribute, and finally subtract the target's *Armor*. Subtract the
  result from the target's *Hit Points*.
| **Summary:** + (Power Damage Bonus) + (Attack Attribute Bonus) - Armor

Powers
======

PCs/NPCs have Powers that represent their attacks and abilities.
Beginnning PCs have 5 powers. NPCs will have a variable number but at
least 1. Two types of powers: Attack & Other. During any combat round a
PC/NPC may have 1 non-attack Power active and may use 1 Power to attack.

.. _attack_powers:

Attack Powers
-------------

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

.. _other_powers:

Other Powers
------------

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

`Category:MapTool <Category:MapTool>`__
