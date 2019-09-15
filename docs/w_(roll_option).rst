============================
w (roll option) - MapToolDoc
============================

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

   .. rubric:: w (roll option)
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

         .. rubric:: [ ] Display to Specific Player Option
            :name: display-to-specific-player-option

         .. container::

            • **Introduced in version 1.3.b58**

         **[w("name"): ]**, **[whisper("name"): ]** evaluates the text
         after the ':' but only displays the results to the specific
         named user, such as:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     Everyone can see this [w("bob"): "but only Bob can see this"]

         **[w():]** can also take more than one player name as an
         argument:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [w("Fred", "Joe"): d20]

         It can also take a JSON list containing player names:

         .. container:: mw-geshi mw-code mw-content-ltr

            .. container:: mtmacro source-mtmacro

               #. .. code-block:: none

                     [h: names = json.fromList("Fred, Joe")]

               #. .. code-block:: none

                     [w(names): d20]

         This roll option may be combined with the
         `[s:] </rptools/wiki/s_(roll_option)>`__,
         `[g:] </rptools/wiki/g_(roll_option)>`__,
         `[gt:] </rptools/wiki/gt_(roll_option)>`__, and
         `[st:] </rptools/wiki/st_(roll_option)>`__ options. Blank
         messages will not be shown to a certain user if an entire
         message is invisible to that user due to these roll options or
         the `[h:] </rptools/wiki/h_(roll_option)>`__ roll option.

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=w_(roll_option)&oldid=3987"

