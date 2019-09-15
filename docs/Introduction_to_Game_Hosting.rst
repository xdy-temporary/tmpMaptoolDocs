.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Game Hosting}}

.. raw:: mediawiki

   {{Beginner}}

__TOC__

Introduction
============

As seen in the `Introduction to Mapping <Introduction_to_Mapping>`__,
MapTool lets you create virtual maps and virtual "miniatures" (which are
known in MapTool jargon as `tokens <Introduction_to_Tokens>`__) to be
used for playing a roleplaying game session, much like you would use a
real map and real miniatures on a tabletop. In fact, that's why we call
MapTool a "virtual tabletop," or "VTT." In this guide, we'll walk
through MapTool's fundamental reason to be: sharing a map with other
players via the Internet.

**Note:** MapTool is not *only* useful for online play - many people use
it for their face to face sessions too, because you can do things with a
virtual map that you can't do with a physical one. Also, you're less
likely to dump Mountain Dew on it. However, this guide will assume that
you're playing online.

The Introduction to Mapping guided you through the basic steps to get
MapTool, open it up, and put a map and some tokens on it. It also talked
about saving Campaign Files, how you can move and zoom the map, and how
to move tokens around. These are essential features of the program,
without which none of the rest would be worth reading about!

Since hosting is no fun without people connecting to your game, the last
section of this guide covers how to connect to a MapTool server. You'll
need to tell your friends how to do that, so make sure to read that
section!

Finally, since this guide is about *hosting* an online game, "you" will
always mean "the person who is running the server."

Architecture
============

When used for online gaming, MapTool uses a *client-server*
architecture. In other words, one person (usually the GM, but not
always) uses MapTool to start a *server*, and the other people in the
group then connect to that server as *clients*.

Once you start the server and everyone is connected, the campaign file
(with all the maps, tokens, and other info) is then shared among all the
players, so that everyone sees the same map and can watch as they and
their friends move tokens around, enter text in the chat window, and
have a great time.

.. _a_word_about_networking_stuff:

A Word About Networking Stuff
=============================

One of the challenges in setting up a MapTool game (like many
client-server applications, including many other Virtual Tabletop
programs) is configuring your home network to permit your friends to
connect to your MapTool server.

There are several ways to set up your network to allow Maptool to be
hosted over the internet. UPnP, port forwarding, or an external Virtual
Private Networking software package. Depending on your computer, ISP,
and hardware (such as cable/DSL modem and/or router), will determine
which of these options will work for your setup - with the wide
variation in home networks and networking hardware, it's not possible to
give a single set of rules that will guarantee success.

UPnP
----

An alternative to port forwarding - if it's available on your router -
is called *UPnP* (short for *Universal Plug-and-Play*). This feature,
instead of permanently saying "Port XYZ traffic goes here!", will
instead tell the router "for a little while - while we're playing - I'm
gonna have to go ahead and ask you to open up Port XYZ for us. That
would be *greeaaaat*."

In other words, it makes the handling of ports and incoming and outgoing
traffic a little more seamless and simple. Of course, the downside is
that not everything supports UPnP, and you'll have to figure out whether
your network can do it. However, if your network hardware supports UPnP,
it is *by far* the easiest way to get your MapTool server up and
running.

.. _port_forwarding:

Port Forwarding
---------------

For home networks that use a router or physical firewall, you will
probably need to configure *port forwarding.* This is a mechanism by
which information coming *to* your network, and arriving on a specific
*port*, is sent to the right place *inside* your network. This is
important for you as the MapTool server person, since your friends need
to be sending information to the right place!

The specifics of configuring port forwarding will depend on your
hardware, so you'll have to check your manual for that one. But the
basic idea is that you indicate two things to the
router/switch/firewall:

#. Which port MapTool will use (more on MapTool ports later!) - this is
   telling the router "information will be coming in on Port XYZ; pay
   attention!"
#. Which computer, inside the network, that information needs to go to -
   basically, "and when you see information coming in on Port XYZ, send
   it *here*"

   #. Incidentally, setting up port forwarding also tells the router
      where it can stick *outgoing* information, too.

That is port forwarding in a nutshell, and the reason you need to set it
up is that most routers (especially if they're configured securely and
properly) are not going to just allow random incoming information to get
through.

.. _more_and_better_networking_information:

More and Better Networking Information
--------------------------------------

I was all set to write an elaborate section on networking, when I
realized that there is an excellent
`FAQ <http://forums.rptools.net/download/file.php?id=116>`__ written by
Azhrei at the `MapTool Forums <http://forums.rptools.net>`__. If you are
unfamiliar with concepts like Port Forwarding, configuring your router,
or how networks work (in general), please read the FAQ.

If you are familiar with network configuration and managing your home
network (especially if you can set up software to act as a server, or
have set up port forwarding on your network for other applications),
setting up MapTool to act as a server will be old hat: you'll basically
need to configure port forwarding or UPnP on your router to permit
MapTool network traffic to pass.

If you need specific information on port forwarding configuration for
your network hardware, check out
`Portforward.com <http://www.portforward.com>`__ for an extensive
collection of how-to documents for specific network hardware and
specific software packages.

On the other hand, if all that stuff above made no sense to you: read
the `Networking
FAQ <http://forums.rptools.net/download/file.php?id=116>`__! All will be
revealed!

Now, let's get on with it.

.. _starting_up_a_maptool_server:

Starting Up a MapTool Server
============================

Assumptions
-----------

From here on out, these instructions assume that you have configured
your network to handle MapTool traffic (via port forwarding or UPnP, for
example). If not, you'll have to figure out how to do that before it
will be possible to start a server that your friends can use.

.. _the_start_server_dialog:

The Start Server Dialog
-----------------------

.. figure:: mt-file-menu-startserv.jpg
   :alt: mt-file-menu-startserv.jpg

   mt-file-menu-startserv.jpg

.. figure:: StartServerDialog.png
   :alt: StartServerDialog.png

   StartServerDialog.png

1. Go to **File > Start Server**.

2. You will now see the **Start Server** dialog. There are a lot of
options here.

.. _server_options_and_settings:

Server Options and Settings
---------------------------

.. _configuration_settings:

Configuration Settings
~~~~~~~~~~~~~~~~~~~~~~

-  **Username**: this is the name that will appear in chat and in the
   Connections window; you can set it to be anything you like.
-  **Role**: this drop down box lets you tell MapTool what *kind* of
   user you are: are you the GM (and therefore in possession of Total
   Cosmic Power over all of the MapTool functions?) or are you a player,
   who lives at the GM's every whim (or, in other words, only has access
   to player functions)? Note that a game can have more than 1 GM!
-  **Port**: A *very* important setting, this is where you tell MapTool
   what port you've configured your router to forward. If you give it
   the wrong port, MapTool traffic will be unable to enter or leave your
   network, and you will have no game!
-  **RPTools Alias**: this field allows you to set up an "alias" for
   your server to appear on the RPTools server registry. It basically
   lets you tell your players "look for the server named Awesome Server
   and connect to it," instead of "connect to the server at IP Address
   123.45.678.9"
-  **Passwords**: you can protect access to your server by configuring
   passwords. Setting a password on the server is optional; however, if
   you leave it blank, anyone who can find your server can connect to it
   as a player. There are two password categories:

   -  **GM**: the GM password is used to provide someone with full
      access to the campaign remotely, though there are a small number
      of features which cannot be done remotely, such as loading a
      campaign. The GM password is typically used for a secondary GM so
      that GM duties may be shared, but can also be used in cases where
      the GM may not be able to get hosting set up properly and has one
      of his players host the session.
   -  **Player**: people connecting to the server in the "Player" role
      will use this password to connect.

.. _ownership_vision_and_behavior:

Ownership, Vision, and Behavior
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  **Strict Token Ownership**: MapTool uses a concept called "token
   ownership" to control who can select, move, or look at the
   `properties <Macros:Glossary#P>`__ of a particular token. If you
   enable *Strict Token Ownership*, only the *owner* of a particular
   token may perform any actions on it - everyone else is confined to
   looking at the token.
-  **Players can reveal vision**: MapTool has a vision and fog-of-war
   system (where you can configure how tokens "see" the map). With this
   option enabled, players can reveal the area that is "visible" to
   their token without GM intervention (in other words, an area hidden
   to the token is covered by Fog of War, and appears opaque on the
   screen; when you reveal it, the opaque overlay is cleared, and the
   map underneath becomes visible). Otherwise, the GM must do all
   reveals.

   -  **Auto Reveal On Movement**: Enabling this will let tokens reveal
      the map as the tokens are moved.

-  **Use Individual Views**: in the vision system mentioned above,
   player tokens can either "share" their vision (*i.e.*, everyone sees
   what one player character sees) or they can have individualized
   views.

   -  **Use Individual FOW**: means that each token's don't share the
      exposed areas and can only see where the individual token as been.

-  **Restricted Player Impersonation**: This means that players can only
   impersonate tokens that they have ownership (see above) of
-  **Players Receive Campaign Macros**: MapTool lets you write
   `macros <Macros:introduction>`__, which are basically sequences of
   text, token, and dice rolling commands used to automate certain
   activities - basically, a short script that does *something*. The GM
   can create "Campaign Macros" which become available to all players if
   this option is checked.
-  **Use Tooltip for [] rolls**: Enabling this option makes any dice
   roll you enclose in square brackets show only the roll result, and
   display the full roll details if you hover your mouse over the
   result.

.. _testing_the_connection:

Testing the Connection
----------------------

Before you start your server, it is a good idea to hit the **Test
Connection** button. This will send a message out to a server at
RPTools.net asking that it attempt to connect to your computer - in
other words, the RPTools connection testing server will find out if it
can see your computer over the network!

What you want to see is **Success! I can see your computer!** If you get
that, you can be pretty sure that your server will be visible when you
start it up.

If you do *not* see a message proclaiming a successful connection test,
you will need to investigate port forwarding and your network
configuration to make sure you have the right ports configured and
everything properly arranged.\ :sub:`This description is deprecated.`

**Note:** The test connection was frequently broken and has so caused
lots of trouble. Thus it was removed in b76 (or so). The Start Server
Dialog now has a button "Networking Help" that leads you to the
Networking FAQ in the forums. This is really the place to go. Read it
(yes, read it not skim it!) and follow all steps. If that doesnt help
the community will very likely be able to help you out.

For a quick connection test you can use
canyouseeme.org\ `1 <http://canyouseeme.org/>`__

.. _get_your_connection_information_and_tell_your_friends:

Get your Connection Information and Tell Your Friends
-----------------------------------------------------

.. figure:: mt-file-menu-cinfo.jpg
   :alt: mt-file-menu-cinfo.jpg

   mt-file-menu-cinfo.jpg

.. figure:: connection-info.jpg
   :alt: connection-info.jpg

   connection-info.jpg

Assuming that you had a successful connection test, and you clicked
**OK** to start the server, you can then check out your *Connection
Information* to double-check the settings. These settings will need to
be passed on to your friends so that they can connect to the server.

1. Go to **File > Connection Information**.

This will display what MapTool currently knows about your computer.
Since you haven't started a server quite yet, you'll just see your
computers internal and external IP addresses (this is useful info,
though, especially if you haven't quite set up port forwarding!).

When a server is started, you will also see the name of the server (if
you give it one), and the network port that server traffic will use.

2. Provide this information to your friends: tell them the *Server Name*
(a.k.a. the RPTools Alias, if you set one), the *external* IP address,
and the *port*. They will need to put this into the **Connect to
Server** dialog when they attempt to log in to your server.

| 

.. _connecting_to_a_maptool_server:

Connecting to a MapTool Server
==============================

The steps leading up to this point walked you through setting up a
MapTool server so that people can connect to it. Of course, if you don't
have anyone connecting to your server, things are going to get pretty
boring pretty quick. These steps are focused on your friends who will be
connecting *to* the server you just created.

.. _assumptions_1:

Assumptions
-----------

The following information assumes that all of the following are true!
Lacking any of these is going to make for a very short trip.

-  You have friends
-  You have a MapTool server running
-  Your friends know the following:

   -  Either the server's *Name* OR the servers *External Address* is
      (or preferably, both!)
   -  What the appropriate *password* is (either GM or Player password)
   -  What *Port* the server is using

-  **VERY IMPORTANT: Your friends are using the same version of MapTool
   that you are using!**

.. _open_the_connect_to_server_dialog:

Open the Connect to Server Dialog
---------------------------------

.. figure:: mt-connect-to-server.jpg
   :alt: mt-connect-to-server.jpg

   mt-connect-to-server.jpg

If the assumptions mentioned above are met, here's what you tell your
friends:

1. Go to **File > Connect to Server** to see the **Connect to Server**
dialog.

2. Enter a *User name*. This can be anything your friends wish.

3. Enter the password (which you set when you started the server).

4. Choose your *Role*. Your friends can connect as a GM, or as a Player.
Make sure that they pick the right role for the password you're using!

| 

.. _choose_how_you_will_connect:

Choose how You will Connect
---------------------------

The **Connect to Server** dialog presents three ways to connect to a
running server.

RPTools.net
~~~~~~~~~~~

.. figure:: mt-connect-registry.jpg
   :alt: mt-connect-registry.jpg

   mt-connect-registry.jpg

This tab (which is shown by default) lists all of the servers listed at
the RPTools.net *Server Registry.* When you set up the server, you had
the option to give it an *alias*, which is what appears in this list.
The *Server Registry* stores the connection information for the server,
so your friends can just select the server they want, and hit **OK**.

| 

LAN
~~~

.. figure:: mt-connect-lan.jpg
   :alt: mt-connect-lan.jpg

   mt-connect-lan.jpg

This tab will show any servers that are currently running on the *local*
network. This is for when you want to have a MapTool LAN Party, or when
all your friends are inside the same network (like if everyone bringes
their laptop to your house for game night).

| 

Direct
~~~~~~

.. figure:: mt-connect-direct.jpg
   :alt: mt-connect-direct.jpg

   mt-connect-direct.jpg

A direct connection is just that - your friends bypass the friendly
RPTools.net tab, and simply type the External Address and port number
for the server.

| 

.. _verifying_connections:

Verifying Connections
---------------------

As your friends connect to your MapTool server, you will see
notifications in the **Chat Pane** that people have connected to your
server, which look like:

\ *JQRandom has connected.*\ 

You can also check the **Connections Pane** to see a list of everyone
who is connected to your server. If you do not see the Connections Pane,
go to **Window > Connections** to have it pop into view.

.. _tokens_on_your_map:

Tokens on your Map
==================

When you're running MapTool by yourself, you've got access to every
token and every item on a map, because MapTool assumes that you're the
GM (and, therefore, the All-Powerful God of the tiny world represented
by the Map). However, when you start hosting a game, MapTool has
different roles (mentioned previously) for the different people
connecting. The **GM** role retains it's all-powerful status, able to
select and manipulate anything on the map; however, the **Player** role
has a much more restricted set of options, able to control only those
items that the player has *ownership* of.

Because of that, when you start a server, you will need to make sure
that you give your players ownership of the Tokens they are supposed to
control! This is a common oversight when starting up a new server -
forgetting to set token ownership after your players have connected!

Token Ownership is explained in more detail in `Introduction to
Tokens <Introduction_to_Tokens>`__, but for the purposes of this
tutorial, once you've started a server and you've got your friends
connected as players, do the following for each player connected to the
game:

#. Double click on the token that player will be controlling as their
   Player Character (see Note, below).
#. Set the token type to PC.
#. Go to the **Ownership** Tab
#. Check the box next to the *player's* name, granting them ownership of
   the token.
#. Click **OK** to save the changes.

Once you do this, the players will be able to move and edit their own
tokens. You can also grant ownership of a token to All Players, if
everyone needs to manipulate it.

**NOTE**: players can have ownership of NPC tokens if you wish (the
process is the same, except you don't do Step #2); however, you'll at
least need to make sure they own their own player token!

`Category:MapTool <Category:MapTool>`__
