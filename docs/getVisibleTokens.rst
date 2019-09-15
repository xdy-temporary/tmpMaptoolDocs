=============================
getVisibleTokens - MapToolDoc
=============================

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

   .. rubric:: getVisibleTokens
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

            -  `1 getVisibleTokens()
               Function <#getVisibleTokens.28.29_Function>`__

               -  `1.1 Usage <#Usage>`__
               -  `1.2 Examples <#Examples>`__
               -  `1.3 Version Changes <#Version_Changes>`__

         .. rubric:: getVisibleTokens() Function
            :name: getvisibletokens-function

         .. container:: template_version

            • **Introduced in version 1.3b49**

         .. container:: template_description

            Returns a `string list <Macros:string_list>`__
            or `JSON Array <JSON_Array>`__ of `token
            ids <Glossary#Token_Id>`__ for the
            `tokens <Token:token>`__ that are *visible* to
            the player. The type of the value returned depends on the
            delimiter parameter.

            -  If the delimiter is not specified then a `string
               list <Macros:string_list>`__ is returned
               with the default value of ``","`` is used.
            -  If the delimiter ``json`` then a `JSON
               Array <JSON_Array>`__ is returned.
            -  Otherwise a `string
               list <Macros:string_list>`__ is returned
               with the delimiter passed in.

             

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getVisibleTokens()

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     getVisibleTokens(delim)

         .. rubric:: Examples
            :name: examples

         .. container:: template_examples

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: tokens = getVisibleTokens()]

            | 

            .. container:: mw-geshi mw-code mw-content-ltr

               .. container:: mtmacro source-mtmacro

                  #. .. code-block:: none

                        [h: tokens = getVisibleTokens("json")]

         .. rubric:: Version Changes
            :name: version-changes

         .. container:: template_changes

            -  **1.3b51** - No longer a trusted function.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=getVisibleTokens&oldid=7212"

