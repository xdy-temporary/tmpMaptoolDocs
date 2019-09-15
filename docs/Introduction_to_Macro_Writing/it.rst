.. contents::
   :depth: 3
..

.. raw:: mediawiki

   {{Languages|Introduction to Macro Writing}}

.. raw:: mediawiki

   {{Translation}}

.. _lunità_più_importante_che_dovresti_conoscere_sintassi_del_codice:

L'unità PIÙ importante che dovresti conoscere!! (sintassi del codice)
=====================================================================

Se non hai mai creato codice prima probabilmente la parte seguente NON
avrà senso (ma *continuate* a leggere). Tutt'ora ciò che riguarda le
macro in Maptool è l'unità più importante da conoscere. Quindi quando
raggiungete la fine di questo (lungo) articolo, tornate indietro e
leggete di nuovo, quando avrete creato il vostro primo codice, tornate
indietro e leggete ancora. Comincerà ad avere senso e converrete "ahhhhh
ok, finalmente ha senso" e vorrete capire perché questa sia la parte più
importante. Felice lettura.

Se avete già familiarità con il codice allora ciò che segue avrà molto
più senso e capirete perché sia così importante.

E come per tutto il codice, c'è una sintassi che vi serve sopportare.
*TUTTE le linee di codice/script di Maptool consistono in 0 o più
opzioni e 1 funzione* (con una accezione: ).

Una **opzione** è qualcosa che influenza quello che viene mostrato al
termine nella chat. Per esempio

-  l'opzione nasconderà i risultati,
-  l'opzione mostrerà solo i risultati e
-  l'opzione ; mostrerà solamente uno o l'altro (dipendentemente se vero
   o falso).
-  se non date nessuna opzione l'intera esecuzione della funzione
   mostrata nella chat

nota che ci sono molte `Roll
Opzioni <http://lmwcs.com/rptools/wiki/Category:Roll_Option>`__

Una **funzione** è qualcosa che RESTITUISCE un valore risultato, quindi
avete un valore iniziale e usate una funzione SU di esso e quello che
viene restituito è il risultato di questa funzione su quel valore.
Esempio:

-  la funzione restituirà un valore positivo (rimuove il - da ogni
   valore), quindi restituirà 3. Il valore iniziale è -3 e quello
   risultante è 3.
-  la funzione (in realtà esiste sia *l'opzione* che la *funzione* )
   restituirà il primo parametro se il valore è true (=1) e il secondo
   parametro se il valore è falso (=0). Quindi restituirà "White". Nota
   che perché questa è una funzione, entrambe le istruzioni vera e falsa
   verranno eseguite (ma solo il risultato di una delle due sarà
   restituito).

Ecco una panoramica di tutte le
`Funzioni <http://lmwcs.com/rptools/wiki/Category:Macro_Function>`__

**Da questo momento voi avete SEMPRE:**

`` [opzione, opzione, ...: risultato = funzione(valore, parametri)] ``

Nota così che tutto il codice/script inizia con "[" e finisce con "]" e
se c'è un'opzione si separa da una funzione con un ":", se avete più
opzioni le separate con un ",". Non ci sono MAI più di UNO di questi tre
elementi in una istruzione di uno script. E quindi tutto quello FUORI le
"[" "]" NON è codice ma solo testo (html) semplice (indipendentemente
dal contenuto). Questo 'testo (html)' apparirà SEMPRE nella chat com'è e
non sarà influenzato dal codice in nessun modo.

Come ho detto, questo per ora non avrà senso, ma annotatelo su un foglio
di carta e attaccatelo alla vostra scrivania rileggendolo spesso,
comincerà ad avere senso.

Se siete arrivati qui attraverso il link 'leggete questo' ora potete
smettere di leggere perché la parte soprastante è quella considerata *da
leggere*. Se siete principianti, per piacere leggete questo.

.. _cosa_è_una_macro:

Cosa è una Macro?
=================

Come menzionato nella pagina dei Token Macro, una macro è semplicemente
un modo per automatizzare un compito in MapTool. Essenzialmente, una
macro è uno script che viene letto da un *parser*, che la interpreta e
si assicura che la parte giusta sia processata nel modo corretto (ad
esempio assicurandosi che un comando per sommare due numeri sia
processato come un comando macro e non semplicemente come testo da
inviare alla finestra di chat).

In MapToll le macro hanno avuto una timida introduzione ma ora il
linguaggio è diventato un vero insieme completo di comandi e funzioni
che possono compiere quasi ogni cosa operazione tu possa immaginare!

.. _cosa_dovresti_già_conoscere:

Cosa dovresti già conoscere
===========================

Le Macro sono l'argomento dove noi scaviamo nelle più potenti - e più
complicate - caratteristiche e capacità di MapTool. Mentre questa guida
cerca di essere semplice da seguire per ogni nuovo utente, ci sono
alcune cosa che io presumerò voi abbiate già letto e conosciate come
fare:

#. Presumo che abbiate letto `Introduction to
   Mapping <Introduction_to_Mapping>`__ così che siate familiari con
   l'interfaccia di MapTool e su come creare una mappa, salvare una
   campagna e inserire token sulla mappa.
#. Presumo abbiate letto anche `Introduction to
   Tokens <Introduction_to_Tokens>`__, così che abbiate una idea di base
   su come manipolare i token, guardare le loro proprietà e via dicendo.
#. E infine, siccome le macro sono usualmente intinamente connesse con
   le *proprietà* dei token, presumo che abbiate letto e seguito i passi
   in `Introduction to Properties <Introduction_to_Properties>`__ e
   creato un nuovo file di campagna basato su `Sample RPG
   ruleset <Sample_Ruleset>`__ scritto per aiutare i nuovi utenti ad
   imparare MapTool. Se non avete letto questa guida, per piacere fatelo
   - farà si che alcuni degli esempi seguenti avranno *più* senso!

.. _una_importante_configurazione_delle_preferenze:

Una importante configurazione delle preferenze
==============================================

Una delle cose importanti presunte in questa guida sulle macro è che voi
abbiate una preferenza abilitata chiamata *Use Tooltips for Inline
Rolls.* Lasciatemi spiegare:

In modo predefinito, quando l'output di una macro viene mostrato, ciò
che viene visualizzato è un analisi completa di come il risultato
inviato alla chat sia stato ottenuto. Questo non è l'ideale per piccole
macro - somiglierà a questo:

   **Attack Roll**: « roll + bonus = 18 + 9 = 27 » vs. AC

Un po' brutto anche se non terribile. D'altra parte, con qualcosa di più
complesso esso somiglierà a questo:

   **Toxic Cloud** vs: « attack = 1d20+attackBonus = attack = (4 + 7) =
   11 » « damage = 1d6 + 2 = damage = (5 + 2) = 7 » Target 0: Attack 11;
   « damage = 7 » damage. « attack = 1d20+attackBonus = attack = (14 +
   7) = 21 » « damage = 1d6 + 2 = damage = (3 + 2) = 5 » Target 1:
   Attack 21; « damage = 5 » damage. « attack = 1d20+attackBonus =
   attack = (6 + 7) = 13 » « damage = 1d6 + 2 = damage = (1 + 2) = 3 »
   Target 2: Attack 13; « damage = 3 » damage. « attack =
   1d20+attackBonus = attack = (17 + 7) = 24 » « damage = 1d6 + 2 =
   damage = (2 + 2) = 4 » Target 3: Attack 24; « damage = 4 » damage.

Che è davvero poco leggibile.

Per evitare di vedere questi dettagli del processo di ottenimento
dell'output di una macro avrete bisogno si impostare MapTool per
mostrare questi calcoli in tooltip (suggerimenti visibili quando
posizionate il puntatore sopra il risultato in chat) piuttosto che nella
finestra di chat. Per farlo:

#. Andate nel menu **Modifica**.
#. Selezionate **Preferenze**
#. Nel lato destro della scheda **Interactions**, nell'area "Chat",
   assicuratevi di aver **spuntato** *Use ToolTips for Inline Rolls*.
#. Cliccate sul bottone **OK**.

Seguendo questi passi i dettagli del processo saranno mostrati su un
tooltip disponibile quando puntate il valore stampato in chat invece che
mostrati direttamente nella finestra di chat.

.. _convenzioni_per_questa_guida:

Convenzioni per questa guida
============================

Cercherò di fare del mio meglio per mantenere il mio linguaggio e
terminologia consistenti. In questa guida:

-  **Macro** si riferirà a collezioni di comandi raggruppate insieme per
   automatizzare un compito
-  **Macro command** si riferirà ad un particolare comando o funzione
   *individuale* che potete vedere *dentro* una macro
-  **Macro language** significherà l'intera collezioni di comandi,
   funzioni e operazioni che potete usare ogni volta che scrivete una
   macro. Potete vedere una lunga lista di funzioni in `List of Macro
   Functions <:Category:Macro_Function>`__.

Inoltre, benché sia possibile per una macro attivarne un altra (chiamato
"chiamare" un'altra macro), per questa guida, le uniche macro di cui
parleremo saranno attivate cliccando un bottone sull'appropriato Macro
Panel e avranno effetto solamente sul token su cui sono state avviate
*sopra*.

.. _perché_dovrei_usarle:

Perché dovrei usarle?
=====================

Non c'è niente che richieda specificatamente l'utilizzo di macro quando
usate MapToll. Ricordate, lo scopo principale di MapTool è di
condividere una mappa con gli amici e giocare (leggete `Introduction to
Mapping <Introduction_to_Mapping>`__ e `Introduction to Game
Hosting <Introduction_to_Game_Hosting>`__ per sapere come condividere
con il vostro gruppo di gioco), e MapTool vi offre tutto quello che
serve per farlo: mappe, token, e sistema di chat che permette di parlare
impersonando o meno il personaggio, lancio di dadi e di prendere il
ruolo di qualsiasi carattere voi stiate giocando.

Tuttavia, ci sono molte altre cose che si possono fare con MapTool, se
siete interessati a imparare un po di più sulle capacità delle macro.
Per esempio, se volete cliccare su un bottone per lanciare
automaticamente 1d20 e aggiungere automaticamente un modificatore ad
esso, è possibile creare una macro apposita. Se volete cambiare i vostri
punti ferita dopo essere stati colpiti, potete scrivere una macro per
farlo. E questo tutorial vi mostrerà come.

.. _dove_risiedono_queste_cosiddette_macro:

Dove risiedono queste cosiddette "Macro"?
=========================================

Le macro sono associate a varie parti dell'interfaccia MapTool e gli
oggetti che contengono. Ci sono tre posti in cui una macro può
"risiedere":

.. _token_macros:

Token Macros
------------

Il primo e più comune posto di residenza di una macro è in un
`token <Introduction_to_Tokens>`__. Le macro dei token sono associati al
token su cui sono state create e lo accompagneranno finché gliele
lascerete.

Le macro dei token sono accessibili direttamente solo dalle persone
proprietarie del token, se il token non vi appartiene non potrete
cliccare (e neanche vedere!) il bottone di una macro.

.. _macro_della_campagna:

Macro della Campagna
--------------------

Le macro della campagna sono macro che non sono collegate un token
specifico ma a tutta la campagna. Queste macro funzionano molto
similmente a quelle dei token, eccetto per:

#. Non dovete selezionare un token per vedere le macro
#. Chiunque può accedere e avviarle

Le macro delle campagne sono molto utili per i GM e per i giocatori per
gestire le funzioni comuni, infatti se voi settate una operazione comune
come una macro di campagna avrete bisogno di farne una sola copia
(invece di doverne fare una per ogni token che ne necessita).

.. _global_macros:

Global Macros
-------------

Le macro globali non sono collegati a un token o una campagna, sono
invece collegati alla vostra copia di MapTool. Queste macro *non* sono
visibili a tutti quelli che si connettono al tuo gioco.

Questo è un buon posto dove inserire macro per operazioni che voi *non*
volete che le altre persone vedano, come informazioni che volete vengano
mostrate ai giocatori solo quando *voi* lo decidete; od operazioni sui
vostri PNG che non volete che i vostri PG possano fare.

.. _il_pannello_delle_macro:

Il pannello delle macro
=======================

|Macro-panels.jpg| |Tabbed-panels.jpg|

Con tutto quanto detto sulle macro e le locazioni voi probabilmente vi
starete chiedendo dove sono questi bottoni Voi troverete i bottoni delle
macro in uno dei 4 **pannelli delle macro** che appaiono in MapTool. Se
non vedete nessuno dei pannelli andate in nel **Finestra** e
assicuratevi che queste quattro finestre siano contrassegnate:

-  Selezionato
-  Impersonato
-  Campagna
-  Globali

Dovreste vedere queste finestre apparire in MapTool se non sono già li.
Se guardate lo screenshoot a destra dovreste vedere che il pannello
Global è popolato da diversi bottoni. Ognuno di questi bottoni eseguirà
una macro; il bottone apparirà quando voi creerete una nuova macro.

**Per piacere notate**, tuttavia, che il pannello Global contiene macro
che sono specifiche del *tuo* computer e della *tua* installazione di
MapTool. I bottoni che vedete nello screenshoot del Pannello Global sono
le *mie* macro globali; le vostre... beh, dovrete scriverne alcune!

.. _pannelli_selezionato_e_impersonifica:

Pannelli Selezionato e Impersonifica
------------------------------------

Ci sono due pannelli che hanno a che fare con le macro dei token:
Selezionato e impersonifica.

Il pannello **Selezionato** mostrerà i bottoni per tutte le macro che
sono attualmente localizzate sul token che avete selezionato (potete
selezionare il token cliccando su di esso con il mouse). Ognuno di
questi bottoni avvierà un particolare gruppo di comandi macro.

Il pannello **Impersonifica** mostra i bottoni per le macro del token
che state *impersonificando*. Impersonare un token è un modo per
"assumere la persone del token", quando voi chattate il testo apparirà
come se fosse il token a parlare, e così via. È possibile impersonare un
token e selezionarne un altro, quindi fate attenzione al pannello che
state guardando!

.. _pannello_campagna:

Pannello Campagna
-----------------

Questo pannello mostra tutte le macro impostate per la campagna
corrente. Ricordate, queste sono visibili a tutti.

.. _pannello_globale:

Pannello Globale
----------------

Questo pannello contiene le macro globali che avete impostato.
Ricordate, queste potete *vederle solo voi*.

.. _prima_di_proseguire_le_basi:

Prima di proseguire: le basi
============================

Prima di procedere, ci sono alcuni elementi *essenziali* nella sintassi
delle macro che voi dovreste capire, o cose imprevedibili accadranno. Le
macro sono state create come modo per scriptare una breve sezione di
testo o dei lanci di dado utili inviati alla finestra di chat. Quindi,
se voi volete mostrare un grido di battaglia ma non volete riscriverlo
ogni volta, potreste scrivere una "macro" per inviare questo grido di
battaglia alla finestra di chat. Similmente, se volete lanciare 2d6 per
fare un attacco, potreste voler scrivere una macro per generare questo
output invece che riscrivere ogni volta .

Da qui a crescere, i comandi macro diventano sempre più complessi fino a
diventare simili ad un linguaggio di programmazione; ma sono
semplicemente del testo passato ad un *parser* chhe gestirà tutti i
comandi nella macro e genererà i risultati.

Quindi una delle cose importanti da ricordare è questa:

**IMPORTANTE: Le macro sono sequenze di testo contenente sia testo che
volete mostrare in chat CHE comandi speciali che fanno cose come
lanciare dadi**.

.. _il_token_corrente:

Il token corrente
-----------------

Prima di iniziare a scrivere macro, per piacere consultate i concetti
nella pagina `Current Token <Current_Token>`__. Quando scrivete macro,
usualmente (ammenoché la macro non sia veramente minimale) state
manipolando `Token Properties <Token_Property>`__. Per poter manipolare
*correttamente* le proprietà con le vostre macro è cruciale capire il
concetto di `Current Token <Current_Token>`__.

**IMPORTANTE: Una macro si riferisce** **sempre** '''al token corrente
ammenoché non abbiate specificatamente istruito la funzione/operazione
di questa macro per indirizzarsi ad un altro token diverso da quello
corrente. '''

.. _quadre_e_graffe:

Quadre e Graffe
---------------

Ora, poiché abbiamo testo semplice, abbiamo bisogno di un metodo per
distinguere le parti che sono solo testo da inviare in chat e le parti
che sono "comandi di programmazione". MapTool gestisce questo
raccogliendo i comandi in parentesi quadre o graffe .

**IMPORTANTE: Qualsiasi cosa trovata dentro parentesi quadre o graffe
non viene gestita come testo ma come comando e parsata per ottenere
qualcosa. Similmente, se** **non** **è fra parentesi quadre o graffe,
viene inviato alla finestra di chat come testo.**

Quindi qualcosa come:

.. code:: mtmacro

   [1d20]

oppure

.. code:: mtmacro

   {1d20}

Non dice a MapTool di inviare il testo [1d20] o {1d20} alla chat; invece
dice "genera un numero random fra 1 e 20 e invia *questo* alla finestra
di chat." Le quadre e le graffe (anche se le graffe sono più consigliate
per via di complicazioni che causano alle funzioni di looping e
branching) indicano a MapTool che le informazioni *in* esse sono comandi
macro o variabili e non semplicemente testo. Quindi, come vedrete in
seguito, potete mischiare testo e comandi macro:

.. code:: mtmacro

   I roll [1d20+4] for initiative.

Nella macro sostituiremo [1d20+4] con il risultato dell'espressione del
dado, e quindi stamperemo l'intera frase nella chat, che assomiglierà a:

.. code:: mtmacro

   I roll 16 for initiative.

.. _opzioni_di_lancio:

Opzioni di Lancio
-----------------

Le opzioni di lancio sono un altra caratteristica speciale del
linguaggio delle macro. Il loro nome ha vecchie origini, dal momento che
la maggior parte di macro erano lanci di dado (come l'appena menzionato
[1d20+4]) c'era bisogno di avere modi diversi per mostrarli (o non
mostrarli affatto). Dal momento che queste opzioni erano usate per
cambiare come i lanci apparivano, allora sono sto stati chiamati opzioni
di lancio, e così sono rimaste. In realtà questo è ancora vero anche se
le opzioni non gestiscono solamente come vengono mostrate le cose.

Le opzioni di lancio sono una cosa critica da capire nella scrittura
delle macro. Ci sono un paio di regole. La prima, il formato genera di
ogni comando di macro in MapTool è quesot:

.. code:: mtmacro

   [(comma-list-of-options): operation(s)]

Ora per spiegare: una opzione di lancio ha le seguenti regole:

#. Va sempre all'inizio di una istruzione macro (per i nostri scopi, una
   istruzione è una qualsiasi linea di macro fra parentesi quadre).
#. È sempre seguita dai due punti.
#. Può essere combinata con altre opzioni di lancio; in questo caso
   dovete separare ogni opzione con una virgola e alla fine della
   comma-separated list, dovete inserire i due punti.
#. deve apparire una sola volta in una data istruzione macro perché
   venga applicata all'operazione che contiene. Questo potrebbe
   diventare complesso usando iniziate a usare la roll option CODE, dal
   momento che potrete nidificare intere istruzioni assestanti, ma
   questo verrà spiegato nella sezione di branching e looping.

Un semplice esempio di una opzione di lancio è:

.. code:: mtmacro

   [r:1d20+4]

Questa usa l'opzione "regular output" per mostrare il risultato di
1d20+4 come testo semplice (senza evidenziamenti o tooltips). Un esempio
complesso potrebbe essere questo:

.. code:: mtmacro

   [h,if(d20roll == 20): output = "Critical Hit"; output = "Not a Critical Hit"]

Questo combina le opzioni di lancio [h: ] (che significa, "nascondi
dalla finestra di chat") e [if(): ] che effettua una operazione
se-allora. Nota però che le opzioni di lancio appaiano solo all'inizio
di una istruzione di macro dove si applicano.

Un esempio *veramente* complesso potrebbe coinvolgere l'uso della
opzione di lancio [CODE: ] (ne saprete di più in [Introduction to Macro
Branching]) per permettere di nidificare intere istruzioni macro dentro
blocchi da eseguire come se fossero singole istruzioni. Per esempio:

.. code:: mtmacro

   [h,if(d20roll == 20),CODE:
   {
       [damageAmount = 16]
       [damageType = "acid"]
       [TargetHP = TargetHP - damageAmount]
   };
   {
       [damageAmount = 1d10+6]
       [damageType = "acid"]
       [TargetHP = TargetHP - damageAmount]
   }]

Questa è una istruzione complessa, ma le opzioni di lancio per il
comando complessivo (le parentesi quadre più esterne) sono all'inizio,
separate da virgole e seguite da un due punti. L'istruzione interna è
*nidificata*.

.. _virgolette_e_apostrofi:

Virgolette e Apostrofi
----------------------

In molte circostanze le macro conterranno apostrofi che funzioneranno
correttamente, essi sono semplicemente testo e quindi verranno inviati
alla finestra di chat senza problemi. Tuttavia, in alcune situazioni
singoli apostrofi spaiati faranno pensare a MapTool che voi abbiate
creato na *stringa non terminata*. Quando questo accade il testo della
macro (tutti i comandi ecc. ecc.) saranno solitamente ricopiati nella
chat ottenendo come risultato un grosso blocco di brutto output.

Per evitare questo ricordate questa regola: se avete testo che volete
appaia in chat contenuto fra parentesi graffe, un singolo apostrofo o
virgoletta causerà. Quindi modificate l'esempio seguente:

.. code:: mtmacro

   [h,if(d20roll == 20),CODE:
   {
       [damageAmount = 16]
       [damageType = "acid"]
       [TargetHP = TargetHP - damageAmount]
       The target's HP is now [r:TargetHP].
   };
   {
       [damageAmount = 1d10+6]
       [damageType = "acid"]
       [TargetHP = TargetHP - damageAmount]
   }]

Il singolo apostrofo nella riga causerà errore. Ci sono due strade per
evitare questo:

#. Non usare apostrofi. Questo potrebbe essere un po' un disagio.
#. Sostituite l'apostrofo con il codice HTML per l'apostrofo: ****

Commenti
--------

**NON CI SONO MECCANISMI DI COMMENTO NEL CODICE DELLE MACRO. TUTTI I
COMANDI CORRETTAMENTE SCRITTI IN UNA MACRO** **SARANNO ESEGUITI.**

Il linguaggio di macro spedirà tutto il contenuto della macro al parser
integrato che cerca testo da stampare in chat e commandi da eseguire. È
possibile nascondere l'output dalla finestra di chat un paio di modi
fashion ma non è possibile evitare l'esecuzione di comandi macro
correttamente scritti. In altre parole, **non potete commentare il
codice.**

Ci sono due modi di nascondere l'output: l' opzione di lancio e il
formato di commento dell'HTML. Avete già visto l'opzione di lancio
nascosto ma se non siete familiari con l'HTML, i commenti hanno questo
aspetto:

.. code:: html4strict

   <!--This is an HTML comment-->

In una pagina HTML tutto quello che sta fra <!-- e --> viene
completamente ignorato. In contrasto nel linguaggio macro di MapTool,
tutto quello che è fra i tag di commento è *nascosto* dalla chat ma se
inserite comandi macro al loro interno esse *verranno* eseguite. In
altre parole, se in una macro avete queste righe:

.. code:: html4strict

   <!--In this part of the macro I roll some dice-->

Essere verranno nascoste dalla chat e agiranno come commenti. Tuttavia
se nella riga è scritto:

.. code:: html4strict

   <!--In this part of the macro I roll some dice using the format [r:1d20+9]-->

il parser nasconderà tutto dalla chat ma *eseguirà* la macro, che lo
vogliate oppure no.

La lezione da imparare qui è: **Non potete commentare il vostro codice
macro.**

.. _scrivere_macro:

Scrivere Macro
--------------

.. figure:: Camp-panel-nomacros.png
   :alt: Camp-panel-nomacros.png

   Camp-panel-nomacros.png

.. figure:: Camp-panel-rcaddnew.png
   :alt: Camp-panel-rcaddnew.png

   Camp-panel-rcaddnew.png

La creazione di macro è una procedura di tre passi (sebbene essi possano
contenere moltitudini!):

1. Clic destro sul pannello dove volete che la macro appaia (uno dei due
pannelli dei token, un pannello della campagna o quello globale) e
selezionate **Aggiungi Nuova Macro**. Un bottone grigio con l'etichetta
**(new)** apparira.

2. Tasto destro sul bottone e seleziona **Modifica**.

3. Inserisci il tuo codice di macro, dagli un nome e clicca su **OK**.
Finalmente! Avete creato una macro!

Ma aspetta...cosa significa "macro code?"

Come avevo detto, questi tre passi possono contenere un *grande*
ammontare di dettagli, passi, consigli, trucchi, vittorie, fallimenti,
frustrazioni e a volte, grida e digrignazioni di denti. Quindi, facciamo
un passo indietro e guardiamo alcune semplici macro in stile
passo-passo. Se volete vedere come possono sembrare macro avanzate, ci
sono tanti tutorial e how-to su questo wiki da leggere. Per ora,
tuttavia, scriveremo alcune semplici ma utili macro.

.. _lancio_diniziativa:

Lancio d'iniziativa
-------------------

.. figure:: Camp-panel-newbutton.png
   :alt: Camp-panel-newbutton.png

   Camp-panel-newbutton.png

.. figure:: Camp-panel-rceditbutton.png
   :alt: Camp-panel-rceditbutton.png

   Camp-panel-rceditbutton.png

.. figure:: Macro-editor-examplestring.png
   :alt: Macro-editor-examplestring.png

   Macro-editor-examplestring.png

.. figure:: Camp-panel-exbutton.png
   :alt: Camp-panel-exbutton.png

   Camp-panel-exbutton.png

La macro più semplice non è altro che testo, che viene mostrato nella
finestra di chat. In effetti una macro contenente testo (praticamente
tutte le macro) inviano semplicemente una stringa di comandi alla
finestra di chat dove vengono leggi e interpretati. Molti linguaggi di
programmazione iniziano con il classico programma "Ciao Mondo!", ma
*non* questa guida. Invece faremo qualcosa di più GDR: creiamo il temuto
messaggoi "Lanciate per l'iniziativa!"

1. Selezionate il pannello Campagna.

2. Clic destro su di esso e selezionate **Aggiungi Nuova Macro**.

3. Clic destro sul nuovo bottone new e clic su **Modifica**.

4. Nel campo **Etichetta** inserite "Lanciate per l'iniziativa!"

5. Lasciate il **Gruppo** e **Sort Prefix** in bianco.

6. Nel campo **Comandi** scrivete

   ``Roll for Initiative!``

7. Cliccate **OK**.

8. Quando avete finito, dovreste vedere che il bottone è cambiato, ora
si chiama **Lanciate per l'iniziativa!** e quando lo cliccate, ecco che
il testo "Lanciate per l'iniziativa!" appare nella finestra di chat.

Questa è la base della scrittura delle macro: voi inserite del testo
nella macro e questo testo viene letto dal parser e inviato alla
finestra di chat quando voi premete il bottone.

.. _qualcosa_di_più_interessante:

Qualcosa di più interessante
----------------------------

"Lanciate per l'iniziativa" benché sia spaventoso quando pronunciato dal
DM non è una macro molto *interessante* come macro. Probabilmente
penserete "perché non posso scriverlo semplicemente in chat?" Ed infatti
la risposta è "probabilmente lo vorreste". E quindi facciamo qualcosa di
più interessante e più in linea con il motivo principale per cui usiamo
MapTool (dopo tutto non siamo qui per scrivere programmi ma per
giocare): aggiungeremo alcuni *comandi macro* alla macro in aggiunta del
testo semplice. I comandi macro sono speciali istruzioni che, quando
letti dal parser, gli dicono di fare qualcosa in più della semplice
stampa di testo nella finestra di chat, come lanciare alcuni dadi o
calcolare dei valori.

I comandi macro devono essere *sempre* racchiusi in parentesi quadre
(es. [*macro command*]) o graffe (es. {*macro command*}). Racchiuderle
in questo modo è quello che suggerisce al parser che un comando è in
arrivo, altrimenti esso tratterebbe il comando come un qualsiasi altro
testo e lo stamperebbe in chat.

.. _lanciare_dei_dadi:

Lanciare dei dadi
~~~~~~~~~~~~~~~~~

.. figure:: Macro-editor-rolldice.png
   :alt: Macro-editor-rolldice.png

   Macro-editor-rolldice.png

Questa è una semplice macro che automatizza alcuni lanci e ci aggiunge
un modificatore prima di mostrare il tutto nella finestra di chat.

1. Create una nuova macro (createla dove volete, su un toke, nella
campagna, in global) e aprite la finestra di modifica (ricordate, lo
potete fare con il tasto destro sul bottone **(new)**).

2. Nel campo **Etichetta**, chiamate la macro con qualcosa simile a
"Lancio d'Attacco" o "Lancio Dado"

3. Nel area **Comandi** inserite:

   ``My attack roll is [1d20+7]!``

4. Cliccate **OK**. Dovreste vedere un bottone chiamato come avete
scelto nel precedente passo 2. Quando cliccate su di esso dovreste
vedere qualcosa di simile a questo apparire in chat:

   Chris: My attack roll is 8!

Quello che è successo è che MapTool legge nel contenuto della macro e
quando arriva alla sezione **[1d20+7]** sa di dover:

#. Tirare un dado a 20 facce (o, in realtà, scegliere un numero casuale
   fra 1 e 20) e
#. Aggiungere 7 al risultato, e
#. Mostrare il risultato nella finestra di chat inserendolo nel testo
   nel posto giusto

Potete vedere che il numero 8 ha uno sfondo grigio. Se puntate sul
numero un "tooltip" apparirà mostrando come questo numero sia stato
ottenuto. In questo caso ho ottenuto 1 dal lancio 1d20 (fiasco! un colpo
maldestro!) Se non vedete questo tooltip guardate nelle vostre
impostazioni di `MapTool Preferences#Chat <MapTool_Preferences#Chat>`__
in **Use ToolTips for Inline Rolls**.

Inoltre, probabilmente voi non vedrete il nome "Chris" ammenoché non vi
chiamiate così. Questa parte dell'output di chat indica semplicemente
chi sta *dicendo* quel particolare pezzo di testo; se è un token
apparirà la sua immagine e nome invece del noioso "Chris".

.. _più_che_solo_numeri:

Più che solo numeri
~~~~~~~~~~~~~~~~~~~

I comandi macro possono funzionare con numeri e test, potete manipolare
*stringhe* (questo sono, collezioni di caratteri alfanumerici) usando il
linguaggio macro di MapTool. Per un istante diciamo che volete lanciare
il vostro attacco ma volete inserire il nome del vostro obiettivo così
che venga mostrato in chat.

.. figure:: Macro-editor-basiccommands.png
   :alt: Macro-editor-basiccommands.png

   Macro-editor-basiccommands.png

.. figure:: Prompt-undeclared-variable.png
   :alt: Prompt-undeclared-variable.png

   Prompt-undeclared-variable.png

Quello che dovete fare è modificare la vostra macro di attacco in questo
modo:

   ``My attack roll against [target] is [1d20+7]!``

Quando avvierete questa macro una finestra apparirà improvvisamente
chiedendovi un "Value For target". Cosa è successo?

Bene, quando MapTool guarda queste macro, vede un comando macro che
recita semplicemente **[target]**. MapTool assume che qualsiasi parola
*dentro* un comando macro che *non* sia racchiuso da apostrofi o
virgolette sia il nome di una *variabile* (in altre parole un valore che
può cambiare).

MapTool nota anche che in nessun posto della macro a *cosa* la variabile
*target* equivale. I linguaggi di programmazione chiamano questa sorta
di situazione *variabile non dichiarata* (in altre parole voi non avete
mai dichiarato il suo valore). Siccome MapTool non ha nessun modo per
sapere cosa sia *target* allora ve lo chiede! Se scrivete un nome, un
numero o qualsiasi altra cosa in questa finestra, MaoTool prenderà
questa informazione, l'assegnerà in una variabile *target* e finirà la
macro.

Andate avanti e scrivete "Orchi Cattivi" (senza le virgolette) nella
finestra e premete **OK**. Dovreste vedere qualcosa di simile a questo
nella finestra di chat:

<blockquote style="border:1px solid gray;" width:50%;>Chris: My attack
roll against Nasty Orcses is 23!

.. raw:: html

   </blockquote>

Un altra volta, il parser legge nel testo del comandi macro che hai
inserito nella macro e nei posti dove è indicato un comando macro
indicati (dalle quadre), MapTool sostituisce le informazioni
appropriate.

.. _usare_variabili_in_una_macro:

Usare Variabili in una Macro
============================

Noi abbiamo visto in un paio di esempi come usare una variabile (come
nel precedente ) in una macro ma non abbiamo approfondito ancora il
processo. Tuttavia, le variabili e il loro uso sono veramente il cuore
della scrittura di macro, quindi da parte mia sarebbe una negligenza
saltarlo.

.. _cosa_è_una_variabile:

Cosa è una Variabile?
---------------------

Se avete dimestichezza con la programmazione lo sapete già ma se vi
state appena inserendo in questi argomenti la semplice definizione di
*variabile* in termini del linguaggio macro è:

   **Una variabile è un valore che può cambiare (o variare) in base ad
   una proprietà del token, ad un calcolo o a un altro comando macro**

Visto che il valore di una variabile potrebbe cambiare, noi dobbiamo
dargli un nome (cioè *dichiarare* una variabile, dichiarate che "questa
variabile esiste!") per poterci riferire a lei. Allora, ogniqualvolta
che ci servirà usare un qualsiasi valore che la variabile ha *in quel
momento*, dobbiamo semplicemente inserire il suo nome nel comando macro
e MapToll lo sostituirà con l'appropriato valore attuale.

Pensate in questo modo: se il valore di un lancio di dado può essere
qualsiasi cosa fra 1 e 20, per esempio, non potete semplicemente
inserire 19 dove avete bisogno di usare quel lancio, potrebbe essre 19 o
2 o 7 o altro. Invece voi volete "qualsiasi sia il lancio di dado,
inserisci quel numero qui".

   **Nota**: questo non significa che MapToll sostituirà il vlalore
   *corretto* con i *vostri* bisogni: questo significa che sostituirà il
   valore corrispondente a quella variabile in quel dato momento. Quindi
   se il vostro programma contiene uno sbagli in essa, il valore finale
   sarà sbagliato - ma MapToll non capisce "sbagliato" ma solo "questo è
   ciò che è stato detto adesso".

.. _assegnamento_delle_variabili:

Assegnamento delle variabili
----------------------------

Quando volete dare un valore a una variabile state facendo un
"assegnamento" di un valore ad una variabile. L' "operatore di
assegnamento" in MapToll è il segno di uguaglianza ( = ). Questo suona
stravagante ma significa che voi state un segno di uguale per dire a
MapToll che una particolare variabile ha un particolare valore. Un
esempio di un un assegnamento di variabile è

   .. code:: mtmacro

      [h:myHP = 30]

Come potete vedere quello che fa questa riga è prima *dichiarare* una
variabile chiamata e in seguito *assegnargli* il valore . Questa è
l'assegnazione di variabili alla radice, ;;alcune variabili''
equivalgono ad *alcuni valori*. La **h**: con i due punti dice a
maptools di "nascondere" l'output. Non è necessaria ma se non volete che
tutti i numeri delle vostre variabili siano inviati alla finestra di
chat dovreste inserire un **h**: all'inizio del vostro assegnamento.

Ricorderete dall'esempio dove veniva richiesto il nome per target che
potete usare una variabile senza assegnarli nessun valore. Se lo fate
state dichiarando che la variabile esiste ma senza nessun valore
assegnato, quindi MapToll vi chiederà (o lo chiederà a chiunque avii lo
script) un valore. La lezione imparata è che una variabile ha bisogno di
avere un valore assegnato perché la macro possa concludersi, ma non
dovete sempre inserirlo prima del tempo, alle volte potreste voler
ottenere l' *input* dall'utente.

L'assegnamento di variabili è l'unico modo per impostare o cambiare il
valore di una variabile; le variabili non sono modificabili sul posto.
Se state usando una funzione per cambiare il valore di una variabile la
funzione ritornerà il contenuto della variabile modificata che dovrà
essere assegnata alla variabile esistente o ad un altra nuova.

.. _quando_fate_un_assegnamento:

Quando fate un assegnamento
---------------------------

MapTool processa ogni comando macro in una macro in ordine, partendo
dall'alto. Quindi, se volete che MapTool mostri una finestra che chiede
input all'utente, dovete assegnare un valore a una variabile *prima* di
usarlo! Per esempio, nel comando di macro:

.. raw:: mediawiki

   {{code|The hit does [damage] [damageType] damage, leaving you with [remainingHP] hit points!}}

A meno che non vogliate che MapTool richieda all'utente le variabili , e
, dovrete assicurarvi di dargli dei valori *prima* di arrivare a quella
riga. Probababilmente con qualcosa di questo tipo:

   .. code:: mtmacro

      [h:damage = 1d6+4]
      [h:damageType = "fire"]
      [h:remainingHP = 30 - damage]
      The hit does [damage] [damageType] damage, leaving you with [remainingHP] hit points!

Come potete vedere abbiamo fatto tre assegnazioni *prima* che le
variabili siano usate nella linea riguardante il colpo. Abbiamo
assegnato il valore di un lancio di dado 1d6+4 alla variabile , alla
variabile e il valore dell'operazione alla variabile .

Se guardate attentamente, vedrete che abbiamo usato una variabile per
l'assegnamento di un valore a un altra variabile: il valore della
variabile è usato quando assegniamo un valore a , così le variabili
possono essere utilizzate per impostare e manipolare altre variabili.

.. _regole_per_le_variabili:

Regole per le Variabili
-----------------------

Ci sono due regole da ricordare quando create una variabile:

#. Niente spazi: nomi di variabile non possono contenere spazi, non
   potete usare la variabile - deve essere .
#. Variabili speciali: ci sono alcune "variabili speciali" che MapTool
   si riserva, quest osignifica che non potete usarle per altri scopi
   che quelli per cui MapTool se le è riservate. Solitamente potete
   riconoscere una variabile speciale perché ha un punto nel suo nome,
   come o . Le introdurremo in seguito ma per ora sappiate che non
   potete creare una variabile con lo stesso nome di quelle presenti
   nella pagina `Special Variables <:Category:Special_Variable>`__.

.. _miglioriamo_i_nostri_giochi:

Miglioriamo i nostri giochi
===========================

Gli esempi fin ora mostrano un uso veramente base delle macro: stampare
testo sulla finestra di chat quando cliccate sul bottone; fare un
semplice lancio di dadi dentro una macro; ottenere un semplice input
dall'utente per poter completare una macro.

ora, facciamo un passo avanti: giochiamo con alcune opzioni di
formattazione, cambiamo proprietà del token e diamo uno sguardo di base
ai loop (ripetere la stessa più volte) e al branching (fare diverse cose
sulla base di diverse condizioni o situazioni).

.. _opzioni_di_formattazione:

Opzioni di Formattazione
------------------------

L'output delle macro (come ogni output della chat) può essere formattato
usando tag HTML base, come anche alcune opzioni integrate in MapTool.
Vediamo prima brevemente l'HTML, e poi un paio di `Display Roll
Options <:Category:Display_Roll_Option>`__.

.. _tiri_estesi:

Tiri Estesi
~~~~~~~~~~~

In MapTool 1.3.b54 il modo predefinito di mostrare il risultato di un
lancio di dadi o un calcolo è quello di stampare il totale o valore
finale. Se quindi lanciate 1d20+7 quello che apparirà in chat sarà
giusto il risultato finale, con il tooltip (quando puntate il mouse
sopra il numero) che mostra l'analisi matematica.

Se volete potete istruire MapTool per stampare anche tutto il calcolo
matematico di un lancio, utilizzando le opzioni di formattazione dei
lanci, nello specifico l' **Expanded Roll**.

Pensate a una opzione di formattazione come uno interruttore che dice a
MapTool come trattare il risultato di un lancio. Per ottenere la forma
espansa editate la macro del vostro attacco in questo modo:

   ``My attack roll against [target] is [e:1d20+7]!``

Quindi, quando la lanciate, otterrete una cosa simile nella chat:

   My attack roll against Nasty Orcses is « 1d20+7 = 1 + 7 = 8 »

Ora potete vedere l'analisi completa del vostro lancio.

.. _tiri_solo_risultato:

Tiri solo risultato
~~~~~~~~~~~~~~~~~~~

Ma se *non* volete che nessuno sia in gradi di vedere il calcolo? Fin
ora entrambe le opzioni consentivano ancora a chiunque di vedere il
lancio effettivo. Per farlo usate l'opzione **Result Roll**. Editate la
vostra macro per assomigliare a questo:

   ``My attack roll against [target] is [r:1d20+7]!``

E il vostro output assomiglierà a questo:

   My attack roll against Nasty Orcses is 11!

Notate che non c'è nessuno sfondo grigio dietro il numero 11 e che non
ottenete un tooltip se lo puntate. L'opzione Result Roll rimuove la
formattazione extra restituendo solo testo semplice. Se volete
sbarazzarvi dell'evidenziazione dietro le parole "Nasty Orcses" potete
semplicemente cambiare la macro in:

   ``My attack roll against [r:target] is [r:1d20+7]!``

E il nome del target verrà mostrato senza nessuna speciale
sottolineatura.

.. _tiri_nascosti:

Tiri Nascosti
~~~~~~~~~~~~~

Alle volte non volete vedere nessun output dalla macro, forse volete
mostrare solo del testo ed effettuare i calcoli nelle quinte senza
rivelare niente. In questi casi vorrete sostituire "r:" o "e:" dei
vecchi esempi con "h:" come nel precedente esempio.

   | ``[h:myHP = 30]``
   | ``[h:Bloodied = myHP / 2]``
   | ``My bloodied value is [Bloodied].``

L'esempio sovrastante è una illustrazione semplice di come **hidden
roll** sia utile. In questa macro stiamo facendo queste tre cose:

#. Impostando il valore della variabile *myHP* a 30 ma dicendo a MapTool
   di nascondere questo calcolo
#. Impostando il valore della variabile *Bloodied* alla metà di *myHP*
   ma dicendo a MapTool di nascondere anche questo calcolo
#. Mostrando del testo ed inserendo il valore di *Bloodied* alla fine
   dell'output.

Se avviate questa macro l'output avrà queste sembianze:

   My bloodied value is 15

Tuttavia se *non* usate l'opzione **hidden roll**, l'output avrà queste
sembianze:

   30 15 My bloodied value is 15

I numeri extra provengono dai due calcoli *precedenti* la linea di
testo. Non avete bisogno di vederli, quindi, convenientemente, potete
nasconderli!

.. _formattazione_html:

Formattazione HTML
~~~~~~~~~~~~~~~~~~

Le macro di MapTool supportano la formattazione usando tag HTML di base.
Diciamo che volete mettere il nome del vostro targht su una linea, il
lancio dell'attacco su un altra e nella terza aggiungere un lancio per
il danno. Potete modificare la vostra macro di attacco in questo modo:

   | ``I make an attack roll!<br>``
   | ``<b>Target</b>: [r:target]<br>``
   | ``<b>Attack</b>: [1d20+7]<br>``
   | ``<b>Damage</b>: [1d8+5]``

Quando avvierete questa macro il risultato nella chat sarà questo:

   | I make an attack roll!
   | **Target**: Nasty Orcses
   | **Attack**: 15
   | **Damage**: 7

Questo è semplicemente la formattazione, potete mettere l'output in una
tabella, cambiare il font e il colore di sfondo, cambiare la
dimensione... molte opzioni sono disponibili!

**NOTA**: se siete pratici con l'HTML, tenete presente che MapTool
supporta l'HTML3.2, alcune cose come il tag <br> *non* vanno chiuse, è
<br>, non <br/>. In aggiunta MapTool supporta un sottoinsieme del CSS 1
nello stile in linea, e in certi casi anche i fogli di stile. Altre
informazioni sui tag CSS supportati possono essere trovati ad `Supported
CSS Styles <Supported_CSS_Styles>`__.

.. _usare_proprietà_del_token:

Usare proprietà del token
-------------------------

Fin ora abbiamo manipolato alcune variabili che sono state inserite in
anticipo o che MapTool vi chiedeva quando avviavate la macro. Abbiamo
una macro di attacco formattata che elenca un target, un attacco e i
danni. Tuttavia abbiamo ancora i valori delle macro *hardcoded* o
abbiamo l'utente che li inserisce da solo ogni volta che serve. Visto
che i personaggi dei GDR non sono tutti uguali, dobbiamo pensare ad un
modo per automatizzare alcuni numeri, così noi possiamo:

#. Fare una macro che molte persone o personaggi possono usare
#. Minimizzare il quantitativo di scrittura richiesta!

Come discusso in `Introduction to Tokens <Introduction_to_Tokens>`__,
ogni token trasporta con se una *scheda* personale sottoforma di
*proprietà*. Queste proprietà possono essere *riferite* da una macro,
quindi potete per esempio scrivere una macro che ''Lancia 1d20 e
aggiunge la destrezza del mio personaggio al lancio". Sono sicuro che vi
accorgete di come questo sia utile.

.. _impostare_alcune_proprietà_desempio:

Impostare alcune proprietà d'esempio
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Naturalmente per far si che le proprietà funzionino, dobbiamo averle
settate. È buona cosa che voi leggiate `Introduction to
Properties <Introduction_to_Properties>`__ e creiate un file di campagna
per il MapTool RPG `Sample Ruleset <Sample_Ruleset>`__!

Il primo passo è aprire il file **MTRPG.cmpgn** (o qualsiasi altro nome
con cui l'abbiate chiamato) e trascinare un token sulla mappa (se non ne
avete già uno). Se non avete idea di cosa questo significhi, controllate
`Introduction to Mapping <Introduction_to_Mapping>`__ per imaprare cose
in proposito della creazione di mappe e inserimento dei token sopra di
esse. Ora seguite questi passi:

1. Doppio cliccate sul token per aprire la finestra **Edit Token**.

2. Andate nella scheda chiamata **Properties**.

3. Dovreste vedere una lista simile ad un foglio di calcolo di tutte le
proprietà nel tochen che potete editare direttamente (i token hanno
altre proprietà che si possono editare solamente con le macro ma per ora
non ci preoccupiano di queste!). Dovreste vedere (se state usando il
file MTRPG.cmpgn che abbiamo impostato in `Introduction to
Properties <Introduction_to_Properties>`__):

   | ``*Strength:1``
   | `` *Dexterity:1``
   | `` *Intelligence:1``
   | `` *Endurance:1``
   | `` *HitPoints(HP):{Endurance * 6}``
   | `` *Armor(AR)``
   | `` *Movement(MV):{Dexterity}``
   | 

4. Cliccate nella cella seguente alla Strength. Un cursore apparirà
mostrandovi che potete scrivere in questa cella. Inserite un numero in
questa cella come valore di Strength dela token. Io userò il 6.

5. Ripetere lo step 4 per la Dexterity, Intelligence, e Endurance,
scegliendo il numero che preferite (io userò rispettivamente 3, 2 e 6).
Ricordate che *HitPoints* e *Movement* vengono calcolati
automaticamente!

6. Cliccate **OK**. Avete aggiornato manualmente le proprietà del token.
Se cliccate due volte sul token e guardate queste proprietà ancora,
vedrete che i numeri inseriti sono stati memorizzati.

Dovreste anche vedere che ora, quando puntate il mouse sopra il token,
una piccola finestrella apparirà nell'angolo in basso a destra della
mappa mostrando i valori per le proprietà che avete inserito. Questa
finestrella è chiamata **Statsheet** ed è un modo veloce per vedere le
proprietà del token, è fondamentalmente un veloce riferimento alla
"scheda".

.. _far_riferimento_ad_una_proprietà_del_token_in_una_macro:

Far riferimento ad una proprietà del token in una macro
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Ora che avete configurato alcune proprietà, usiamole in una macro. Per
la nostra prima macro lanceremo 1d20 e invece di aggingere 7 ci
aggiungeremo la **Strength** del token.

1. Aprite la vostra macro di attacco.

2. Nella parte in basso a destra assicuratevi che sia sputanto **Applica
al token selezionato** (in alternativa la macro non saprà quale Strength
del token utilizzare!)

3. Editate la vostra macro per assomigliare a questo:

   | ``I make an attack roll!<br>``
   | ``<b>Target</b>: [r:target]<br>``
   | ``<b>Attack</b>: [1d20+Strength]<br>``
   | ``<b>Damage</b>: [1d8+5]``

Notate che ho sostituito il 7 con la parola "Strength" Visto che
"Strength" non è fra virgolette o apici singoli, MapTool saprà che voi
intendente sia una variabile e quindi controlla nel *token corrente*
(che è il token selezionato) per una proprietà chiamata *Strength*. Se
non la trova (o se la proprietà non è stata impostata), vi chiederà d
iinserirla (proprio come lo richiede per il valore *target*). Se lo
*trova*, MapToll userà il valore di *Strength* nella macro eseguita.

4. Selezionate il vostro token e avviate la macro cliccando il bottone.
L'output assomiglerà a questo:

   | I make an attack roll!
   | Target: Nasty Orcses
   | Attack: 27
   | Damage: 6

La cosa importante da notare è che se voi posizionate il mouse sopra il
risultato del lancio, il tooltip ora mostrerà qualcosa come *« 1d20 +
Strength = 17 + 10 »* indicando che il valore inserito nel lancio di
dadi è la proprietà *Strength*.

.. _cambiare_una_proprietà_con_una_macro:

Cambiare una Proprietà con una Macro
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Le proprietà di un token possono essere cambiate usando una macro.
Supponiamo di voler ridurre gli hit pint dopo che un nemico ha colpito
il personaggio. Potete editare manualmente il token per cambiare il
valore della proprietà *HP* oppure potete creare una macro che sottragga
l'ammontare di danni dal suo valore di *HP*. Ecco come:

1. Create una nuova macro nel pannello **Campagna**.

2. Nel campo **Etichetta** inserite "Danno".

3. Nel campo **Comandi** inserite:

   ``Aarrgh! I'm hit! I have [HitPoints = HitPoints - damage] hit points left.``

4. Spuntate la casella **Applica al token selezionato** (nell'angolo in
basso a sinistra).

5. Cliccate **OK**. Quando voi avviate la macro vi verrà mostrato il
valore da inserire nella variabile "damage". Io ho inserito il numero 7.
L'output mostrerà qualcosa di simile:

   Aarrgh! I'm hit! I have 23 hit points left

E se doppiocliccate su token, vedrete che la proprietà *HP* è ora a 23.
Cosa ha fatto la macro:

#. Richiesto l'inserimeto di *damage* all'utente (in questo esempio io
   ho inserito 7)
#. Recuperato il valore di *HitPoints* dal token (in questo esempio il
   valore è 30 perché è uguale ad Endurance \* 6)
#. Sottratto il valore di *damage* dal valore di *HitPoints* (30-7
   risulta 23)
#. Impostato il valore di *HitPoints* (originariamente 30) al nuovo
   totale calcolato (23)
#. Stampato il testo e il nuovo valore di *HitPoints* nella chat

.. _concatenazione_stringhe:

Concatenazione stringhe
-----------------------

Un'abilità essenziale da possedere quando si scrive macro è quella di
assemblare *stringhe*, che sono collezioni di caratteri alfanumerici che
possono essere manipolate o mandate inviate alla chat. Frequentemente
vorrete costruire una stinga da questi testi che è sempre la stessa
(testo "hardcoded") e testo che cambia (testo che è il valore di una
variabile, in altre parole). la costruzione di una stringa è spesso
chiamata "concatenazione" ma vuol dire semplicemente "costruire una
stringa lunga da pezzi più corti".

Ci sono due modi per fare questo in una macro, fuori o dentro il comando
di macro.

.. _fuori_dal_comando:

Fuori dal comando
~~~~~~~~~~~~~~~~~

Il modo base funziona così:

#. Parsare tutta la macro e seprarare i comandi macro dal testo semplice
#. Il parser dirotta questi comandi macro nel luogo predisposto al loro
   processamento (quindi i numeri sono addizionati, i dadi lanciati ...)
#. I comandi processati vengono rispediti *indietro* al parser che
   sostituisce i *risultati*' di questi comandi nei posti dove ognuno di
   essi deve andare.
#. L'intera pasticcio, testo semplice e risultato dei comandi (ora
   collocati al posto del comandi originali) vengono spediti alla
   finestra di chat.

Quindi quando volete mostrare il risultato di un comando insieme a del
testo (per esempio, volete stampare la parola "Attacco:" e quindi fargli
seguire il risultato di un lancio 1d20) in una macro, il modo più
semplice è quello di inserire semplicemente un comando nella posizione
giusta nel vostro testo, in questo modo:

   .. code:: mtmacro

      Attack: [1d20]

Il parser leggerà il tutto, spedirà il comando per farlo processare e
quindi otterrà il risultato, lo rimpiazzerà al posto del comando e lo
invierà alla chat. Il risultato sarà qualcosa come "Attacco: 17".

Questo è il modo più diretto per inviare testo alla chat, semplicemente
inserire le variabili che volete mostrare nel giusto posto nel testo e
queste verranno mostrate nella finestra di chat.

.. _dentro_un_comando_macro:

Dentro un comando macro
~~~~~~~~~~~~~~~~~~~~~~~

Alle volte però vi servirà usare stringhe *all'interno* delle parentesi
quadre. In questo caso unire tutto assieme sarà un po' diverso. Prima di
tutto, all'interno delle parentesi quadre, avete bisogno di usare
virgolette o apostrofi per attorniare quello che vi occorre essere
trattato come una stringa. Diversamente MapTool penserà che voi vogliate
che ogni parola sia una variabile! Per esempio:

**Correct String**

   .. code:: mtmacro

      [string = "This is a string"]

**Incorrect String**

   .. code:: mtmacro

      [string = This is a string]

Ricordate, fuori dalle quadre non servono apici. Dentro? APICI.

Quindi cosa ci serve per costruire una stringa dinamicamente? Cioè, ciò
che ci occorre è creare una stringa in parte "hardcoded" e in parte
basata sull'input dell'utente? Non potete indovinare ciò che l'utente
inserirà e quindi non potete scrivere questa parte in anticipo. Quello
che *potete* fare è *concatenare* l'input dell'utente dentro la stringa
hardcoded. Il modo per farlo e usare il segno d'addizione (**+**), che,
quando usato fra *stringhe*, le unirà insieme in un'unica più lunga.

Ecco un esempio: supponiamo di voler che l'utente inserisca il nome di
una abilità e che quindi noi vogliamo inserire questo nome in una
stringa hardcoded preesistente che sarà memorizzata in un'altra
variabile. Quello che dobbiamo fare sarà:

   .. code:: mtmacro
      :number-lines:

      [h:existingString = "The skill name you entered is "]
      [h:concatString = existingString+skill+"."]
      [r:concatString]

E quello che accadrà sarà:

-  La linea 1 imposterà la parte "hardcoded" dell'output
-  La linea 2 imposterà la stringa concatenata, al valore di *più* il
   valore di (che MapTool stramperà) Tuttavia in questo caso, visto che
   MapTool sa già che è una stringa, non proverà a fare la somma
   matematica ma appenderà semplicemente il valore di dopo il valore di
   . Per essere grammaticamente corretti, noi concateniamo un'altra
   piccola stringa alla fine, questa volta, del periodo. Ricordate, le
   stringhe dentro alle parentesi quadre hanno bisogno di essere
   protette da apici (ma ovviamente non i nomi delle variabili!)
-  La linea 3 mostra il valore finale di dopo che gli sia stato appeso.
   L'output assomiglerà a questo:

..

   The skill name you entered is Archery.

Questo è un esempio molto semplice ma illustra l'essenza della
costruzione di stringhe, potete "sommarle" insieme con un segno di
addizione.

.. _come_proseguire:

Come proseguire?
================

Questa guida colora a malapena la superficie di tutte le potenzialità
del linguaggio di macro in MapTool. Tuttavia, usando semplicemente
queste tecniche base qui mostrate, potrete creare un sacco di utili
macro per giocare più facilmente in modo più divertente ai vostri
giochi. Le guide successive tratteranno comandi macro e tecniche più
avanzate.

`Category:MapTool <Category:MapTool>`__
`Category:Tutorial <Category:Tutorial>`__

.. |Macro-panels.jpg| image:: Macro-panels.jpg
.. |Tabbed-panels.jpg| image:: Tabbed-panels.jpg
