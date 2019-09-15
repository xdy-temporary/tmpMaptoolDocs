.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Game Hosting}}

__TOC__

Introduzione
============

Come già visto nella `Introduzione al
Mapping <Introduction_to_Mapping/it>`__, MapTool permette di creare
mappe e "miniature" virtuali (conosciute nel gergo del programma come
`tokens <Introduction_to_Tokens/it>`__) da utilizzare per riprodurre una
sessione di gioco di ruolo proprio come se la si giocasse su un vero
tavolo. Infatti, è per questo che chiamiamo Maptool un "Virtual
tabletop" o "VTT" (tavolo virtuale). In questa guida tratteremo la
ragione principale dell'esistenza di MapTool: Condividere una mappa con
altri giocatori attraverso internet.

**Nota:** MapTool non è utile *solo* per giocare online - molte persone
lo usano per le loro sessioni faccia a faccia, perché con una mappa
virtuale si possono fare cose impossibili con una reale. Inoltre, avete
meno probabilità di roversarci sopra una birra. Tuttavia questa guida
presume che giochiate online.

L'introduzione al mapping vi ha guidato attraverso i passi base per
procurare MapTool, aprirlo e disporre map e token. Ha anche parlato del
salvataggio dei Campaign Files e del movimento/zoom di map e token.
Queste sono le caratteristiche principali del programma senza le quali
niente del resto che è scritto in proposito avrebbe valore!

Poiché l'hosting non è divertente senza persone che si connettono alla
nostra partita, la parte finale della guida illustra come connettersi al
server di MapTool. Avete bisogno di spiegare ai vostri amici come fare,
quindi siate sicuri di leggere questa sezione!

Infine, visto che questa guida parla di *ospitare* (hosting) un gioco
online, "voi" sarete intesi come "la persona che ha in esecuzione il
server".

Architettura
============

Quando viene usato per giocare online, MapTool usa un architettura
*client-server*. In altre parole, una persona (usualmente il GM, ma non
per forza) utilizza MapTool per avviare un *server* e le altre persone
del gruppo ci si connettono come *clients*.

Una volta che si avvia il server e tutti sono collegati, il campaign
file (con tutte le maps, tokens e le altre informazioni) è quindi
condiviso con tutti i giocatori, in modo che chiunque di loro possa
osservare la stessa mappa, gli spostamenti dei token propri e degli
amici, inserire testo nella finestra di chat e divertirsi molto.

.. _una_parola_sugli_accessori_del_networking:

Una Parola sugli accessori del Networking
=========================================

Uno dei cimenti con la quale ci si dovrà confrontare durante la
creazione di una partita a MapTool (come per le altre applicazioni
client-server incluso gli altri programmi di Virtual Tabletop), è
configurare la vostra rete domestica per consentire agli amici di
connettersi al vostro server.

Ci sono diversi modi per configurare la vostra rete per consentire a
Maptool di hostare attraverso internet. UPnP, port forwarding, oppure
una VPN (un programma per il Networking privato su reti pubbliche).
Dipendentemente dal vostro computer, ISP ed hardware (come una
connessione via cavo/DSL e o router) verrà determinata quale di queste
opzioni funzionerà meglio per la vostra situazione - con gli
innumerevoli tipi di reti domestiche e di hardware, non è possibile
darvi un singolo insieme di regole che garantiscano il successo.

UPnP
----

Un alternativa al port forwarding - se disponibile sul vostro router -
si chiama *UPnP* (acronimo di *Universal Plug-and-Play*). Questa
peculiarità, invece di indicare permanentemente "il traffico transita
sulla porta XYZ", comunica al router "per un po' - mentre giochiamo -
dovrò chiederti di aprire la porta XYZ per noi. Sarebbe stràààfico".

In altre parole, questo rende la gestione delle porte e del traffico in
entrata/uscita più semplice e scorrevole. Indubbiamente, l'aspetto
negativo è che non tutto supporta l'UPnP e si dovrà capire se la propria
rete può farlo. Nondimeno, se il vostro hardware di rete lo supporta,
questo è senza dubbio il modo più semplice per conseguire la corretta
esecuzione di un server di Maptool.

.. _port_forwarding:

Port Forwarding
---------------

Per le reti domestiche che utilizzano router o firewall fisici
probabilmente occorrerà configurare il *port forwarding* (apertura delle
porte). Questo è un meccanismo per il quale le informazioni in arrivo
sulla *vostra* rete, attraverso una specifica *porta*, sono spedite nel
posto giusto all\ *'interno* della vostra rete. Questo è importante per
voi che siete l'esecutore del server di MapTool, visto che i tuoi amici
hanno bisogno di inviare le informazioni al posto giusto!

Le istruzioni specifiche per configurare il port forwarding dipendono
dall'hardware, dovrete controllare il manuale per questo. L'idea base è
che voi indichiate due cose al vostro router/switch/firewall:

#. Quale porta userà MapTool (più avanti avrete i dettagli) - questo
   dirà al router "delle informazioni possono arrivare sulla porta XYZ,
   fai attenzione!"
#. Quale computer, all'interno della rete, deve ricevere queste
   informazioni - in sostanza, "e quando delle informazioni arrivano su
   questa porta, spediscile *quì*"

   #. Per coincidenza, configurare il port forwarding comunica al router
      anche dove far passare le informazioni in *uscita*.

Questo è in breve il port forwarding, la ragione principale per cui
avete bisogno di impostarlo è che la maggior parte dei router
(specialmente se sono configurati in maniera corretta e sicura) non
consentono il traffico casuale di informazioni.

.. _precisazioni_e_approfondimenti_sul_networking:

Precisazioni e approfondimenti sul Networking
---------------------------------------------

Ero pronto a scrivere un'elaborata sezione sul Networking finché mi sono
accorto che ce n'è già una eccellente nelle
`FAQ <http://forums.rptools.net/download/file.php?id=116>`__ scritta da
Azhrei sul `Forum di Maptool <http://forums.rptools.net>`__. Se avete
poca dimestichezza su concetti come Port Forwarding, configurazione del
router o funzionamento della rete (in generale), provate a leggere le
FAQ.

Se invece la configurazione e gestione di una rete casalinga
(specialmente se siete capaci di configurare programmi che agiscono da
server o aprire porte per altre applicazioni) vi è familiare, far
funzionare MapTool come un server risulterà normale amministrazione:
essenzialmente dovrete configurare il port forwarding oppure l'UPnP sul
vostro router per permettere al traffico di rete di MapTool di passare.

Se avete bisogno di informazioni specifiche sulla configurazione del
port forwarding per il vostro hardware di rete cercate in
`Portforward.com <http://www.portforward.com>`__ per consultare una
vasta raccolta di guide e programmi appositi al riguardo.

D'altronde, se tutto quello scritto in precedenza non ha alcun
significato per voi: leggete `Networking
FAQ <http://forums.rptools.net/download/file.php?id=116>`__! Tutto vi
sarà rivelato!

Ora proseguiamo il discorso.

.. _avviare_un_server_di_maptool:

Avviare un Server di MapTool
============================

Presupposti
-----------

Da quì in poi le istruzioni considereranno configurata la rete per la
gestione del traffico di MapTool (attraverso il port forwarding o l'UPnP
per esempio). Se non è così, bisognerà che capiate come farlo prima che
sia possibile far partire un server utilizzabile dai vostri amici.

.. _la_finestra_di_dialogo_start_server:

La finestra di dialogo Start Server
-----------------------------------

.. figure:: mt-file-menu-startserv.jpg
   :alt: mt-file-menu-startserv.jpg

   mt-file-menu-startserv.jpg

.. figure:: mt-start-server.jpg
   :alt: mt-start-server.jpg

   mt-start-server.jpg

1. Andare su **File > Start Server**.

2. Ora potrete vedere la finestra **Start Server** . In essa ci sono
molte opzioni.

.. _opzioni_del_server_ed_impostazioni:

Opzioni del Server ed Impostazioni
----------------------------------

Impostazioni
~~~~~~~~~~~~

-  **Username**: Questo è il nome che apparirà in chat e nella finestra
   Connections; potete scriverci quello che preferite.
-  **Role**: questo menù a tendina comunica a MapTool che *tipo* di
   utente siete: siete un GM (e quindi in possesso del Potere Cosmico
   Totale di tutte le funzioni di MapTool) o siete un giocatore, che
   sopravvive ai capricci del GM (o, in altre parole, ha solo accesso
   alle funzioni del player)? Nontate che un gioco può avere anche più
   di un GM!
-  **Port**: un impostazione *veramente* importante, qui è dove dovrete
   indicare a Maptool la porta di trasferimento che avete configurato
   sul router. Se gli date una porta sbagliata Il traffico di MapTool
   non sarà incapace di uscire dalla vostra rete e non avrete nessun
   gioco!
-  **RPTools Alias**: questo campo vi consentirà di impostare un
   "soprannome" al vostro server per apparire nel registro server di
   RPTools. Di base ciò vi servirà a comunicare ai vostri giocatori
   "cercate il Sublime Server e connettetevici" piuttosto che
   "connettetevi al server all'IP 123.45.678.9"
-  **Passwords**: Potete proteggere il vostro server configurando una
   password. Decidere una password è un operazione opzionale; tuttavia,
   se lasciate in bianco chiunque potrà trovare e connettersi al vostro
   server come utente. Ci sono due categorie di password:

   -  **GM**: la password da GM si usa per chiunque abbia l'accesso
      remoto completo alla campagna benché ci siano un piccolo numero di
      funzionalità non possibili in remoto, come il caricamento di una
      campagna. La password da GM si usa solitamente per un Master
      secondario in modo da poter condividere i suoi compiti, ma può
      anche essere usata in altri casi dove il GM non riesce a
      configurare correttamente l'hosting e uno dei giocatori ospita la
      sessione.
   -  **Player**: le persone connesse al server con il ruolo di "Player"
      utilizzeranno questa password per connettersi.

.. _proprietà_visione_e_capacità:

Proprietà, Visione e Capacità
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

-  **Strict Token Ownership**: MapTool fa uso di un concetto chiamato
   "token ownership" per controllare chi può selezionare, muovere o
   guardare nelle `proprietà <Macros:Glossary/it#P>`__ di un token
   specifico. Se abilitate *Strict Token Ownership*, solamente il
   "proprietario" di un determinato token potrà compiere qualsiasi
   azione su di esso - tutti gli altri potranno solo guardarlo.
-  **Players can reveal vision**: MapTool possiede un sistema di visione
   e nebbia-di-guerra (dove si può configurare come i tokens "vedono" la
   mappa). Con questa opzione abilitata, i giocatori possono scoprire
   l'area che è "visibile" ai loro token senza l'intervento del GM (in
   altre parole, un area sconosciuta è coperta dalla nebbia di guerra e
   appare opaca sullo schermo; quando la rivelate il rivestimento opaco
   viene scoperto e la mappa sottostante diventa visibile). Altrimenti
   il GM dovrà liberarla tutta.
-  **Use Individual Views**: Nel sistema di visione menzionato prima, i
   token dei giocatori possono "condividere" la propria visione
   (*ossia*, tutti i giocatori riescono a vedere quello che vede ognuno)
   oppure essere limitati alla propria.
-  **Restricted Player Impersonation**: Questo significa che i giocatori
   possono impersonare solamente i token che gli appartengono (guardare
   di seguito).
-  **Players Receive Campaign Macros**: MapTool permette di scrivere
   `macros <Macros:introduction/it>`__, che sono fondamentalmente
   sequenze di testo, token e tiri di dado usati per automatizzare
   alcuni eventi - in sostanza, piccoli script che fanno "qualcosa". Il
   GM può creare "Campaign Macros" che saranno dispoibili a tutti i
   giocatori se questa opzione è attivata.
-  **Use Tooltip for [] rolls**: Abilitando questa opzione qualsiasi
   lancio di dadi verrà rinchiuso in parentesi quadre che ne mostreranno
   solo il risultato, per vedere i dettagli del tiro basterà
   posizionarci il puntatore del mouse sopra.

.. _testare_la_connessione:

Testare la connessione
----------------------

Prima di avviare il vostro server è una buona idea premere il pulsante
**Test Connection**. Questo manderà un messaggio ad un server di
RPTools.net chiedendogli di provare a connettersi al vostro computer -
in altre parole, il server di test su RPTools.net cercherà di capire se
il vostro computer è visibile su internet!

Quello che vorrete leggere è **Success! I can see your computer!** e se
questo si mostrerà saprete con certezza che il vostro server sarà
visibile.

Se *non* vedrete un messaggio che acclama il successo del test, sarà
necessario che indaghiate sul port forwarding e la configurazione della
vostra rete per sincerarvi di aver impostato le giuste porte e tutto il
resto.\ :sub:`Questa descrizione è deprecata.`

**Nota:** La connessione di test spesso non funziona e ha causato molte
seccature. Quindi è stata rimossa in b76 (o giù di li). La finestra di
avvio del server ora ha un bottone "Networking Help" che vi porta alle
Networking FAQ nel forum. Questo è veramente il posto dove recarsi.
Leggete (si leggete, non sfogliate!) e seguite i passi. Se non vi è
d'aiuto la comunità sarà sicuramente in grado di darvi una mano.

Per un veloce test di connessoine potete usare
canyouseeme.org\ `1 <http://canyouseeme.org/>`__

.. _ottieni_le_informazioni_di_connessione_e_dille_ai_tuoi_amici:

Ottieni le Informazioni di Connessione e Dille ai Tuoi Amici
------------------------------------------------------------

.. figure:: mt-file-menu-cinfo.jpg
   :alt: mt-file-menu-cinfo.jpg

   mt-file-menu-cinfo.jpg

.. figure:: connection-info.jpg
   :alt: connection-info.jpg

   connection-info.jpg

Supponendo che il test di connessione abbia avuto successo e voi
premiate **OK** per avviare il server, sarà ora possibile controllare le
proprie *Connection Information* per verificare le informazioni di
connessione. Dovrete passare queste informazioni agli amici perché
possano connettersi al vostro server.

1. Andate su **File > Connection Information**.

Questo mostrerà ciò che MapTool sa attualmente sul vostro computer. Fin
quando non avrete avviato un server potrete vedere esclusivamente il
vostro IP interno ed esterno (questa è un informazione importante,
specialmente se non avete ancora impostato il port forwarding!).

Quando il server è avviato potrete vedere anche il suo nome (se gliene
avete dato uno) e la porta che userà per il traffico di rete.

2. Provvedete a fornire queste informazioni ai vostri amici: il *Server
Name* (noto anche come RPTools Alias, se lo impostate), l'indirizzo IP
*esterno* e la *porta*. Loro avranno bisogno di questi dati per poterli
inserire nella finestra di dialogo **Connect to Server** quando
tenteranno di accedere al vostro server.

| 

.. _connettersi_ad_un_server_di_maptool:

Connettersi ad un Server di MapTool
===================================

I passi compiuti fino ad ora vi hanno consentito di creare un server di
Maptool disposto al collegamento di altre persone. Indubbiamente, se non
avete nessuno connesso al vostro server le cose finiranno ben presto per
diventare noiose. La procedura mostrata in seguito si concentrerà sulla
connessione dei vostri amici al server che avete appena creato.

Prerequisiti
------------

Le asserzioni qui elencate si presume siano tutte positive, il viaggio
durerà ben poco altrimenti!.

-  Avete degli amici
-  Avete un server di Maptool in esecuzione
-  I Vostri amici sanno:

   -  Il *Nome* del server e/o *l'indirizzo esterno* (preferibilmente
      entrambi)
   -  L'appropriata *password* impostata (per il GM o per i Player)
   -  La *Porta* del server in uso

-  **MOLTO IMPORTANTE: Tutti i partecipanti devono utilizzare la stessa
   versione di MapTool del server!**

.. _aprire_la_finesta_di_dialogo_connect_to_server:

Aprire la finesta di dialogo Connect to Server
----------------------------------------------

.. figure:: mt-connect-to-server.jpg
   :alt: mt-connect-to-server.jpg

   mt-connect-to-server.jpg

Se tutti i presupposti precedentemente menzionati sono soddisfatti, ecco
cosa dovrete dire ai vostri amici:

1. Andate su **File > Connect to Server** per vedere la finestra di
dialogo **Connect to Server**.

2. Inserite un *User name*. Quale usare è a discrezione dei vostri
amici.

3. Inserite la password (che avete impostato all'avvio del server).

4. Scegliete il vostro *Ruolo*. I tuoi amici possono connettersi come GM
oppure come Player. Siati sicuri che loro scelgano il giusto ruolo
rispetto alla password in uso!

| 

.. _scegliere_come_connettersi:

Scegliere Come Connettersi
--------------------------

La finestra di dialogo **Connect to Server** offre tre strade per
connettersi al server in esecuzione.

RPTools.net
~~~~~~~~~~~

.. figure:: mt-connect-registry.jpg
   :alt: mt-connect-registry.jpg

   mt-connect-registry.jpg

Questa scheda (che è quella mostrata per prima) elenca la lista completa
dei server presente sul *Server Registry* di RPTools.net . Durante la
configurazione del server avete avuto l'opportunità di assegnargli un
*alias* che sarà quello che poi apparirà in questa lista. Il *Server
Registry* immagazzina le informazioni di connessione del server così che
i tuoi amici possano semplicemente selezionare il server che cercano e
premere **OK**.

| 

LAN
~~~

.. figure:: mt-connect-lan.jpg
   :alt: mt-connect-lan.jpg

   mt-connect-lan.jpg

Questa scheda mostra tutti i server attualmente in esecuzione nella rete
*locale*, utile quando si ospita un Lan Party di MapTool oppure quando i
vostri amici sono all'interno della stessa rete (come ad esempio una
riunione notturna con i propri portatili a casa di qualcuno).

| 

Direct
~~~~~~

.. figure:: mt-connect-direct.jpg
   :alt: mt-connect-direct.jpg

   mt-connect-direct.jpg

La connessione diretta è proprio questo - i tuoi amici bypassano
l'amichevole scheda RPTools.net e semplicemente inseriscono l'indirizzo
esterno e la porta del server.

| 

.. _verificare_le_connessioni:

Verificare le Connessioni
-------------------------

Quando gli amici si connetteranno al vostro server di MapTool apparirà
nel **Chat Pane** (riquadro della chat), in riferimento alla persona
appena connessa, una notifica come questa:

\ *GiocatoreX has connected.*\ 

Potete anche controllare il **Connections Pane** (riquadro della
connessione) per osservare la lista completa delle persone connesse al
vostro server. Se non trovate il Connections Pane andate su **Window >
Connections** per farlo comparire.

.. _tokens_sulle_tue_map:

Tokens Sulle tue Map
====================

Quando utilizzate MapTool in solitario il programma vi lascia accedere a
qualsiasi elemento della mappa poiché presume che voi siate il GM (e
quindi l'onnipotente dio del piccolo mondo rappresentato nella mappa).
Tuttavia quando si ospita un gioco, MapTool possiede un ruolo differente
(menzionato precedentemente) per ogni persona connessa. Il ruolo del
**GM** mantiene il suo stato d'onnipotenza, può selezionare e manipolare
qualsiasi cosa sulla map; invece il ruolo del **Player** ha una rosa di
opzioni molto più ristretta, può controllare solamente quegli elementi
di cui detiene il *possesso* (ownership).

Per questo fatto, ogniqualvolta si avvia un server, bisogna essere
sicuri di aver dato ad ogni giocatore l'ownership del token che gli
spetta! Dimenticarsi di selezionare l'ownership di un token dopo che i
vostri giocatori si sono connessi è una svista comune!

L'Ownership dei Token è spiegato in maggior dettaglio in `Introduzione
ai Tokens <Introduction_to_Tokens/it>`__, ma per scopo illustrativo,
quando avete avviato un server con gli amici connessi come player,
dovete compiere le seguenti operazioni per ognuno di essi:

#. Doppio clic sul token che dovrebbe entrare in possesso del giocatore
   come il suo Player Character (vedi nota sotto).
#. Definisci il tipo di token come PC.
#. Vai sulla scheda **Ownership**
#. Spuntate la casella affianco al nome del *player*, concedendogli così
   l'ownership del token.
#. Clicca su **OK** per salvare i cambiamenti.

Fatto questo i giocatori saranno in grado di muovere e modificare i
propri token. Potete anche assegnare l'ownership di un token a tutti i
players se tutti i giocatori hanno il bisogno di manipolarlo.

**NOTA**: I players possono avere anche l'ownership dei token NPC se
volete (il processo è identico eccetto per l'assenza del secondo punto);
tuttavia, avrete bisogno che loro possiedano almeno i propri player
token!

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__
`Category:MapTool <Category:MapTool>`__
