===============================
Hit Check Function - MapToolDoc
===============================

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

   .. rubric:: Hit Check Function
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

         Checks the value of an attack result against a target's
         defense. If the attack is greater than or equal to the defense,
         it outputs "Hit!" or "Miss."

         function HitCheck(attackResult,targetName,TargetDefense)

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  Code:
                  [h: attackResult = arg(0)]
                  [h: targetName = arg(1)]
                  [h: targetDefense = arg(2)]
                   
                  [h: defenseValue = getProperty(targetDefense,targetName)]
                   
                  [r,if(attackResult >= defenseValue): "Hit!"; "Miss."]

         Thanks to Rumble for help with this macro.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Hit_Check_Function&oldid=3962"

