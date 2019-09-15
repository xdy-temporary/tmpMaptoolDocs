.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Tokens}}

__TOC__

.. raw:: mediawiki

   {{Beginner}}

.. _introduzione_ai_tokens_di_maptool:

Introduzione ai Tokens di Maptool
=================================

Come menzionato nella guida d'\ `Introduzione al
Mapping <Introduction_to_Mapping/it>`__, il
`token <Macros:Glossary/it#T>`__ è il gergo per indicare un marcatore
visuale posizionato sulla map di MapTool. L'uso più intuitivo per i
tokens è rappresentare i personaggi nel gioco - in altre parole, i
tokens prendono il posto delle miniature sul tavolo virtuale (virtual
tabletop).

Presupposti
-----------

Questa guida presume che voi abbiate letto L'\ `Introduzione al
Mapping <Introduction_to_Mapping/it>`__ e che voi sappiate come:

-  Aggiungere una cartella alla vostra Resource Library ed
   aggiornare/aggiungere le immagini che la compongono di modo che
   compaiano in lista
-  Creare una map in MapTool
-  Depositare tokens sulla map e spostarle
-  Cambiare il Name, GM Name e Label dei tokens
-  Ridimensionare i token (size)
-  Cambiare le immagini dei token
-  Traslare un token attraverso i layer (livelli)

Se non sapete come fare queste cose, per piacere leggete la guida di
Introduzione al Mapping - altrimenti quello che è scritto di seguito
potrebbe risultarvi insensato!

Infine, questa guida è stata scritta principalmente dal punto di vista
del GM -- qualcuno che ha il controllo completo su tutte le impostazioni
dei token e sulle proprietà della campaign. I Giocatori (cioé gli
individui che si uniscono al gioco nel ruolo di "Player") sono limitati
su diversi cambiamenti effettuabili in una determinata campaign.

.. _i_layers_di_maptool:

I Layer's di MapTool
--------------------

Sebbene molti utenti di MapTool si riferiscano ai "token" solamente come
le immagini che rappresentano i personaggi e le creature sulla map, in
realtà, la parola "token" definisce *qualsiasi* oggetto-immagine deposto
sulla map in MapTool. Le modalità di interazione con uno specifico token
dipendono dal Layer della Map dove vengono immessi. Questi layers sono
illustrati qui in basso, perché è importante capire come agiscono sui
tokens.

-  Gli elementi deposti nel layer **Token** sono quelli che vengono
   considerati più comunemente "tokens" - rappresentano i personaggi, i
   mostri, i PNG (personaggi non giocanti) - le persone e creature del
   gioco.
-  Gli elementi deposti nel layer **Object** sono le immagini che
   rappresentano gli arredamenti, i contenitori, le *cose* nel mondo di
   gioco - quello che una persona può manipolare o usare. MapTool
   continua a ritenerli tokens, naturalmente (per esso è tutto un token
   - ha veramente una mentalità restrittiva), ma per amor di chiarezza,
   molti utenti li chiamano *oggetti* per distinguerli dai token che
   rappresentano i *personaggi*
-  Gli elementi deposti nel layer. **Background** sono tipicamente le
   cose che arricchiscono la map - muri, pareti rocciose, sporcizia,
   erba. Potrebbero essere unici, ma solitamente sono "stampati" sulla
   map più e più volte, sia a formare un disegno ben preciso o proprio
   perché state utilizzando diverse copie distinte della stessa immagine
   (ad esempio, utilizzare più muri per completare una stanza). Per
   questa ragione, molti utenti chiamano queste immagini *francobolli*.

.. _the_hidden_layer:

The Hidden Layer
~~~~~~~~~~~~~~~~

Avrete notato che non ho parlato del layer **Hidden** nel paragrafo
precedente. Questo perché il Layer Hidden ha una finalità leggermente
differente.

Mentre i layers Token, Object e Background hanno una relazione
abbastanza intuitiva in termini concezione del mondo -- Io sono una
*persona o creatura*, quell'elemento lì è un *oggetto* e tutto quello
che ci circonda è lo *sfondo* -- il Layer Hidden è quello che *non si
vede*. In MapTool qualsiasi cosa posizionata sul Layer Hidden è visibile
solo dal GM fintanto che questi non decida di spostarla su un altro
layer.

Generalmente su questo layer vorrete metterci personaggi e oggetti - non
ci sono ragioni per inserirci francobolli di sfondo, malgrado io sia
sicuro che voi potete già pensarne un paio.

E' sufficiente dirvi che quando piazzate un token su una map di MapTool
dovete prestare attenzione al layer dove lo mettete!

.. _creare_un_nuovo_token:

Creare un nuovo Token
=====================

Creare un token consiste semplicemente nel trascinare un immagine dalla
`Resource Library <Macros:Glossary/it#R>`__ al Layer Token della map. Ma
come si fa a creare un immagine in primo luogo? ci sono diverse
alternative.

.. _scaricare_un_immagine:

Scaricare un Immagine
---------------------

La comunità di utenti di MapTool ha creato una moltitudine di
immagini-token pronte all'uso. Visitate la `Galleria di
RPTools <http://gallery.rptools.net>`__ per visionare le centinaia di
immagini-token già pubblicate.

.. _crearne_una_attraverso_tokentool:

Crearne una attraverso TokenTool
--------------------------------

Un altra alternativa è creare le vostre immagini utilizzando
`TokenTool <http://www.rptools.net/index.php?page=tokentool>`__, un
programma sviluppato dagli stessi autori di MapTool per creare
immagini-token in modo facile e veloce. Per creare un token usando
TokenTool bisogna:

1. Scaricare TokenTool ed aprirlo facendo doppio clic sul file con
estensione **.jar** (questo è un Java "JAR file", un eseguibile che
avvierà un programma java).

2. Trovare un immagine che vi piace (siate cauti con il copyright!) e
trascinatela sul riquadro a sinistra della finestra di TokenTool (questa
è la sezione con un piccolo anello centrato sullo sfondo nero).

3. Quando compare l'immagine, trascinatela in giro con il mouse
fintantoché la porzione che desiderate per il vostro token sia
all'interno dell'anello. Potrete vedere un anteprima di come diverrà il
token in alto a sinistra della finestra di TokenTool.

-  **Consiglio**: Potete usare la rotellina del mouse o i pulsanti di
   ridimensionamento per regolare la grandezza dell'immagine per come vi
   sembra opportuno.
-  **Consiglio**: Potete cambiare l'aspetto e il colore dei bordi, la
   grandezza finale del token ed alcune altre configurazioni utilizzando
   i menu a tendina nella parte destra della finestra di TokenTool.

4. Quando avrete ottenuto ciò che volete, andate su **File > Save
Token** e salvate il token appena creato in un percorso assegnato alla
vostra Resource Library, oppure dove pianificate questo utilizzo. Notate
che il file verrà salvato nel formato PNG (questa è buona cosa! le
immagini \*.png supportano le trasparenze che sono indispensabili per la
creazione di pedine non necessariamente quadrate!).

5. Ritornate a MapTool e aggiungete o aggiornate la cartella nella
vostra Resource Library, li vedrete apparire il vostro nuovo token!
Trascinatelo sulla map e sarete apposto.

.. _disegnarla_da_te:

Disegnarla da te
----------------

Potete creare un immagine-token autonomamente usando programma di
disegno e salvando il file in formato PNG o JPG in una cartella che è o
sarà parte della vostra Resource Library. Il formato PNG è quello
raccomandato per i tokens di MapTool perché consente le trasparenze e,
sostanzialmente, rende meglio.

Indubbiamente potete anche miscelare l'utilizzo di tutti i metodi
esposti per creare tokens belli e ben formati.

.. _editare_un_token:

Editare un Token
================

Editare un token vuol dire cambiare le sue caratteristiche, siano esse
le sue immagini, i suoi nomi o i suoi settaggi impostati. Le istruzioni
per cambiare nomi, immagini e dimensioni di un token sono coperte nel
capitolo `Introduzione al Mapping <Introduction_to_Mapping/it>`__.

La seguente sezione tratta delle varie opzioni, schede e menù a tendina
nella finestra di dialogo **Edit Token**.

.. _tipi_di_token:

Tipi di Token
-------------

I Tokens sono di due possibili tipi (type) in MapTool: NPC e PC (PNG e
PG). Questi termini saranno familiari ai giocatori di ruolo poiché
stanno per "Player Character" e "Non-Player Character" (Personaggi
Giocanti e Personaggi Non Giocanti), l'uso più comune di
quest'impostazione "type" è di fare distinzione tra i due gruppi durante
una partita vera e propria.

In generale, i tokens appartententi ai vostri giocatori dovrebbero avere
il tipo "PC". I tokens appartenenti a *voi* (GM) dovrebbero avere il
tipo "NPC".

.. figure:: Edit-token.jpg
   :alt: Edit-token.jpg

   Edit-token.jpg

**NOTA**: Il *type* dei token non ha influenza su chi può manipolarli o
vederne le proprietà - al contrario, questo potere è garantito agli
*owner* o *owners* (proprietari) di quel token. Come GM, voi siete
considerati possessori (ownership) di tutti i tokens su tutte le maps
nelle campaign. Guardate
`Ownership <Introduction_to_Tokens/it#Ownership>`__ più sotto per
maggiori dettagli.

Per cambiare il type dei token:

1. Doppio-clic sul token per aprire la finestra di dialogo **Edit
Token**.

2. Nell'angolo in alto a destra utilizzate il menù a tendina per
selezionare PC o NPC.

3. Cliccate su **OK**.

Notes
-----

.. figure:: Notes-tab.jpg
   :alt: Notes-tab.jpg

   Notes-tab.jpg

La scheda Notes presenta due aree dove potete inserire delle note
approposito del token. Questi campi supportano i tag HTML base, così che
possiate formattare la nota.

Il campo del testo in alto è li per le note disponibili e visibili per
chiunque voglia vederle. Il campo in basso (intitolato **GM Notes**) è
per le note che solo il/i GM possono vedere.

Le note sono un po' intricate - Maptool può esporle in un elegante
finestra a scomparsa, ma dovete fare un paio di cose prima.

#. Inserire informazioni nei campi delle note di un token.
#. Mettere questo token in un layer che non sia il "Token Layer"
   cliccandogli sopra con il pulsante destro del mouse e selezionando
   **Change To >**
#. Essere sicuri di trovarsi o spostarsi nel **Token Layer**

Ora noterete che, quando posizionate il cursore sopra il token, il
puntatore diventerà una mano. Se farete doppio-click, al posto della
normale finestra di dialogo **Edit Token**, vedrete una piccola finestra
a scomparsa nell'angolo in basso a sinistra della mappa che visualizzerà
le note.

La lezione da trarne è -- ove le note di un Token sono accessibili in
diversi modi -- uno dei più comuni usi è quello di porre annotazioni e
promemoria su token o oggetti depositati nell'"Object" o "Background"
layer.

Properties
----------

.. figure:: Properties-tab.jpg
   :alt: Properties-tab.jpg

   Properties-tab.jpg

Le **Properties** (proprietà) sono un tema che merita una guida
apposita, in quanto sono "pesantemente" coinvolte nella creazione e uso
delle token macros. Questa guida non entrerà nei minimi dettagli delle
proprietà, piuttosto si incentrerà solo sulle informazioni di base che
le riguardano.

Qualsiasi token deposto sulla map in MapTool acquisisce automaticamente
una serie di **properties**, che fondamentalmente possono essere viste
come statistiche, caratteristiche o tratti (lo sapete, i numeri su una
scheda del personaggio). In effetti, ogni token si porta dietro la
propria scheda del personaggio incorporata. In termini di
programmazione, le proprietà sono reputabili come variabili a cui può
essere assegnato un valore utilizzabile successivamente dalle macros.

-  '''Nota: sebbene le persone facciano riferimento spesso alle
   "proprietà dei token", le proprietà visibili nella finestra di
   dialogo "Edit Token" non sono altro che le proprietà specifiche in
   quella sola ed unica campaign.

Quando si clicca sulla scheda **Macros** nella finestra di dialogo
**Edit Token** vedrete una lista di proprietà che sono attualmente
configurate per la **Campaign** che state usando. Se avete aperto una
nuova campagna (o appena avviato MapTool), potrete vedere il *default
property set* (serie di opzioni predefinite) che appaiono così:

-  Strength
-  Dexterity
-  Constitution
-  Intelligence
-  Wisdom
-  Charisma
-  HP
-  AC
-  Defense
-  Movement
-  Elevation
-  Description

Per il resto di questa guida gli esempi useranno la lista di qui sopra.

L'elenco di proprietà che vedete è racchiuso in una tabella (o foglio di
calcolo), con il nome specifico sulla sinistra e uno spazio bianco sulla
destra. In questo spazio potete inserire il valore che volete assegnare
alla rispettiva proprietà. Potete inserire testo, numeri o in casi più
avanzati direttamente delle istruzioni macro (dichiarazione o contenuto
di una macro) come valore per una particolare proprietà.

Una volta fatto questo e premuto **OK**, il valore immesso verrà
assegnato alle proprietà **di quel token**. Più tardi potrete scrivere
una macro che si riferisca a queste proprietà per fare dei calcoli o
tirare dadi.

Dal momento che le proprietà già di per sé rappresentano uno dei temi di
maggior importanza, consultate la guida `Introduzione alle
proprietà <Introduction_to_Properties/it>`__ per informazioni più
dettagliate.

State
-----

.. figure:: State-tab.jpg
   :alt: State-tab.jpg

   State-tab.jpg

.. figure:: State-example.jpg
   :alt: State-example.jpg

   State-example.jpg

Gli **States** sono marcatori visuali che possono essere applicati ad un
token (tipicamente appaiono come un'immagine sovrimpressa sul token) e
rappresentano una sorta di richiami che potrebbero servire in un gioco.
Per esempio, se cercate un marchio per identificare che un particolare
token NPC è "morto", potete selezionare lo stato "dead" sul token, e
qualsiasi immagine abbiate selezionato per indicare la "morte" apparirà
sopra il token.

Gli stati predefiniti che sono caricati quando avviate MapTool sono:

-  Dead
-  Disabled
-  Hidden
-  Prone
-  Incapacitated
-  Other
-  Other 2
-  Other 3
-  Other 4

| 

.. _health_bar:

Health Bar
~~~~~~~~~~

.. figure:: Bar-example.jpg
   :alt: Bar-example.jpg

   Bar-example.jpg

La scheda State contiene anche le informazioni di regolazione per le
**bars** che il token mostra o potrebbe mostrare. Queste barre vengono
esposte in sovrimpressione sul token (in alto, in basso o ai lati), e
possono essere usati per tracciare cose come la vitalità (o le
munizioni, le magie o qualsiasi altra cosa possa essere persa o spesa).

| 

Macros
------

Dalla versione 1.3.b54 di MapTool, la tab Macros non è più abilitata.
Questa scheda originariamente deteneva le token macros ma con
l'avanzamento delle capacità delle macro questa scheda è diventata
sempre meno utile, finché alla fine non è stata del tutto rimossa. Però,
se volete ancora dare un occhiata, è presente nelle vecchie versioni.

Speech
------

.. figure:: Speech-tab.jpg
   :alt: Speech-tab.jpg

   Speech-tab.jpg

Questa scheda contiene una lista di **speech** (frasi) del token. Potete
usarla per impostare detti, aforismi, gridi di battaglia e qualsiasi
cosa desideriate che il vostro token possa "say" (dire) in chat. Ci sono
due campi per ogni singolo speech item (elemento orativo) :

-  **ID**: Questo campo è il breve identificativo che si assegna ad un
   elemento orativo; l'ID è usato in chat come riferimento al testo
   completo del discorso. L'ID può essere alfanumerico, potete usare
   numeri o lettere o un mix di entrambi. Non può contenere nessuno
   spazio, però!
-  **Speech Text**: Questo è il testo effettivo che verà visualizzato
   nel riquadro di chat.

Per utilizzare uno speech item, dovete conseguire:

#. Selezionate il token che volete abbia qualcosa da dire ("say")
#. Nel riquadro di chat scrivete **/tsay (ID)**, dove "(ID)" è
   sostituito dall'ID effettivo dello speech item. Se quindi volevate
   urlare il vostro grido di battaglia - a cui avete abilmente assegnato
   l'ID "bcry" - selezionereste il vostro token e scrivereste **/tsay
   cry** nel riquadro di chat.

Ownership
---------

.. figure:: Ownership-tab.jpg
   :alt: Ownership-tab.jpg

   Ownership-tab.jpg

Il Token **ownership** (possesso dei token) determina chi fra i
giocatori `connessi al gioco <Introduction_to_Game_Hosting/it>`__ è
abilitato a selezionare, muovere o controllare i dettagli di un
determinato token.

Se voi siete il possessore di un token potete selezionarlo, fare doppio
clic su di esso per aprire la finestra di dialogo "Edit Token" e
personalizzarne le opzioni e anche spostarlo per la map. Se *non* siete
il possessore di un token in particolare, non potete far altro che
rimirarlo sulla map -- non potrete selezionarlo, muoverlo o vederne
proprietà e configurazioni.

Per assegnare il possesso semplicemente spuntate le caselle antecedenti
il nome di qualcuno. I nomi mostrati nel box saranno i nomi di ogni
giocatore (compreso il GM) connesso al gioco (se osservate la scheda
Ownership quando nessuno è connesso vedrete solo il vostro nome). Se
volete dare possesso di un token a tutti i giocatori, semplicemente
spuntate **All Players**.

(Notate che selezionare l'opzione **Strict token ownership** quando
avviate il server è indispensabile per le funzionalità descritte
poc'anzi. Consultate `Avviare un Server di
MapTool <Introduction_to_Game_Hosting/it#Avviare_un_Server_di_MapTool>`__
per i dettagli sulle opzioni del server.)

Config
------

.. figure:: Config-tab.jpg
   :alt: Config-tab.jpg

   Config-tab.jpg

Questa scheda contiene una serie di impostazioni che hanno effetto sul
campo visivo, movimento ed interazione di un token attraverso MapTool.

Shape
~~~~~

I Tokens in MapTool possono avere tre tipi di shapes (conformità):

-  **Top Down**: i token di stampo top-down sono usualmente disegnati a
   mano o renderizzazioni di creature, oggetti e persone vedute
   dall'alto in basso (a volo d'uccello). Impostare lo shape di un token
   su **Top-down** indica a MapTool di abilitare la rotazione del token
   quando selezionate **Change Facing** al clic destro su di essi (in
   questo modo il vostro token potrà guardare in faccia i suoi nemici!).
-  **Circle**: i token dalle fattezze circolari sono come Pog o fiches
   da poker - immagini tonde che rappresentano creature o personaggi.
   Poiché sono raffigurazioni simboliche e non realistiche vedute
   "dall'alto", quando voi selezionate Change Facing invece di ruotare
   l'immagine - che sarebbe brutto da vedere - una piccola freccia
   gialla apparirà ad indicarci dov'è rivolto il token.
-  **Square**: i tokens dalla sagoma squadrata funzionano come quelli a
   forma circolare eccetto perché sono...un momento...quadrati. (N.d.T.
   in realtà semplicemente la punta della freccia gialla che indica la
   direzione della pedina costeggerà una cornice quadrata invece che
   circolare)

Size
~~~~

Un token può avere un dato numero di taglie che scalano la larghezza
della token image.

Le graduazioni disponibili dipendono dalla griglia selezionata durante
il `regolamento di una map <Introduction_to_Mapping/it>`__. Se impostate
la map con una griglia (essa sia esagonale o quadrata) avrete a
disposizione sia *Free Size* come modello di scalatura (che vi consente
un ridimensionamento fluido) che una serie di taglie a tutti gli
effetti, da "Fine" a "Colossal" (se avete mai giocato a D&D
probabilmente li avrete già riconosciuti).

Se invece dalle Map Properties avrete scelto di togliere la griglia una
scala numerica da -11 a +20 sostituira le taglie.

.. _properties_1:

Properties
~~~~~~~~~~

Questo campo vi permette di indicare quale serie di proprietà adotta un
token fra quelle disponibili nella campaign. Il progettista della
campaign può assegnare distintamente le serie di proprietà ai tokens
(per esempio, una apposita per i tokens PG e l'altra per gli NPG).

.. _has_sight:

Has Sight
~~~~~~~~~

Questo campo vi consente di decidere che tipo di `facoltà
visive <Introduction_to_Lights_and_Sights/it>`__ possiede il token.
L'opzione **Sight** consente al GM di simulare l'oscurità, la luce, gli
oggetti celati e i nemici furtivi.

.. _snap_to_grid:

Snap to Grid
~~~~~~~~~~~~

Questa casella di spunta indica semplicemente che il token si aggancia
alla griglia esistente quando viene spostato. Se deseleziona, il token
non si curerà della griglia mentre lo trascinate sulla map.

.. _visible_to_players:

Visible to Players
~~~~~~~~~~~~~~~~~~

Questa casella di spunta fa consente di far scomparire un determinato
token alla vista - se spuntata nessun giocatore connesso al gioco potrà
vedere il token o interagire con esso in nessun modo.

.. _layout_portrait_ed_handout:

Layout, Portrait, ed Handout
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ci sono tre campi che hanno a che fare con l'apparenza estetica di un
token:

-  **Layout**: questo mostra come il token è raffigurato sulla map
-  **Portrait**: questa è un immagine separata che compare nell'angolo
   in basso a sinistra della map al passaggio del mouse sul token
-  **Handout**: consente di scegliere un immagine che apparirà alla
   pressione del tasto destro sul token, scegliendo **Show Handout**

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__
`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__
