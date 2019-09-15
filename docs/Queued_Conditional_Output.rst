======================================
Queued Conditional Output - MapToolDoc
======================================

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

   .. rubric:: Queued Conditional Output
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

         .. container::

             Note: This function can only be used in a `Trusted
            Macro <Trusted_Macro>`__

         | **Requires MapTool 1.3b55**
         | The following is a user defined function that allows you to
           queue output to various recipients. All of the queued output
           is then displayed to the intended recipient/s after the
           completion of the current macro.

         .. container:: toc
            :name: toc

            .. container::
               :name: toctitle

               .. rubric:: Contents
                  :name: contents

            -  `1 Usage <#Usage>`__
            -  `2 Notes <#Notes>`__
            -  `3 Macros <#Macros>`__
            -  `4 See Also <#See_Also>`__

         .. rubric:: Usage
            :name: usage

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     outputTo(who, what)

         **Parameters:**

         -  ``who`` - Expects a string containing the recipient/s; this
            string can be ``'self'``, ``'gm'``, ``'gm-self'``, or a JSON
            array of player names(e.g. ``'["Bob","Joe"]')``.
         -  ``what`` - Expects a string that contains the output; it is
            sent to the recipient as plain text, so HTML code works as
            intended.

         .. rubric:: Notes
            :name: notes

         -  When sending to a specific list of recipients, the output
            comes across as a whisper; that's just the way it is.
         -  Currently there is no error checking, if you want/need error
            checking, it shouldn't be hard to implement.
         -  There is theoretically no limit to the amount of outputs you
            can queue, but like any software your hardware will impose
            its own limits.

         .. rubric:: Macros
            :name: macros

         Place the following macros all on the same library token(or on
         different library tokens if you know what you're doing and what
         to change).

         --------------

         **onCampaignLoad**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [defineFunction('outputTo', 'outputTo@this')]

         --------------

         --------------

         **outputTo**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [h: toSend = '{}']
                  [h: argTest = json.type(arg(0))]
                  [h, if(argTest=='ARRAY'), code:
                  {
                      [h: toWho = 'list']
                      [h: toSend = json.set(toSend, 'mlOutputList', arg(0))]
                  };{
                      [h: toWho = arg(0)]
                  }]
                  [h: toSend = json.set(toSend, 'toSend', arg(1))]
                  [h: conditionalOutput = macroLinkText('conditionalOutput@this', toWho, toSend)]
                  [h: execLink(conditionalOutput, 1)]

         --------------

         --------------

         **conditionalOutput**

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               .. code-block:: none

                  [r: json.get(macro.args, 'toSend')]

         --------------

         .. rubric:: See Also
            :name: see-also

         `macroLinkText <macroLinkText>`__,
         `execLink <execLink>`__

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Queued_Conditional_Output&oldid=3641"

