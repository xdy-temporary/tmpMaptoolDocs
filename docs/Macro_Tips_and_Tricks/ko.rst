.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Marcro Tips and Tricks}}

.. _이니셔티브를_추가_하는_소스:

이니셔티브를 추가 하는 소스
===========================

-  미리 토큰 속성에 Initiative이 설정되어있고 Initiative 수정값이
   들어있어야함.

..

   .. code:: mtmacro
      :number-lines:

      [InitTotal = 1d20 + Initiative + MiscMod]
      [h: setInitiative(InitTotal)]
      [h:abort(0)]

.. _여럿의_적에게_공격을_하는_파워_소스:

여럿의 적에게 공격을 하는 파워 소스
===================================

count 함수를 사용, roll.count 값을 이용해 횟수 기록.

   .. code:: mtmacro
      :number-lines:

      <!-- 맨 처음 값을 입력받는 부분: 타겟 숫자, 명중굴림 수정치, 피해굴림 수정치 -->
      [h:status=input(
      "TargetCount|1|How much Target?",
      "hmod|0|Misc. BONUS to Attack roll",
      "dmod|0|Mics. BONUS to Damage roll")]
      [h:abort(status)]

      파워 명칭~설명들 입력<!--반복문 앞에 기재할 사항 들-->
          [count(TargetCount, "<br>"),CODE: { 
              <b>Target:</b> [roll.count+1]     <!-- 몇번째 대상인지 횟수 표시 -->
              <b>Attack:</b> [roll=1d20]→[roll+Hit+hbuff+Hmod] <!-- 굴림값 표시, 굴림값과 각종 수정치 합산-->
              <span style="color:blue;"><b>vs. AC</b></span>     <!-- 어떤 DEF를 상대하는지 기록 -->
              <span style="color:Red"><b>[if(roll==20):"Crit";""][if(roll==1):"Miss";""]</b></span> <!-- 크리티컬/오토미스 부분-->
          }]
      <br>
          <b>Hit:</b> [w+dmg+dbuff+dmod]점 피해(Crit: [12+w+3d6+dmg+dbuff+dmod]점 피해)를 준다. <!-- 명중시 피해는 반복문 밖에 일괄적으로 기재-->

.. raw:: mediawiki

   {{Languages|Marcro Tips and Tricks}}

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__
