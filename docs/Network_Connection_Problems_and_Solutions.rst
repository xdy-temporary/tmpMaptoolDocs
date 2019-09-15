.. contents::
   :depth: 3
..

.. _network_connection_problems_and_solutions:

Network Connection Problems and Solutions
=========================================

this is an import from the Network FAQ PDF v1.7 from
`1 <http://forums.rptools.net/viewtopic.php?f=22&t=3370>`__

Assumptions
-----------

MapTool will start via either WebStart or by executing the proper file
for your operating system that resides in the ZIP archive or DMG image.
If you do not get the MapTool splash screen or the default "Grasslands"
background map when you start MapTool, this document will not help you.

Symptoms
--------

When someone else attempts to connect to your server, their MapTool
seems to pause for a long time with the Connecting message and then
finally times out and gives up. The error message may say “Connection
timeout” or it may be something more generic like “Could not load
campaign” (which indicates an inability for the network to pass data
back and forth).

The server running on the hosting computer is not seen by Internet
connection testing tools such as CanYouSeeMe.org. These testing tools
should be started after the MapTool server has been started via the
**File → Start Server...** dialog. More discussion of these tools is
covered after the next section on terminology and theory of operation.

.. _background_information:

Background Information
----------------------

MapTool uses TCP/IP to make a connection from each client to the server.
Without going into a lot of nitty-gritty detail about how TCP/IP works,
I will provide a short (and amazingly accurate) analogy of TCP/IP using
the phone system. The rest of this section can be skipped if you are
confident of your knowledge in networking basics and already know the
difference between a “switch” and a “router”. However, forum users will
expect you to be familiar with the information in this section if you
ask for help there. At a minimum you should be familiar with the
terminology.

.. _a_simple_network:

A simple network
~~~~~~~~~~~~~~~~

The picture below depicts multiple computers on a local area network
(LAN). Each computer is labeled with a hostname – a name used to
uniquely refer to that particular computer. You can think of these names
just like the names of your friends, your family, your employer, and so
on: when you need to talk to one of these people, you look up their
phone number in the phonebook and then pick up the phone and dial.

.. figure:: lan1.png
   :alt: Image:lan1.png

   Image:lan1.png

In the picture, let's assume that PC1 is the server and PC2 and PC3 are
clients. In order for the clients to contact the server, they need some
way to locate PC1 on the network. This is the phonebook look up that was
discussed in the last paragraph. One look up technique is called "DNS"
(Domain Naming Service) and is very common on the Internet. The primary
function of DNS is to convert hostnames into IP addresses very similar
to the way you use a phonebook to convert a person's name into their
phone number. However, if you dial the number of your best friend very
often, are you going to have to look it up in the phonebook? Probably
not! You probably have it memorized or stored in your local contact
list. TCP/IP is the same way: if you know the IP address of a machine
you can use that instead of the hostname.

MapTool provides a shortcut to DNS called the RPTools Registry. When you
open the **File → Connect to Server**... window, you'll see a list of
MapTool servers that have registered with RPTools.net. This allows a
client to just double-click the correct entry in order to attempt a
connection. The client will contact the RPTools.net web site and
retrieve the IP address of the server. Once it has this information, the
client will use the IP address of the server to make their connection.
So the IP address is the "phone number" that you use to contact the
server. The client now knows how to contact the server and send/receive
data. However, the RPTools.net technique is only for connecting to
MapTool servers outside your own LAN – on your LAN you should pick a
server from the **LAN** tab. In fact, it's likely that using the RPTools
registry will fail even if your server is working fine; this is
discussed in more detail later.

Whenever the client wants to send a packet of data to the server, it
prepends the IP address and puts it out onto the network. Each machine
between the client and server forwards the packet to the next one in the
link. In the picture above, there are no intermediate machines since all
machines are connected to the same wire, but when communicating over the
Internet there will be tens or hundreds of intermediate machines. An
example of an intermediate machine is shown in the next picture.

When you call your family or friends, the phone number is all you need
to make contact. But if they are at work, you may need to use more than
a phone number – you may need an extension number as well. In the terms
of TCP/IP, that extension number is the port number that the server
allocates when it starts. This port number allows multiple applications
on a single machine to be "listening" for incoming phone calls. The
default port number for MapTool is **51234**. Other default port numbers
include 80 for web servers and 25 for email servers. Port numbers less
than 1024 are reserved for well-known server applications and those from
1024 to 5000 are reserved for local use, so if you change the MapTool
port number, **be sure to choose one larger than 5000**. In summary, the
IP address and the port number uniquely identify an application on the
computer and are used to deliver packets between the two computers, the
same way that a phone number and extension number uniquely identify a
person or department in a company.

When a MapTool server starts it lets other machines on the same network
know of its existence. This is evidenced by the clients being able to go
to the **LAN** tab when they choose **File → Connect to Server**... and
see the server appear in the list. This technique is similar to the
phone company giving you a new phonebook that has been updated with new
contact information every time someone in your nehgiborhood changes
their phone number! In the real world that doesn't happen, but in the
electronic world it's almost required because things can change so
quickly. (It doesn't really work like this, but this is a functional
description and not a treatise on the implementation :)).

.. _connecting_outside_your_own_network:

Connecting outside your own network
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

When all of the computers, both server and client(s), are on the same
network the situation is pretty simple as we discussed above. But what
happens when the server is remote from the clients? In this situation,
routing the client's phone call through a lot of other machines is
required before the phone rings at the server's location. And if you've
ever tried to contact the CEO of a company directly, you can be sure
that their secretary is going to run interference!

.. figure:: lan2.png
   :alt: Image:lan2.png

   Image:lan2.png

One of the jobs of the CEO's secretary is to filter incoming messages
and decide which ones get to the executive and which ones don't. This is
why it can be of more importance to have the secretary's ear than the
CEO's! In comparison to a network, the router's job is the same as the
secretary's.

I'm using the term router pretty loosely here. In this guide, I use the
term router to mean any device between your computer and the Internet
whose job is to filter network data. The primary goal of a router is to
protect your computers from those on the Internet – it doesn't let them
succeed in connecting to your computer. Secondary goals are to allow
multiple IP addresses within your home while only allocating a single IP
address on the Internet. But we're getting ahead of ourselves a little
bit...

In the case of MapTool, when a client calls a server, it's possible that
the server's router might block that incoming request. In that
situation, the client hears a ring-ring on their end, but the MapTool
server never knows that the call was even made because the router
blocked it. This will be reported as “Connection Failed: timeout” or
something similar. In the picture above, any time PC2 or PC3 tries to
contact PC1, they have to get through the router first. Most commercial
routers have firewall software built into them. Routers that cost
thousands of dollars will have more sophisticated firewalls than the
"home use" router you bought at the BigBox store, but the goal of
filtering traffic remains the same. And that brings us to our next
topic...

.. _port_forwarding_and_upnp:

Port forwarding and UPnP
~~~~~~~~~~~~~~~~~~~~~~~~

Most routers, just like most secretaries, can be told that some traffic
is more important than other traffic and that it should be routed
directly through. Can you imagine how much trouble the CEO would be in
if he didn't take his wife's (or her husband's) call in a timely manner?
A good secretary can actually figure some of this out on their own. For
example, the CEO calls his wife and they chat for a few minutes. When
the wife calls back in five or ten minutes, you can bet that the
secretary will simply route it straight through. Computer firewalls can
be told to do the same thing. This is called **port forwarding**.

Essentially, when a call to a certain IP address and port number is
about to be blocked by the router, it will check its exception list. If
the exception list says to go ahead and allow the call to proceed, the
router forwards the call to the IP address and port number of the CEO's
desk. This is what happens when you have a router sitting between your
Internet connection (DSL, cable modem, satellite, dial-up, or any other
type) and your home computer(s). The router will act as a firewall and
not allow any incoming phone calls unless you've specified a list of
exceptions. The actual technique for how to accomplish this varies from
router to router, so the MapTool forums recommend that the home user
visit `2 <http://www.portforward.com/>`__ and search for their
particular router model for instructions.

Note that port forwarding can be turned on and left that way or it can
be enabled on the router only when it is going to be used. For security
purposes, it is best to only have it turned on when you need it and turn
it off when you're done. Note that the router doesn't block outbound
calls that the CEO makes; the CEO can pick up the phone and dial his
wife without the secretary stopping the call. This is like running a
browser and connecting to a web site – the router doesn't get in the
way. But if the web site were to try contacting your browser directly,
the request would be blocked.

This is a problem for us: we **want** to run a MapTool server and we
**want** the router to let that traffic through! Because routers (and
firewalls) are **supposed** to be blocking exactly that kind of traffic,
we don't have any choice. We must visit that URL given above and figure
out how to configure our routers. Unfortunately, not everyone relishes
the idea of reprogramming their router the way I do! Yes, hard to
believe, but not everyone is a geek. *(Geek = cool and trendy computer
person, Nerd = not-so-cool and trendy computer person, and Dork =
totally un-cool computer-person-wannabe. You see? I told you there was a
lot of terminology in this section!)*

So there's another technique that can be used: the CEO could explicitly
tell the secretary something like, "any calls that come in on extension
80 should be routed directly to my desk." Now the secretary can pass
calls directly to the CEO and not worry about needing to filter them.
Maybe the CEO is expecting a call from a certain individual and wants to
take the call immediately. Or perhaps the CEO has a "private line" that
the secretary monitors but allows calls to "ring through". Having such
an automated system for your router is called UPnP, short for Universal
Plug-n-Play. (An alternative is called NAT-PMP, but they are
functionally the same so the second won't be mentioned again.)

If you have turned on this feature on your router, then the MapTool
1.3.b23+ server, or any other program running on your network, can tell
the router to allow certain ports through for a limited period of time.
You will need to refer to your router manual for instructions on how to
verify that this feature is enabled. If this feature is turned on in
your router you can try enabling it in MapTool by checking the **Use
UPnP** checkbox in the **File → Start a Server**... window.

**You must not use both port forwarding and UpnP!** If you try to use
both at the same time, most secretaries will simply become confused and
not know what to do at all when a call comes in – you don't want that do
you?!

.. _network_address_translation_nat:

Network Address Translation (NAT)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Unfortunately, many companies don't have enough phone lines for each
employee to be on the phone all at the same time. (Well, *maybe* that's
unfortunate. I can think of a few situations where that's not such a bad
thing!) When a customer calls the company, they use a single phone
number. The switchboard operator for the company will convert the number
the customer dialed into the internal number used by the company's phone
system (sometimes called a PBX).

The Internet requires such a feature. There are only a certain number of
IP addresses that can be used, so *network address translation* was
devised to help prevent them from being used up too quickly. For
example, your author has a cable modem at home. Connected to the cable
modem is a router. This router is assigned a *public IP address* by my
ISP, but the rest of the computers in the house receive a randomly
assigned *private network address* from the router. Most routers use
random IP addresses in the range of **192.168.0.2-192.168.0.100** or
something similar. The computers attached to the router don't realize
that they are receiving random IP addresses – they just take what they
get and are happy with it! You can use MapTool's **File → Connection
Information**... menu option to determine what your private IP address
is, as well as the external IP address of your router.

When my laptop makes an outbound connection, the router keeps track of
my private IP address so that when the response comes back, it can send
the response to my laptop and not to my wife's desktop or the TiVo or
the laser printer.

.. _advanced_nat_scenario:

Advanced NAT Scenario
^^^^^^^^^^^^^^^^^^^^^

One issue with this technique is that to any computer outside my home
the IP address looks the same for every computer inside the house. This
is why port forwarding is important. When a call comes in to the router
for port **51234**, the router forwards it to a preprogrammed private IP
address. Using this scheme, can I run multiple MapTool servers on my
home network and have different outside computers connect to them? It
might appear that the answer is "no" because there's only one "port
51234". However, if a different port number is assigned to each MapTool
server, the router can be configured to forward each port to a different
private IP address. For example, my laptop, my wife's desktop, and my
TiVo are all on the same network (not really, but we can pretend they
are for the sake of this example). I could forward port 80 on the router
to the TiVo, then when I'm traveling I could find out which shows the
TiVo has recorded by visiting port 80. I could forward port 55555 to my
laptop (port 51234) and port 55556 to my wife's desktop (port 51234).
Notice how the destination port is the same on both, but the outside
port numbers are different? This would allow multiple MapTool servers on
the internal network to be connected to by different outside computers.
This is exactly like having a company with multiple outside extension
numbers. When a customer calls the company, the secretary figures out
who the call is for and sends it to the right person. The fact that
there are two “John Smith” employees doesn't confuse the secretary
because the port forwarding as a different extension number for each
one.

The last example is probably pretty confusing and there's no shame in
going back and reading the last few sentences two or three times. Go
ahead... I'll wait.

Basically, that last example says that the router has two phone
extensions configured (ports 55555 and 55556) and each one is sent to a
different location inside the company. The first goes to my laptop, the
other goes to my wife's desktop. But I don't want to have to change the
port number in MapTool, so I just leave it 51234.

To use a configuration in which the MapTool port number doesn't change,
I can't use UPnP. If I did, and I tried to run MapTool on both my laptop
and my wife's machine at the same time, the router couldn't accommodate
both of us – only one of us could have extension 51234. So I'd have to
reprogram the port forwarding manually on the router. This is also not a
good choice if you're going to use the RPTools Registry feature since
the port number MapTool will give the MapTool registry is not the one
your router will be configured for. Remember: when a player connects to
your server, they will get the outside extension number. If you've
manually set up port forwarding and used a different internal and
external port number then the wrong number will be stored in the
registry.

If I was willing to use different ports for MapTool, then I could use
UPnP. Because UPnP doesn't require you to reprogram your router, this is
the one I recommend. Especially when you consider that you could get a
different private IP address every time you power up your computer!
(Remember earlier when I said the router will give you a randomly
assigned IP address? The truth is that you will probably get the same
address, but to be safe you should treat it as though your machine gets
a different address at each reboot.) This is a much better solution
because if you fill in the **RPTools.net Alias** field on the **File →
Start Server**... dialog, this port number is saved in the MapTool
registry and is the port that other clients will attempt to connect to.

.. _two_routers_and_the_double_nat_problem:

Two Routers and the “Double-NAT” Problem
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

The big issue with NAT is something called "double-NAT". What if there
are **two** routers between the outside computers and the inside server?
It becomes impossible for UPnP to handle this and while the
configuration of both routers is possible, often the home user doesn't
have control over one of the routers. Sometimes the home user can put
one router in “bridged” mode, which essentially turns off the firewall
in that router and tells it to pass all connections straight through.
This effectively eliminates it from the picture. This is a good choice
in cases where your ISP has provided you with equipment and your control
over that equipment is limited. In all other cases of double-NAT,
running a MapTool server will require a VPN solution. Beyond mentioning
the Hamachi program (which is popular on the MapTool forums), further
discussion of VPNs is beyond the scope of this document. Be sure to ask
on the forums if you have this issue. When enough interest is shown,
this document will be updated. (It has happened. See FAQ#12 below for
more information.)

.. _its_a_two_way_street:

It's a two-way street
~~~~~~~~~~~~~~~~~~~~~

The last thing to point out is that all communication must be two-way to
be useful. Yet the secretary on the client end will always allow
incoming data if the client initiated the request in the first place! We
talked about this above, when we discussed the overall flow of the
network traffic. We said that the secretary doesn't get in the way of
outbound calls, only inbound calls. And only the server will have
inbound calls so only the server needs to have port forwarding
configured.

.. figure:: lan3.png
   :alt: Image:lan3.png

   Image:lan3.png

For example, when you type a URL into a browser, the browser makes the
outbound request and the router allows the response to come back in. The
same thing will apply to MapTool; if the client sends a packet to the
server, the client's router will allow the response to get through. This
is one of the security issues in a router; it cannot block traffic that
is a result of a request made by an internal source. (This is the
primary issue with cross-site scripting attacks, which is when a script
embedded on a web page makes a request that the user doesn't know about
and then sends the information to another location, also without the
user's knowledge or consent! Since the script is operating from inside
the company's router, the router cannot know that it should block the
traffic.)

In the following section, a series of common MapTool connection problems
will be discussed, including the symptoms and possible solutions.

.. _step_by_step_problem_diagnosis:

Step-by-Step Problem Diagnosis
==============================

These next steps attempt to solve your network problem without resorting
to the (sometimes slow) turn around time on the forums. If you head to
the forums and don't have the answers to the questions asked by these
steps, you'll be directed here and told to start at Step 1 and progress
through them until a step fails. Some steps may not apply to your
situation and you can skip them. For example, Step 5 discusses wireless
clients not connecting while wired clients do; if you're not concerned
about wireless clients, you can skip that step. Be prepared to identify
which steps you skipped and why you skipped them when you post on the
forum. There's a section later in the document (ref!) which describes
what information you'll need to provide when you post on the forum.
'''These steps ''must ''be done in the order presented here or the
results are ''meaningless *!*'

.. _when_i_click_the_test_connection_button_on_the_start_server_window_i_get_an_error_unable_to_see_your_computer_from_the_internet._what_causes_this_and_how_do_i_correct_it:

When I click the ''Test Connection ''button on the ''Start Server ''window, I get an error, "unable to see your computer from the Internet." What causes this and how do I correct it?
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The **Test Connection** button talks to a server on the Internet. (This
button has been replaced with the **Networking Help** button in current
builds of MapTool. If that's the case for you, check the last paragraph
of this step for help.) Because you're making an outbound call, your
secretary (er, router) will be making the actual call for you and is
responsible for making sure that all data from you is sent to the other
system. If this server out there on the Internet receives a call from
your secretary, it will put the current conversation on hold and call
you back using your secretary's IP address and the port number in the
**port number**''' '''field. This is just like a MapTool client would do
if you were the server for an online MapTool session. But what happens
if your secretary doesn't allow that incoming call to go through? In
that case, you'll get the error message referenced in the question,
"Unable to see your computer from the Internet."

To fix this problem, you either need to enable the UPnP option when you
start your MapTool server (and configure your router to enable UPnP) or
you need to enable port forwarding on your router and configure it to
send all requests for extension number **51234** (or whatever port
you're using for MapTool) to your computer on the LAN. **Don't do
both!** *(Most routers will require that you give them a private IP
address to identify your computer; see the section below, How to Find
Network Information in order to determine that number.)*

Another possible solution is to put the machine that will be running the
MapTool server into the router's *de-militarized zone* or DMZ. This
essentially eliminates all protective services of the router and is not
recommended for long-term use. However, if your MapTool server works
while your computer is in the DMZ you have narrowed down the problem to
an issue with the router.

It is also possible that your operating system has a firewall installed
that blocks the network packets once they arrive at your machine. This
will be handled in more detail in Step 6, but keep going through these
steps one at a time.

Also note that if the **Services.RPTools.net** server is down or some
point between you and that server doesn't forward your request, this
test will appear to fail. If you think the problem is that the RPTools
server might be down (check the '''Announcements '''forum at
`3 <http://forums.rptools.net/>`__ for information), there's currently
not another server available for you to try. You can use a public
service though. For example, you could start a MapTool server (so that
an application is listening on the port) and then test it by visiting
CanYouSeeMe.org `4 <http://www.CanYouSeeMe.org/>`__ using a web browser.
You will be asked for the port number that you want to test and you
should enter the same value as you gave MapTool. The web site will check
to see if the secretary is allowing the call in and report either Error
or Success.

.. _i_have_a_server_running_but_if_i_start_maptool_again_in_a_separate_window_on_the_same_machine_it_cannot_connect_as_a_client_why_not:

I have a server running, but if I start MapTool again in a separate window *on the same machine* it cannot connect as a client! Why not?
----------------------------------------------------------------------------------------------------------------------------------------

There must be a firewall or antivirus setting on the machine that is not
allowing connections to the port you used when you started the MapTool
server. Unless you change it, the default port is **51234**. When
connecting to a MapTool server on the same machine, you should be using
**127.0.0.1** as the IP address — you cannot use an RPTools server
alias.

Linux: On some distributions we've seen comments in the forums that
their machine had incorrect entries in the **/etc/hosts** file that
caused MapTool to fail. You may want to check your file and ensure that
it does not contain an entry for your hostname that points to
'''127.0.0.1 '''or **127.0.1.1**. If it does, comment out that entry and
copy the hostname to the end of the line that contains **localhost**.

.. _i_have_a_server_running_but_clients_wired_into_my_local_network_cant_see_my_server_on_the_lan_tab_in_the_connect_to_server..._window._why_not:

I have a server running, but clients wired into my local network can't see my server on the "LAN" tab in the *Connect to Server...* window. Why not?
----------------------------------------------------------------------------------------------------------------------------------------------------

When a client selects the '''LAN '''tab, it sends out a request to on
the LAN for servers to identify themselves. All servers on the LAN are
supposed to respond so that they can be shown in the list of machines.
Either the server machine is running software that blocks the request
from getting to the MapTool application (firewall or virus protection
software) or the client has software that is blocking the server's
response so that the client never sees it (this is less likely, but if
it is the problem it will be because of a firewall package on the
client).

Try turning off the firewall at one or both ends of the connection and
try again. Once you isolate which machine is causing the problem, you
can configure the software on that machine to allow traffic through on
the specific port that MapTool is using and then turn the software back
on again. DO NOT LEAVE YOUR FIREWALL TURNED OFF INDEFINATELY!

.. _i_have_a_server_running_and_clients_wired_into_my_local_network_can_see_the_server_on_the_lan_tab_but_they_get_errors_when_they_try_to_connect_why_doesnt_it_work:

I have a server running and clients wired into my local network can see the server on the LAN tab, but they get errors when they try to connect! Why doesn't it work?
---------------------------------------------------------------------------------------------------------------------------------------------------------------------

Different ports are used for locating servers than for connecting to
servers. Locating servers is done with UDP (a networking protocol) and
connecting to servers is done with TCP (another networking protocol).
It's possible that a firewall on one of the machines is blocking TCP but
not UDP. This is a rare occurrence though, so if turning off the
firewall doesn't fix this problem, post on the '''RPTools.net '''forums
for additional help. (Read the very last section at the end of this
document for how to post to **RPTools.net**)

.. _i_have_a_server_running_and_local_wired_clients_can_connect_but_not_those_using_the_same_router_via_wireless_why_not:

I have a server running and local wired clients can connect, but not those using the same router via wireless! Why not?
-----------------------------------------------------------------------------------------------------------------------

This is most likely caused by a router that refuses to send packets from
the wireless portion of the network to the wired portion. Some routers
may come configured this way to prevent wireless users from accessing
your local network – they can only access the Internet in this
configuration. You will need to check the manual for your router to
determine if this is the case. You might find the information in the
router manual under wireless bridging or LAN bridging or even just
wireless connections to your LAN. You will need to reprogram your router
before this step will succeed and you can continue to the next step.

.. _i_have_a_server_running_and_both_wired_and_wireless_local_clients_can_connect_but_not_clients_that_are_on_the_internet_why_not:

I have a server running and both wired and wireless local clients can connect, but not clients that are on the Internet! Why not?
---------------------------------------------------------------------------------------------------------------------------------

There is likely a device blocking the request as it travels from the
client to the server. Common sources for this would be your router or
the routers of your ISP. These routers don't block traffic between two
machines on the same LAN, which is why local computers can reach the
server. This is especially common in university and corporate
environments where the owner of the network isn't thrilled about have
random packets entering their network from the outside. (Gee, I wonder
why not!?)

You can check the port forwarding configuration of your router, but the
problem may be with your network provider's router and I doubt they will
let you modify those settings. This can be tested by removing your
router from the network completely and plugging your Internet connection
directly into your MapTool server machine. If this configuration works,
your router was blocking the traffic. If this doesn't work, it was some
other hop in the route that is blocking the packet. If you do this, you
have removed the protective features of the router, so try to get your
router back into place as soon as possible.

You should also check whether your problem is the “double-NAT” problem
mentioned in the Background section at the beginning of the document.

.. _is_it_faster_for_remote_clients_to_connect_to_my_maptool_server_using_direct_or_through_rptools.net:

Is it faster for remote clients to connect to my MapTool server using ''Direct ''or through *RPTools.net*?
----------------------------------------------------------------------------------------------------------

They are both the same. All three tabs on the '''File → Connect to
Server... '''window simply offer different ways of identifying the
public IP address of the server, but once the IP address has been found
the client talks directly to the server. If the server was started with
the '''RPTools.net Alias '''field filled in with a game name, the client
can immediately see which version of MapTool they should be using and
they can start the connection by simply double-clicking on the entry in
the listbox. This makes it very simple for the client as they don't need
to know the IP address or the port number. (They still need to enter a
Player Name and a password, if necessary.)

.. _why_does_maptool_even_have_three_tabs_on_the_connect_to_server..._window_anyway_what_are_they_for:

Why does MapTool even have three tabs on the ''Connect to Server... ''window anyway? What are they for?
-------------------------------------------------------------------------------------------------------

The **File → Connect to Server**... window gives the client three ways
to connect to the server. The **LAN** tab should only (and **always**!)
be used by clients who are connected to the same network as the server,
such as those wired to the same router as the server or those using a
wireless connection to the same router as the server. Those clients will
all have the same network subnet mask (this is like an "area code" in
the telephone analogy, above) so packets can flow directly from the
client to the server.

The **RPTools.net** tab shows only those MapTool servers that were told
to register themselves when the server was started. There is a text
field called **RPTools.net Alias** on the **File → Start a Server...**
window that may be filled in or left empty. When empty, the server is
private because its information is not sent to **RPTools.net**. This
means clients can only connect if you give them your public IP address
and port number (see the next paragraph). When filled in, your server's
version number and public IP address (what shows up in the '''File →
Connection Information... '''window as the “External IP Address”) is
saved on the '''RPTools.net '''server. This allows a client to simply
choose the server from a list instead of typing in an IP address — much
simpler! And they can see which version of MapTool they need as well.
(Note that the '''RPTools.net Alias '''probably will not work to connect
from a client to a server when both are on the same LAN! Use the **LAN**
tab instead. See the first paragraph of this step and read the
Background section, “A simple network,” to learn why.)

The **Direct** tab is for those cases where the server is NOT registered
on **RPTools.net** (so it's a private server as discussed in the
previous paragraph) and yet the clients still need to connect somehow!
The required information is the public IP address and the port number of
the MapTool server.

.. _im_getting_an_exception_in_a_popup_window_while_executing_maptool._what_does_exception_mean_and_how_do_i_correct_it:

I'm getting an exception in a popup window while executing MapTool. What does "exception" mean and how do I correct it?
-----------------------------------------------------------------------------------------------------------------------

An exception happens when the Java runtime environment detects an error
condition that the program hasn't been written to specifically detect.
As it turns out, Java requires the programmer to detect and handle some
exceptions but not others. The "other" category includes what are called
runtime exceptions. Runtime exceptions are things that are unlikely to
happen so the programmer doesn't have to account for them, but they can
only be detected when the program is executed, not when it's compiled.
Examples are things like '''FileNotFoundException '''or **IOException**.
Here are some of the common exceptions that can occur and things to
check as possible problems. This list is not exhaustive; it's just the
common ones:

#. InvocationTargetException: This exception is the result of the
   program trying to convert a string of characters into an object that
   will be used internally. Examples include converting a hostname into
   an IP address and converting a dotted-decimal IP address into its
   internal format. If you see this exception, try to determine if some
   data that you provided to MapTool had a typo in it and fix the typo.
#. ClassNotFoundException: This exception happens when a Java program
   tries to locate some code that it needs and can't find it. Common
   causes include a corrupted installation (try reinstalling Java) or an
   incorrect '''CLASSPATH '''setting. (The '''CLASSPATH '''tells the
   Java runtime environment where to look for pieces of compiled code.
   It is normally set automatically during the Java installation
   process.)
#. NullPointerException: This is a straight-up programming error. :) It
   represents the program trying to access data using an invalid
   variable. If you receive one of these, please cut and paste the block
   of text that corresponds to the exception into a posting at the
   RPTools.net forum for the developers to look at. Note that pasting an
   image of the error is not helpful, as our programmers can't extract
   the text information that we actually need.

.. _none_of_the_above_are_problems_for_me_yet_one_specific_network_card_for_one_particular_computer_doesnt_work._do_you_have_any_ideas:

None of the above are problems for me, yet one specific network card for one particular computer doesn't work. Do you have any ideas?
-------------------------------------------------------------------------------------------------------------------------------------

There have been reports that many network cards might require that
certain options be modified on Windows systems. There are no reports of
OSX- or Linux-specific cases of this problem.

To do this, open the Windows Device Manager and open the properties for
your network interface. In the Properties tab should be a drop-down list
of various options for your hardware. The two that most frequently are
problems are Hardware Checksumming (also called Checksum Offload and
other names) and Jumbo Frames. The first one tries to do some math
related to error checking on the network card instead of using your
computer's CPU and while this is a good idea in general, sometimes the
card doesn't get it right and network packets are considered corrupted
by other computers when they really aren't. The second one is a similar
issue where larger packets than normally allowed on a network are sent,
confusing other machines on the network. If these features are turned
on, turn them off and see if that helps, or vice versa. (You may need to
reboot after changing these settings as some drivers only apply changes
when they are initialized.)

Some users who have upgraded to Windows 7 have had problems with Atheros
network cards. The problem appears as an inability for clients to
connect – and stay connected – to the MapTool server, typically with an
error on the client about “unable to load campaign”. This appears to
happen with the Atheros cards that identify themselves as
**AR8121/AR8113/AR8114 PCI-E Ethernet Controller(NDIS6.20)**. This is
discussed more at
`5 <http://forums.rptools.net/viewtopic.php?f=3&t=11916&start=30>`__ To
correct the problem:

From network connection / adapter settings: Atheros network adapter
properties → Advanced tab → Transmit Buffers property. My default value
was 256. Changing value to 512 solved the problem.

.. _what_if_maptool_chooses_the_wrong_network_interface:

What if MapTool chooses the wrong network interface?
----------------------------------------------------

You might find that the Local Address reported by MapTool is not the one
that you think should be used. For example, you might know that your
router hands out private IP addresses in the range of 192.168.1.x and
yet MapTool is reporting a number such as 0.1.0.4 in the File →
Connection Information... window. It might be that Windows has assigned
an IP address to a device and MapTool is using that address and not the
one for your actual network. Some web camera drivers do this under
Windows or I wouldn't have bothered to mention it here. :)

If this is the situation for you, you can change which interfaces are
searched first when an application runs by changing the Network Binding
Order. Under Windows XP, go to the Control Panel and open the Network
Connections window. Go to the Advanced Menu and then Advanced Settings.
Under the Adapters and Bindings section, select the device with the
bogus IP address and use the arrows to move it so that it appears below
your normal network device (either your wired or wireless network).
Click OK to save your changes and exit the window. (Thanks to
Phergus@forums.rptools.net for this information.)

Other operating systems are not likely to have this problem, but
searching Google for "network binding order" or "interface binding
order" should help you find the documentation for your operating system.

.. _are_there_other_network_interface_issues_i_need_to_know_about:

Are there other network interface issues I need to know about?
--------------------------------------------------------------

One user on the RPTools forum has indicated that their modem hardware
created a Network Connection and the Services tab had Static NAT
configured. Clearing that option allowed the Test Connection feature of
MapTool to work. Apparently, they were victim of the "double-NAT"
discussed above.

Another issue that has been reported on the forum is that the Cisco VPN
client needs to be disabled for the duration of the MapTool server
session. This probably has something to do with the VPN software adding
itself to the top of the Network Binding Order, as discussed in the
previous question, but that has not been verified by this author. Other
VPN software applications may require the same fix.

It's possible that the organization that provides your Internet access
is blocking certain types of access. This is common on University
campuses, for example. In this case, you may wish to try Hamachi as it
can work around this issue. Essentially, the Hamachi folks provide a
server on the Internet. All of the machines that need to be connected
connect to the Hamachi server. This server gives you a "private IP
network" that only applies to your collection of machines, and each
machine in your private network is given a different virtual IP address.
Now you can use MapTool with those virtual IP addresses and everything
will work! You'll need to use the Direct tab when clients are connecting
the server because the RPTools Registry will have the router's external
IP address and not the Hamachi address. The reason this works is that
each machine is connecting to the Hamachi server, so all connections are
outbound connections – and outbound connections are rarely blocked
because people wouldn't be able to reach web servers if they were!
Hamachi provides a virtual private network amongst your group of
machines. There are other techniques that can accomplish the same thing.
OpenVPN is one competitor but it's meant for true enterprise-level
networking and is not the simplest thing to configure. And regardless of
which software package you use, you'll need at least one machine that is
visible from the Internet to act as the VPN server – the folks at
Hamachi provide that server for you.

Many users of MapTool also use a voice-over-IP solution as well. The
most popular (based on the forums at RPTools.net) appear to be Ventrilo,
TeamSpeak, and Skype. And lately, the Dolby Axon software has been
getting good reviews, although there are no Mac nor Linux clients yet.
Lately, Mumble and Oovoo have seen comments from satisfied users –
Mumble (open source) can emulate the other programs, and Oovoo provides
video feeds in addition to audio. They each have their pros and cons, so
if you haven't tried any of them you may want to give each one a fair
shake before settling on a particular package. And check the RPTools.net
forum as comparison threads pop up regularly as each one leapfrogs the
others in capabilities. At the time of this writing, Skype seems to have
the highest cpu load and the least lag time, while Ventrilo and
TeamSpeak scale to lots of users very well (although the free Ventrilo
server only allows 8 connections and the TeamSpeak server isn't free).
If you're going to be using Ventrilo and you have Mac or Linux users in
your gaming group, be sure to configure the Ventrilo server to use the
Speex audio codec, since it's the only non-proprietary one that's
supported and hence, the only one available for the Mac and Linux.

.. _how_to_find_network_information:

How to Find Network Information
===============================

There are times when you'll need your network information in order to
configure your router or your computer. The important information is in
the table below. You should locate that information (examples below) and
fill in the third column, as you'll probably need it to configure port
forwarding on your router.

===================== =========================================== ===================
Information needed    Comparison from the telephone analogy       Your specific value
===================== =========================================== ===================
IP Address            Your phone number on the network           
Gateway Address       The phone company you get your service from
Network (subnet) mask similar to an area code                    
===================== =========================================== ===================

**IP Address** – this is your "phone number" on the network. In a home
network, it's typically a private IP Address in the range of 192.168.x.x
or 10.x.x.x or even 172.12.x.x-172.16.x.x.

**Gateway IP Address** – this is the name of the secretary in your
office. In other words, your router's private IP address. :) Your router
also has an IP address used to connect to your ISP, but that one is
called the WAN Address.

**Network Mask** (also called Subnet Mask) – this is the area code of
the phone book that you are listed in. In simple networks, this number
can be wrong and data might still be delivered properly, but if you're
connected to the Internet, it's important that the subnet mask be
correct.

For a home network it is very likely that IPv4 is being used. This is a
relatively short sequence of four numbers with periods between the
numbers. The Network Mask is also expressed using this format. Here is
an example: 192.168.42.87, network mask 255.255.255.0

The best way to determine the IP information is to use MapTool itself.
This is because your computer might have multiple IP addresses and you
won't know which one MapTool is actually using. From the File menu,
choose Connection Information... You'll get both your local address
(your IP address on the LAN) as well as your external address (the
address that Internet clients should use). Note that the local address
is ONLY used by clients directly on your LAN such as those wired into
the same router or those using a wireless connection to that router,
while the external address is ONLY used by clients outside of your LAN.
In some cases they may be the same value, but that doesn't change the
previous sentence. :)

.. figure:: lan4.png
   :alt: Image:lan4.png

   Image:lan4.png

In the example to the left, my LAN IP address is 10.4.15.176 and my
external address is 12.48.201.241. If I had clients on my LAN (such as
friends who were sitting around the table with me), I would have them
use the LAN tab and they wouldn't need an address at all. Or I could
give them the local address and they would use the Direct tab. If there
were others who were logging in remotely, I would fill in the
RPTools.net Alias field and let them use the RPTools tab, unless I
didn't want my game listed in the registry. Then I'd give them the
external address and they would use the Direct tab. (That example is
from a recent hotel visit. Using UPnP, I have been able to host MapTool
servers from both wired and wireless Internet connections while
traveling.)

There is also a tool on the RPTools.net site: visit the `Troubleshooting
page <http://www.rptools.net/?page=troubleshooting>`__ and read the
description. The application is called SysInfo and it gathers statistics
necessary for diagnosing network failures as well as verifying the Java
version of your system. When using it to gather your machine's
configuration, do not remove any information from what you report on the
forum. People get freaked out for some reason over their external IP
address being listed or their gateway address, but none of that is
information that isn't already publicly available. And in fact, must be
publicly available or your Internet connection wouldn't work in the
first place!

On Windows, you can double-click on the network connection icon in the
system tray and then click on the Support tab and the Details... button
to see all of the details. Use this technique to obtain the gateway
address and the network subnet mask. On the Mac, full details are
available in the System Properties under the Network application.

.. _when_all_else_fails_heres_what_you_need_to_post_on_rptools.net_for_others_to_help_you:

When all else fails, here's what you need to post on RPTools.net for others to help you
---------------------------------------------------------------------------------------

First, you'll be asked if you went through the diagnostic steps above.
If you haven't, no one may answer your post. However, if you've taken
the time to go through those steps and you post the results of each
step, you're likely to get an answer very quickly.

Second, you will likely be asked if there are any exception popup
windows. This will be useful information for the community in helping
you resolve your issue. If you get an exception, use copy/paste and
include it in your forum post. If you miss the exception for some
reason, they are also stored in a file called log.txt in a directory
named .maptool – you can use your system's Search function to find the
file (it'll be under whatever your operating system uses as your “home
directory”).

When posting to the forum include the following information about your
system. Most of this can be obtained using the troubleshooting tool
referred to above under the How to Find Network Information heading:

#. Version of Windows, Linux, or Mac OS X;
#. Version of the Java Runtime Environment;
#. contents of the Network Connections window (for Windows), or output
   of ifconfig on Linux and OS X;
#. version of MapTool and whether you're using Java Web Start or a ZIP
   version;
#. IP address reported as the Local Address in MapTool's Connection
   Information... window; and
#. How far you've gotten in the list of FAQ steps as described above.

And if you have any comments or additions for this FAQ, please make them
known! If something would help even one person, then we want to include
it here. Thank you!

Examples
========

This user was able to accomplish steps 1 through 4 and step 5 didn't
apply to them. But step 6 failed. This scenario is based on server
machine S and remote player P. Local machines inside the same home were
able to connect to S, but the remote player cannot.

.. _the_packets_from_p_are_being_blocked_by_the_players_router_as_they_leave_his_machine.:

1 - The packets from P are being blocked by the player's router as they leave his machine.
------------------------------------------------------------------------------------------

Very unlikely. Most home routers will automatically pass anything from
the LAN to the WAN (from the local network to the Internet) without
restriction.

.. _the_packets_from_p_make_it_onto_the_internet_but_never_get_to_your_router.:

2 - The packets from P make it onto the Internet, but never get to your router.
-------------------------------------------------------------------------------

Possible, but also unlikely. This would require that some router between
your player and you is choosing to dump the packets in the bit bucket.
While this is possible, the routers comprising that portion of the
Internet are typically managed by experienced personnel and such an
issue would be detected and corrected very quickly.

.. _the_packets_make_it_to_your_router_and_are_rejected.:

3 - The packets make it to your router and are rejected.
--------------------------------------------------------

This is quite likely because one of the primary purposes of a router is
to blocked unknown or unexpected traffic from getting inside. That's why
routers are capable of protecting your LAN in the first place!

Configuring the router to block most traffic but allow some traffic
through is called port forwarding. You can configure this permanently on
the router (this FAQ references http://www.portforward.com/ for
model-specific instructions) or you can hope your router is new enough
to support UPnP and has it enabled (it probably does) and you can enable
that feature when you start the MapTool server.

.. _the_router_is_allowing_the_packet_through_but_machine_s_is_blocking_it.:

4 - The router is allowing the packet through, but machine S is blocking it.
----------------------------------------------------------------------------

It is not likely that S is blocking the traffic as other machines on the
LAN have connected successfully (based on the background in the first
paragraph). As I said above, some computer firewalls might be able to
block non-local traffic, but these software firewalls are not typically
installed on home machines.

.. _machine_s_is_receiving_the_initial_connection_request_but_its_response_is_blocked_by_the_router_between_s_and_the_internet.:

5 - Machine S is receiving the initial connection request, but its response is blocked by the router between S and the Internet.
--------------------------------------------------------------------------------------------------------------------------------

This is possible, but also unlikely. As mentioned under #1 and #4, the
router's job is to allow outbound traffic and block incoming traffic.
It's unlikely your router is blocking the outbound response.

.. _same_as_2.:

6 - Same as #2.
---------------

Unlikely to be the problem for the same reasons as #2.

.. _when_the_response_gets_to_your_players_router_it_blocks_the_response_from_going_in.:

7 - When the response gets to your player's router, it blocks the response from going in.
-----------------------------------------------------------------------------------------

The response is marked as such: a response. The router will block such a
packet if and only if the packet does not correspond to an outbound
request. In this case, it does correspond to a request made by machine
P. For example, player P wants to open a connection to IP address
1.2.3.4. His router passes the packet onto the Internet. The response
comes back from IP address 4.3.2.1 (instead of 1.2.3.4). The router will
ignore it and not deliver it to player P. The end result is a Connection
Timeout error by player P.

There you have a sample of the troubleshooting process. More will be
added over time.
