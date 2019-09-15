==================================================
Introduction to Campaign Repositories - MapToolDoc
==================================================

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

   .. rubric:: Introduction to Campaign Repositories
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

         .. container:: template_languages

            Languages:  English
             • \ `español <Introduction_to_Campaign_Repositories/es>`__\  • \ `français <Introduction_to_Campaign_Repositories/fr>`__\ 
             • \ `日本語 <Introduction_to_Campaign_Repositories/ja>`__\ 

         .. container:: template_beginner

            | BEGINNER
            | THIS IS A BEGINNER ARTICLE

         | 

         .. rubric:: What is a repository?
            :name: what-is-a-repository

         A campaign repository is a set of files (mostly images) that
         are used in a campaign. By hosting a repository someplace other
         than the GM's computer you can help speed up the image download
         time of your players, making the game run smoother in general.

         You must have some externally hosted web space to properly use
         a repository. Many ISPs give you some space you can use for
         this type of purpose. If your ISP does not provide this you can
         usually find cheap (and even free, in some cases) web hosting
         if you search around.

         Unless you are running MapTool from a really beefy server-class
         machine on a T1 connection (or you picked a really bad web
         server) you're almost guaranteed that clients will be able to
         download files from any hosted web storage faster than they
         will from your machine. This is one of the main benefits of a
         repository.

         .. rubric:: Creating a repository
            :name: creating-a-repository

         To create a repository file, open your campaign in MapTool and
         go to File -> Export -> Campaign Repository File. This will
         create a zip file that contains the repository information.

         Unzip the file. (This is very important! MapTool cannot use the
         repository if it remains zipped!) Inside should be a folder
         called "assets" and a file called index.gz. Upload both the
         assets folder and the index.gz file to your web storage. Make
         sure they are in the same directory. (Do not put the index.gz
         file *inside* the assets folder. It should be at the same level
         as the assets folder.)

         Make a note of the URL for to your index.gz file. You can test
         the URL by typing it or copying and pasting it into your
         browser's address bar. If you have the address right you should
         see a page full of letters and numbers that won't mean much to
         you.

         In MapTool, go to Edit -> Campaign Properties then go to the
         Repositories tab. Delete any links that are already there, then
         add the URL of your index.gz file.

         Save your campaign. Now when clients connect to your server
         they will get the campaign files from the repository online
         instead of your PC.

         If you make changes to your campaign file you will need to
         re-export the campaign repository file and re-upload it to your
         web space. You will not need to re-add the URL to the
         Repositories tab of the Campaign Properties unless you changed
         the location where your files are being kept.

         .. container:: template_languages

            Languages:  English
             • \ `español <Introduction_to_Campaign_Repositories/es>`__\  • \ `français <Introduction_to_Campaign_Repositories/fr>`__\ 
             • \ `日本語 <Introduction_to_Campaign_Repositories/ja>`__\ 

      .. container:: printfooter

         Retrieved from
         "http://lmwcs.com/maptool/index.php?title=Introduction_to_Campaign_Repositories&oldid=5634"

