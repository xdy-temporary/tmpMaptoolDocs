=====================================
Talk:Editor:Wanted Pages - MapToolDoc
=====================================

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

   .. rubric:: Talk:Editor:Wanted Pages
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

            -  `1 Current Token <#Current_Token>`__
            -  `2 Introduction to Lighting and
               Vision <#Introduction_to_Lighting_and_Vision>`__
            -  `3 Short Pages <#Short_Pages>`__
            -  `4 Branching and Looping
               Tutorial <#Branching_and_Looping_Tutorial>`__

         .. rubric:: Current Token
            :name: current-token

         With a whopping 73 links(Current Token 37 / Token:Current Token
         36), it seems obvious we could clean up a lot of our 'red'
         links by creating this page. In the meantime though, I'm going
         to go through the
         `Special:WantedPages </rptools/wiki/Special:WantedPages>`__ and
         clean up red links that either point to the same conceptual
         target in different ways, or point to a target that exists
         already under a different name.
         `zEal </rptools/wiki/User:Verisimilar>`__ 21:01, 4 April 2009
         (UTC)

         -  I have a feeling this will be one of the Short Pages
            mentioned below, but I can write a short and sweet page
            defining "Current Token," no problem. Do we want to fix the
            namespace first? Should I just create a new page called
            "Current Token" without the "Token:" namespace?
            `Rumble </rptools/wiki/User:Cclouser>`__ 21:12, 4 April 2009
            (UTC)

            -  I'm going through and changing all the red links that
               point to the namespace version.
               `zEal </rptools/wiki/User:Verisimilar>`__ 21:17, 4 April
               2009 (UTC)

         -  Okay, `Current Token </rptools/wiki/Current_Token>`__ is
            written. I find that it's a lot harder to explain clearly
            than you would think. Suggestions and revisions are welcome.
            `Rumble </rptools/wiki/User:Cclouser>`__ 22:02, 4 April 2009
            (UTC)

         .. rubric:: Introduction to Lighting and Vision
            :name: introduction-to-lighting-and-vision

         This one is all the way at the bottom of the list, as it looks
         like a planned article that Rumble is going to write. As much
         as I like the title, would it be better to try to remain
         semantically correct(in the context of MapTool) and call it
         Introduction to Lights and Sights?
         `zEal </rptools/wiki/User:Verisimilar>`__ 21:04, 4 April 2009
         (UTC)

         For purely aesthetic reasons, I think it should be
         *Introduction to Light and Sight*, but otherwise, the name
         change is fine - I try to make sure I use exactly the same
         wording that MapTool does. I don't always succeed...but I try.
         `Rumble </rptools/wiki/User:Cclouser>`__ 21:10, 4 April 2009
         (UTC)
         It occurs to me that I really don't use light and sight much at
         all when we play, so I'm probably not the best person to write
         this tutorial. Is there any brave soul willing to dive in? It
         will be image heavy and probably laborious.
         `Rumble </rptools/wiki/User:Cclouser>`__ 17:58, 6 April 2009
         (UTC)

         On the other hand (replying to my own comment), sight/light are
         changing *rapidly* at the moment. I wonder if holding off on
         that one is a better idea, at least until 1.3's light stuff
         stabilizes. `Rumble </rptools/wiki/User:Cclouser>`__ 20:21, 6
         April 2009 (UTC)
         .. rubric:: Short Pages
            :name: short-pages

         Rumble and I had a brief exchange in revision comments about if
         a short page like Halo is necessary given the Glossary. Instead
         of discussing that single article's potential, I think we would
         benefit more from discussing how short a page should be allowed
         to be. I personally feel that there is nothing wrong with short
         pages; although headings help a lot, they don't completely
         overcome the "Wall of Text" effect that a user might encounter
         if they were looking for a relatively short explanation of a
         particular concept, and all they could find were some of our
         (very well written) lengthier introductions/tutorials.
         `zEal </rptools/wiki/User:Verisimilar>`__ 21:08, 4 April 2009
         (UTC)

         .. rubric:: Branching and Looping Tutorial
            :name: branching-and-looping-tutorial

         I think something to put on the plate is an actual tutorial on
         branching and looping, *especially* with regard to using the
         CODE: option, because that comes up frequently on the forums
         and it's not particularly transparent in use. I can work on one
         - in fact, I have a series of macros I wrote for Dorpond that
         might be a perfect step-by-step (as the conversation on the
         forum progressed, the macros got more complex).
         `Rumble </rptools/wiki/User:Cclouser>`__ 01:10, 5 April 2009
         (UTC)

         Sounds like a great idea, I had already planned on breaking up
         the roll options into more syntactically focused individual
         articles(mimicking the function articles in scope), and your
         idea compliments that well. I recommend you use the new roll
         option template I just created when writing it, you can find
         basic usage details on the
         `Help:Editing </rptools/wiki/Help:Editing>`__ page.
         `zEal </rptools/wiki/User:Verisimilar>`__ 01:27, 5 April 2009
         (UTC)
         I'm using the *code* template, and I find that it doesn't
         handle an equals sign gracefully (or maybe I'm doing something
         wrong) - if I write {{code|myHP=30}}, I end up with {{{1}}}.
         However, if I put a code bit in that doesn't have an equals
         sign in it, it's fine. I assume that has to do with the
         template looking for equals signs to tell it what to place in
         the template. `Rumble </rptools/wiki/User:Cclouser>`__ 12:58, 5
         April 2009 (UTC)
         Yep, there are a few nuances(annoyances) when it comes to using
         templates, but most of them are easy enough to work around. The
         major two is that \| and = are special characters within a
         template, so you have to use special templates to display them
         within another template, {{!}} and {{=}} respectively. The
         broken bar(pipe) normally only comes into play if you're trying
         to create a table within a template. This isn't a problem
         exclusive to our wiki, it's a problem with the way MediaWiki
         parses templates:
         `Wikipedia:Template:! <http://en.wikipedia.org/wiki/Template:!>`__
         `Wikipedia:Template:= <http://en.wikipedia.org/wiki/Template:%3D>`__
         `zEal </rptools/wiki/User:Verisimilar>`__ 21:24, 5 April 2009
         (UTC)

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Talk:Editor:Wanted_Pages&oldid=2997"

