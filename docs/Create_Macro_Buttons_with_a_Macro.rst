==============================================
Create Macro Buttons with a Macro - MapToolDoc
==============================================

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

   .. rubric:: Create Macro Buttons with a Macro
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

         This is the full macro code from the `Creating Macro Buttons
         Using a
         Macro </rptools/wiki/Creating_Macro_Buttons_Using_a_Macro>`__
         tutorial.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h:powerSlot=macro.args]
                  [h:pname=getStrProp(eval("Power"+powerSlot),"powername")]
                  [h:use=getStrProp(eval("Power"+powerSlot),"usage")]
                   
                  [h:status=input(
                      "addButtons|Yes,No|Add Macro Buttons to your token?|RADIO|ORIENT=H SELECT=1"
                  )]
                  [h:abort(status)]
                   
                  [IF(addButtons==0),CODE:
                  {
                  [h,SWITCH(use),CODE:
                  case "at-will":
                  {
                    [bcolor="green"]
                    [fcolor="black"]
                    [group="1: Powers - At-Will"]
                    [grayout=0]
                  };
                  case "encounter":
                  {
                    [bcolor="red"]
                    [fcolor="white"]
                    [group="2: Powers - Encounter"]
                    [grayout=1]
                  };
                  case "daily":
                  {
                    [bcolor="black"]
                    [fcolor="white"]
                    [group="3: Powers - Daily"]
                    [grayout=1]
                  };
                  case "recharge":
                  {
                    [bcolor="blue"]
                    [fcolor="white"]
                    [group="3: Powers - Recharging"]
                    [grayout=1]
                  };]
                   
                  [h:macroProps="autoexec=true;"]
                  [h:macroProps=setStrProp(macroProps,"color",bcolor)]
                  [h:macroProps=setStrProp(macroProps,"fontColor",fcolor)]
                  [h:macroProps=setStrProp(macroProps,"group",group)]
                  [h:grayoutString=""]
                  [h,IF(grayout): grayoutString=encode("[h:setMacroProps(" + "'"
                                  +pname+ "'" + ",'color=gray;' " + ")]")]
                  [h:command=encode("[h:thisPower="+"'"+pname+"'"+"]")]
                  [h:command=command+encode("[h:index=getMacroIndexes(thisPower)]")]
                  [h:command=command+encode("[h:mProps=getMacroProps(index)]")]
                  [h:command=command+encode("[h:color=getStrProp(mProps,'color')]")]
                  [h:command=command+encode("[h:used=if(color=='gray', 0, 1)]")]
                  [h:command=command+encode("[h:abort(used)]")]
                  [h:command=command + encode("[MACRO('AttackMain@Lib:test'):thisPower]")]
                  [h:command=command+grayoutString]
                  [h:createMacro(pname, decode(command), macroProps)]
                  Buttons added.
                  };
                  {
                  No buttons added to token.
                  };]

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Create_Macro_Buttons_with_a_Macro&oldid=2628"

