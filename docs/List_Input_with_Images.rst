===================================
List Input with Images - MapToolDoc
===================================

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

   .. rubric:: List Input with Images
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

         The following is the full code for the `Creating a List Input
         with Names and
         Images <Creating_a_List_Input_with_Names_and_Images>`__
         tutorial.

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [H: tokenList=getExposedTokenNames()]
                  [H: imgList = tokenList]
                   
                  [H: Num = listCount(imgList)]
                   
                  [h,COUNT(Num),CODE:
                  {
                  [h:tokenName=listGet(imgList,roll.count)]
                  [h,token(tokenName): image=getTokenImage()]
                  [h:imgList=listReplace(imgList,roll.count,tokenName+" "+image)]
                  }]
                   
                  [h:status=input(
                      "Target|"+imgList+"|Select Target|LIST|SELECT=0 ICON=TRUE ICONSIZE=30",
                      "newName| |Enter a new name for this token"
                  )]
                  [h:abort(status)]
                   
                   
                  [h:targetName = listGet(tokenList,Target)]
                   
                  [h:switchToken(targetName)]
                   
                  [h:token.name=newName]
                  The token's name has been changed to <i>[r:newName]</i>.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=List_Input_with_Images&oldid=2625"

