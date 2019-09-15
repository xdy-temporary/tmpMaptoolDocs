.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Game Hosting}}

{{#customtitle:Introduction à l'hébergement de partie|Introduction à
l'hébergement de partie}}__TOC__

Introduction
============

Comme vu dans l'\ `Introduction à la création de
carte <Introduction_to_Mapping>`__, MapTool vous permet de créer des
cartes et figurines virtuelles (connues dans le jargon de MapTool comme
des `pions <Introduction_to_Tokens>`__) (tokens)), afin d'être utilisée
dans des parties de jeu de rôle, un peu de la même façon que vous
utiliseriez une carte papier et de vraies figurines sur une table. De
fait, c'est pour cela que nous appelons MapTool une "table de jeu
virtuelle" ou "VTT" ("Virtual Table Top" en anglais). Dans ce guide,
nous passerons en revue un des fondamentaux de MapTool : partager une
carte avec d'autres joueurs, au travers d'Internet.

**NB :** MapTool n'est pas *seulement* utile pour jouer en ligne - de
nombreuses personnes l'utilise lors de session de jeu "en face à face",
parce que l'on peut faire des choses, avec une carte virtuelle,
infaisable avec une carte réelle. De plus, vous avez moins de chance de
renverser du Coca dessus ;). Toutefois, ce guide partira du principe que
vous jouez en ligne.

L'introduction à la cartographie vous a guidé à travers les étapes de
base permettant d'obtenir MapTool, le lancer, y créer une carte et y
placer des pions. Ainsi que sauvegarder une fichier de campagne, comment
se déplacer sur la carte, zoomer, et déplacer les pions. Ce sont les
fonctions essentielles du logiciel, sans lesquelles le reste n'a aucun
intérêt à être lu !

Etant donné qu'héberger une partie n'est pas drôle si personne n'y
participe, la dernière section de ce guide expose comment se connecter à
un serveur MapTool. Vous devrez expliquer à vos amis comment faire cela,
donc assurez-vous de lire aussi cette section !

Et pour finir, ce guide traitant de l'hébergement d'une partie en ligne,
"vous" signifiera toujours "la personne qui a lancé le serveur".

Architecture
============

Lorsqi'il est utilisé pour une partie en ligne, MapTool utilise une
architecture "client-serveur". En d'autres termes, une personne (en
général le MJ, mais pas nécessairement) utilise MapTool pour démarrer un
"serveur" et les autres personnes de la partie se connectent au serveur
en tant que "clients".

Une fous le serveur démarré et que tous y sont connectés, le fichier de
campagne (avec toutes les cartes, pions et autre information) est
ensuite partagée entre tous les joueurs, afin que tous voient la carte,
les mouvements de leur pion et ceux des autres joueurs, les textes
saisis dans le chat ... et passent un bon moment.

.. _un_mot_à_propos_des_bidules_réseau:

Un mot à propos des "bidules" réseau
====================================

Un des challenges dans la création d'une partie avec MapTool (à l'instar
de nombreuses applications client-serveur, dont beaucoup d'autres VTT)
réside dans la configuration de votre réseau local afin de permettre à
vos amis de se connecter à votre serveur MapTool.

Il existe de nombreuses manières de paramétrer votre réseau pour
autoriser MapTool à être "hôte" à travers Internet. UPnP, redirection de
port ou un VPN. Votre ordinateur, FAI et matériel réseau (cable/modem
xDSL, routeur ...) vont déterminer lesquelles de ces options vont
fonctionner pour vous. Etant donné la myriade de possibilités de
combinaisons matérielles et logicielles, il n'est pas possible de donner
un ensemble de règles et conseils qui garantiraient le succès de
l'opération.

UPnP
----

Une alternative au transfert de port - si elle est disponible sur votre
routeur - est appelée *UPnP* (acronyme de *Universal Plug-and-Play*).
Cette fonctionnalité, au lieu d'indiquer de façon permanente "Le trafic
sur le port XYZ va ici !", va dire au routeur "pour un temps donné -
pendant que nous jouons - je vais devoir te demander d'ouvrir le port
XYZ pour nous. Ce serait *supeeeeeeeeeer*."

En d'autres termes, cela rend la gestion des ports et du trafic entrant
et sortant un petit peu plus transparent et simple. Évidemment, le
désavantage est que tout ne gère pas l'UPnP, et vous devrez découvrir
par vous-même si votre réseau peut le faire. Toutefois, si votre
matériel réseau gère l'UPnP, c'est *de loin* le moyen le plus facile de
lancer votre serveur MapTool.

.. _translation_dadresse:

Translation d'adresse
---------------------

Sur les réseaux personnels qui utilisent un routeur ou un pare-feu
physique, vous aurez probablement besoin de configurer la *translation
d'adresse* ("port forwarding"). C'est un mécanisme par lequel les
informations venant *vers* votre réseau, et arrivant sur un *port*
spécifique, sont envoyées au bon endroit *dans* votre réseau local. Ceci
est important pour vous, qui lancerez le serveur MapTool, étant donné
que vos amis ont besoin d'envoyer l'information vers le bon endroit !

Les spécifications pour configurer la translation d'adresse dépendent de
votre matériel, donc vous devrez consulter votre manuel pour cela. Mais
l'idée de base est que vous indiquez deux choses à votre
routeur/switch/pare-feu :

#. Quel port MapTool va utiliser (plus d'information là dessus
   ultérieurement !) - cela revient à dire au routeur "de l'information
   va arriver sur le port XYZ, sois attentif !"
#. Quel ordinateur, au sein du réseau local, doit recevoir cette
   information - basiquement "et quand tu vois de l'information arriver
   sur le port XYZ, envoie la *ici*"
#. Incidemment, paramétrer la translation d'adresse dit aussi au routeur
   où il doit faire passer l'information *sortante* aussi.

La raison principale, pour laquelle vous devez établir cette translation
d'adresse pour héberger un serveur MapTool, est que la plupart des
routeurs ne laisseront pas passer n'importe quelle information
(particulièrement s'ils sont correctement sécurisés et configurés).

.. _information_complémentaires_sur_les_réseaux:

Information complémentaires sur les réseaux
-------------------------------------------

J'étais sur le point d'écrire une section a propos du Networking,
lorsque j'ai réalisé qu'il y en avait une excellente
`FAQ <http://forums.rptools.net/download/file.php?id=116>`__ écrit par
Azhrei sur `le forum Maptool <http://forums.rptools.net>`__. Si vous
n'avez pas l'habitude des concepts comme la re-direction de ports, la
configuration de routeur, ou comment fonctionne un réseau en général,
jetez un coup d'œil à cette FAQ.

Si vous êtes un habitué des configurations et de la gestion du réseau
familial (plus particulièrement si vous êtes capable de configurer des
logiciels pour qu'ils agissent en tant que serveur, ou que vous savez
comment on réalise une redirection de port sur un réseau en fonction des
besoins des autres applications), configurer Maptool ne présentera
aucune difficulté particulière pour vous : vous devrez principalement
configurer la redirection de port ou l'UPnP sur votre routeur pour
autoriser le trafic de MapTool sur votre réseau.

Si vous avez besoin d'information spécifique sur la configuration de
redirection (forwarding) pour votre matériel réseau, vérifiez sur
`Portforward.com <http://www.portforward.com>`__ pour trouver une
collection exhaustive de documents how-to (comment faire) dédiés à des
matériels et des logiciels réseaux spécifiques.

D'un autre coté, si tout ce dont on parle précédemment n'évoque pour
vous que le chinois (que vous ne parlez pas bien sûr), lisez `la FAQ
réseau <http://forums.rptools.net/download/file.php?id=116>`__! Tous vos
vœux seront exaucés.

Maintenant, essayons de voir ce qu'on peut faire avec ça.

.. _démarrer_un_serveur_maptool:

Démarrer un serveur Maptool
===========================

.. _principe_de_base:

Principe de base
----------------

A partir de ce point, les instructions suivantes supposent que vous avez
configuré votre réseau pour accepter le trafic de MapTool (via la
redirection de ports ou l'UPnP, par exemple). Sinon, vous devrez
résoudre ce point avant de pouvoir espérer démarrer un serveur auquel
vos amis pourront se connecter.

.. _la_boite_de_dialogue_démarrer_un_serveur:

La boite de dialogue Démarrer un Serveur
----------------------------------------

.. figure:: mt-file-menu-startserv.jpg
   :alt: mt-file-menu-startserv.jpg

   mt-file-menu-startserv.jpg

.. figure:: mt-start-server.jpg
   :alt: mt-start-server.jpg

   mt-start-server.jpg

1. Allez dans **File > Start Server**.

2. Vous avez maintenant la boite de dialogue **Démarrer un Serveur**
(Start Server). Un tas d'options sont possibles ici.

.. _paramètres_et_options_du_serveur:

Paramètres et options du serveur
--------------------------------

Configuration
~~~~~~~~~~~~~

-  **Username**: C'est le nom qui apparaîtra dansla fenêtre de Chat et
   dans la fenêtre de connexion ; vous pouvez mettre le nom que vous
   voulez.
-  **Role**: Choisissez le type d'utilisateur que vous allez être : êtes
   vous le MJ de la campagne ?(auquel cas vous allez être en possession
   de totalité des pouvoirs cosmiques à travers toutes les fonctions de
   MapTool) Ou êtes vous un PJ, qui va endurer toutes les lubies du MJ
   ?(en d'autres termes, vous aurez seulement accès aux fonctions du
   joueur!) Remarquez qu'une partie peut accueillir plus d'un MJ !
-  **Port**: Un réglage *très* important, puisqu'il indique à MapTool
   quels ports vous avez configuré pour que votre routeur assure la
   re-direction des informations réseaux. Si vous indiquez un port
   erroné, le traffic MapTool sera incapable d'entrer ou de sortir de
   votre réseau, et vous ne pourrez pas jouer!
-  **RPTools Alias**: Ce champ vous permet d'utiliser un "alias" pour
   que votre serveur apparaisse dans le registre des serveurs de
   RPTools. En fait, il vous permet de dire à vos joueurs "cherchez le
   serveur NOM_DU_SERVEUR et connectez vous à lui" au lieu de "connectez
   vous au serveur dont l'adresse IP est 123.45.678.9".
-  **Passwords**: Vous pouvez protéger l'accès à votre serveur en
   configurant un mot de passe. Cela reste une option, et si vous
   laissez ce champ vide, n'importe quel joueur qui trouverait votre
   serveur pourrait s'y connecter en tant que joueur. Il existe deux
   catégories de mots de passe :

   -  **GM**: Le mot de passe du MJ est utilisé pour conférer à
      quelqu'un un accès total sur la campagne en cours. Toutefois, il
      existe un petit nombre d'actions qui ne peuvent être réalisées à
      distance comme le chargement d'une campagne. Le mot de passe du MJ
      est en général utilisé pour un MJ suppléant, ainsi les charges du
      MJ peuvent être partagées, mais il peut aussi être utilisé dans
      des cas où le MJ se retrouve dans l'incapacité d'héberger
      correctement le serveur et où un de ses joueurs doit assumer le
      rôle de serveur.
   -  **Player**: Les gens qui se connectent au serveur pour y jouer une
      partie utilisent le mot de passe des joueurs.

.. _appartenance_vision_et_comportement:

Appartenance, Vision et Comportement
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  **Strict Token Ownership**: MapTool utilise le concept
   d'"appartenance du Pion" (token ownership) pour décider qui peut
   sélectionner, déplacer ou éditer les propriétés d'un Pion
   sélectionné. Si vous validez l'option *Strict Token Ownership*, seul
   le propriétaire du Pion sélectionné pourra interagir avec ce dernier
   - tous les autres devront se contenter de regarder le Pion.
-  **Players can reveal vision**: MaptTool dispose d'un système qui gère
   le "brouillard de guerre" (dans lequel vous pouvez configurer la
   manière dont les Pions "voient" la carte). Avec cette option validée,
   les joueurs peuvent révéler la partie de la carte visible depuis leur
   Pion sans intervention du MJ (En d'autres termes, une zone cachée aux
   PJ sera recouverte par le brouillard de guerre et apparaîtra opaque à
   l'écran; lorsque vous révélez la zone, la couche opaque est retirée
   et la carte en dessous devient visible). Si l'option n'est pas
   validée, c'est au MJ de révéler la carte au fur et à mesure.
-  **Use Individual Views**: Dans le système gérant la vision cité
   précédemment, les Pions des joueurs peuvent également "partager" leur
   vision (chaque joueur peut voir ce que les autres voient) ou ils
   peuvent choisir d'avoir une vision limitée a leurs seuls Pions.
-  **Restricted Player Impersonation**: Signifie que les joueurs peuvent
   uniquement faire s'exprimer des Pions qu'ils possèdent (voir la
   partie concernant
   `l'appartenance <Introduction_to_Tokens/fr#Appartenance>`__ pour des
   informations complémentaires).
-  **Players Receive Campaign Macros**: MapTool vous permet d'écrire des
   `macros <Macros:introduction>`__ (des suites de commandes concernant
   du texte, des Pions, des jets de dés, utilisées pour automatiser
   certaines activités - de petits scripts qui font "quelque chose"). Le
   MJ peut écrire des Macros pour la campagne, elles deviendront
   disponibles pour tous les joueurs si cette option est choisie.
-  **Use Tooltip for [ ] rolls**: Avec cette option validée, lorsque
   vous intégrez un jet de dés entre crochets, seul le résultat est
   affiché, le détail du jet en question apparaissant uniquement sous
   forme d'info-bulle si vous passez la souris sur le résultat.

.. _test_de_la_connexion:

Test de la connexion
--------------------

Avant de lancer votre serveur, il est préférable d'appuyer sur le bouton
**Test Connection**. Cela aura pour effet d'envoyer un message à un
serveur dédié de RPTools.net lui demandant d'essayer de se connecter à
votre ordinateur - en d'autre terme, ce serveur de test va essayer de
voir si votre ordinateur est visible depuis le réseau !

Un message du type **Success! I can see your computer!** indique que le
serveur de test de RPTools.net a réussi à voir votre serveur depuis le
réseau et que ce dernier sera probablement visible lorsque vous le
démarrerez.

Si vous n'avez pas reçu ce message, vous allez devoir passer un peu plus
de temps à analyser la redirection des ports de votre routeur et la
configuration réseau de votre serveur, de manière à être sûr que tout a
été configuré correctement.

.. _récupérez_les_informations_concernant_votre_connexion_pour_les_transmettre_à_vos_amis:

Récupérez les informations concernant votre connexion pour les transmettre à vos amis
-------------------------------------------------------------------------------------

.. figure:: mt-file-menu-cinfo.jpg
   :alt: mt-file-menu-cinfo.jpg

   mt-file-menu-cinfo.jpg

.. figure:: connection-info.jpg
   :alt: connection-info.jpg

   connection-info.jpg

Nous supposerons que vous avez obtenu une réponse positive au test de
connexion précédent et que vous avez cliqué sur **OK** pour démarrer le
serveur. Maintenant vous pouvez afficher vos *informations de connexion*
(Connection Information) pour effectuer une vérification de contrôle de
votre configuration. Les paramètres affichés devront être transmis à vos
joueurs pour qu'ils puissent se connecter au serveur.

1. Allez dans **File > Connection Information**.

Cela affichera ce que MapTool sait à propos de votre ordinateur. A moins
que vous n'ayez déjà démarré le serveur, vous verrez uniquement les
adresses IP internes et externes de votre ordinateur (Informations
utiles, tout spécialement si vous n'avez pas encore paramétré la
redirection de ports !)

Si le serveur est démarré, vous avez également son nom (si vous lui en
avez donné un), et le port utilisé par le trafic réseau de MapTool.

2. Procurez ces informations à vos joueurs :

-  Le *nom du serveur* (Names) ou *RPTools Alias* si vous en avez saisi
   un.
-  L'adresse *IP externe* (External Address).
-  Le *Port* utilisé.

Ces informations leur seront nécessaires dans la fenêtre de dialogue
**Connexion à un serveur** lorsqu'ils essayeront se se connecter à votre
serveur.

| 

.. _se_connecter_à_un_serveur_maptool:

Se connecter à un serveur MapTool
=================================

Les étapes menant à ce point vous ont conduit à configurer un serveur
MapTool de telle façon que d'autres personnes peuvent maintenant s'y
connecter. Les étapes suivantes sont consacrées aux personnes (vos
amis?) qui pourraient vouloir se connecter au serveur que vous venez de
créer. Bien sûr, si vous ne connaissez personne susceptible de vouloir
se connecter à votre serveur, les choses vont devenir lassantes assez
vite.

.. _pré_requis:

Pré requis
----------

La suite de ce guide part du principe que tout ce qui suit est vrai !
L'absence de n'importe quel élément va couper court à tout le reste.

-  Vous avez des amis
-  Vous avez démarré un serveur MapTool
-  Vos amis connaissent ce qui qui suit :

   -  Soit le *nom* du serveur (*Name*) OU l\ *'adresse externe*
      (*External Address*) du serveur (de préférence ... les deux !)
   -  Quel est le *mot de passe* approprié (*password*), soit celui du
      MJ, soit des joueurs
   -  Quel est le *Port* qu'utilise le serveur

-  **Très IMPORTANT: vos amis utilisent la même version de MapTool que
   vous !**

.. _ouvrir_la_fenêtre_de_connexion_au_serveur:

Ouvrir la fenêtre de Connexion au serveur
-----------------------------------------

.. figure:: mt-connect-to-server.jpg
   :alt: mt-connect-to-server.jpg

   mt-connect-to-server.jpg

Si les pré requis mentionnés ci-dessus sont remplis, voilà ce que vous
devez dire à vos amis :

1. Allez dans le menu **Fichier > Se connecter à un Serveur** pour voir
la fenêtre **Connect to Server**.

2. Entrez un *User name* (*Nom d'utilisateur*). Cela peut être n'importe
quoi souhaité par vos amis.

3. Entez le mot de passe (*password*), que vous avez précisé en
démarrant le serveur.

4. Choisissez votre *Rôle* (*Role*). Vos amis peuvent se connecter en
tant que MJ (*GM*), ou en tant que Joueur (*Player*). Assurez-vous
qu'ils aient choisi le bon rôle par rapport au mot de passe saisi.

| 

.. _choisir_comment_vous_allez_vous_connecter:

Choisir comment vous allez vous connecter
-----------------------------------------

La fenêtre **Connect to Server** propose trois méthodes pour se
connecter à un serveur démarré.

RPTools.net
~~~~~~~~~~~

.. figure:: mt-connect-registry.jpg
   :alt: mt-connect-registry.jpg

   mt-connect-registry.jpg

Cet onglet (affiché par défaut) liste tous les serveurs qui se sont
enregistrés (=ont signalé leur présence) auprès du *Server Registry*
(registre des serveurs) du site RPTools.net. Quand vous démarrez votre
serveur, vous aviez l'option de donner un *alias*, nom qui apparait dans
cette liste. Le *Server Registry* enregistre les informations de
connexion du serveur, ainsi vos amis ont juste à sélectionner le serveur
qu'ils veulent et cliquez **OK**.

| 

LAN
~~~

.. figure:: mt-connect-lan.jpg
   :alt: mt-connect-lan.jpg

   mt-connect-lan.jpg

Cet onglet montrera tous les serveurs qui sont démarrés sur le *réseau
local*. Utile lorsque vous organisez une *LAN Party* MapTool, ou quand
tous vos amis sont dans le même réseau local (par exemple, tout le monde
a amené sont portable chez vous pour une soirée de jeu).

| 

Direct
~~~~~~

.. figure:: mt-connect-direct.jpg
   :alt: mt-connect-direct.jpg

   mt-connect-direct.jpg

Lors d'une connexion directe, vos amis évitent l'onglet "facile"
RPTools.net et tapent simplement l'adresse externe et le n° de port de
votre serveur (ils savent, ou vous leur avez dit, que votre adresse IP
sur Internet est, par exemple, "213.34.45.2" et le port est "51234").

| 

.. _vérifier_létat_de_la_connexion:

Vérifier l'état de la connexion
-------------------------------

Lorsqu'un de vos amis se connecte à votre serveur MapTool, vous verrez
une notification apparaître dans la fenêtre de Chat indiquant qu'une
personne s'est connectée à votre serveur et qui ressemblera a :

\ *JQRandom has connected.*\ 

Vous pouvez aussi vérifier la fenêtre Connexions pour vérifier la liste
des personnes connectées à votre serveur. Si vous ne voyez pas la
fenêtre de connexions, allez dans le menu Fenêtres>Connexions pour en
récupérer la vue.

.. raw:: mediawiki

   {{Languages|Introduction to Game Hosting}}

`Category:MapTool <Category:MapTool>`__
