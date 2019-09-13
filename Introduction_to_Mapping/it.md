__TOC__

### Prima le prime cose: Cos'è MapTool?

Bene o male avete gia un'idea di cosa sia MapTool e di cosa faccia,
voglio solo spendere poche parole riguardo all'obbiettivo primario di
MapTool:

**MapTool è un programma che vi aiuta a condividere un "tavolo virtuale"
con i vostri amici, così da poterci giocare sopra.**

Questo è ciò che MapTool fa, e le sue features hanno puntato a offrirvi
una sequela di opzioni, dalla più semplice alla più complessa, per
raggiungere questo obbiettivo.

In tutti i discorsi di macro e proprietà e tabelle e scripting che
seguiranno in questa e in altre guide, non perdete mai di vista la
ragione per la quale state investendo tempo in MapTool: E' un modo per
giocare con gli amici (ndr: O conoscerne nuovi\!).

### Riguardo a questa guida

Lo scopo di questa guida non è quello di indirizzarvi verso le
rivoltanti viscere del sistema di scripting delle macro di MapTool,
luci, proprietà o altra roba complicata. Anzi, questa guida vuole
iniziarvi all'uso di MapTool come programma per *mapping* per giochi di
ruolo. Altre guide indirizzano ad argomenti come [Ospitare una partita
online](Introduction_to_Game_Hosting/it "wikilink"), [lavorare con i
tokens](Introduction_to_Tokens/it "wikilink"), [predisporre visione e
luci](Introduction_to_Lights_and_Sights/it "wikilink"), e [scrivere
macro](Introduction_to_Macro_Writing/it "wikilink").

Le istruzioni seguenti dovrebbero renderti in grado di poter cominciare
ad usare MapTool come un tool di battle mapping/general mapping. Si
danno per scontate alcune cose:

1.  Tu sai come creare o ottenere immagini di mappe. Esistono terabytes
    (exabytes\! yottabytes\!) di immagini di mappe nel web. Controlla
    [RPTools Gallery](http://gallery.rptools.net) oppure
    [RPGMapShare](http://www.rpgmapshare.com) per tonnellate di
    materiale riguardo a mappe.
2.  Puoi avviare MapTool sul tuo computer. MapTool necessita Java 1.5
    installato sulla tua macchina; Sta a te trovare ed ottenere questa
    roba.

Quindi proseguiamo. Per iniziare:

1.  Scaricate MapTool da <http://rptools.net>. L'ultima "build" di
    MapTool è sempre posta in cima a [questa
    lista](http://www.rptools.net/index.php?page=downloads#MapTool).
    Attualmente, l'ultima build è la 1.3.b88 (b88 tuttavia non funziona
    bene, andrebbe usata la b87). **NOTA**: Puoi anche avviare [Java
    WebStart](http://www.rptools.net/index.php?page=launch) Per avviare
    MapTool senza scaricare e decomprimere il file.
2.  Se scarichi e decomprimi il file zip di MapTool, decomprimilo da
    qualche parte sul tuo computer, poi assicurati che funzioni. Il file
    .bat incluso imposta dei parametri quando avvii il programma, come
    la memoria allocata ecc... Il programma si avvia cliccando sul file
    .jar, ma così facendo otterrete un warnings. Se usi windows, puoi
    usare il windows launcher, che ti consente di alterare le
    impostazioni in modo molto semplice.

Ora, cominciamo a scoprire le funzioni.

## Inserire immagini nella tua Resource Library

La **Resource Library** di MapTool è una collezione di "puntatori" o
"links" a cartelle sul tuo computer, contenenti le immagini che tu
vorrai usare in MapTool. MapTool ha integrato una selezione base di
immagini, ma puoi aggiungere quante e quali immagini desideri - tu hai
il controllo pieno delle immagini inseribili in MapTool.
![Mt-f-addtoreslib.jpg‎](Mt-f-addtoreslib.jpg‎ "Mt-f-addtoreslib.jpg‎")

![Add-asset-dialog.jpg](Add-asset-dialog.jpg "Add-asset-dialog.jpg")

1\. Ottieni immagini (mappe, per esempio) da qualche parte: possono
essere scaricate dal web, o create da te. Inseriscile in una directory
qualsiasi - questa directory è importante per il passo 3.

2\. Apri MapTool.

3\. Seleziona **File -\> Aggiungi alla Resource Library**. Questo aprirà
una finestra di dialogo (clicca sulla miniatura per vedere le immagini a
grandezza naturale, nota che le miniature sono di una vecchia versione
di MapTool; il menù corrente potrebbe essere un po' differente ma le
opzioni generali rimangono invariate).

4\. Questa finestra mostra tre schede, quella di default è **Local
Directory**. Per agginugere immagini dalla directory locale, cliccate
sul pulsante affianco al campo path e selezionate la directory
contenente le immagini che desiderate aggiungere. Nella seconda scheda
potete indicare un URL da cui scaricare le risorse e nella terza scheda
vi è permesso installare alcuni pacchetti di immagini che sono stati
resi disponibili da alcuni artisti proprio per MapTool.

5\. Nel momento che avete fatto la vostra scelta, cliccate su
Install\>\> in modo che MapTool aggiunga le immagini alla vostra
resource library.

**NOTA**: Il nome della cartella nella Resource Library di MapTool sarà
lo stesso della directory che hai richiamato nel passo 3.


![Mtreslib.jpg](Mtreslib.jpg "Mtreslib.jpg")

5\. Se selezioni una cartella nella tua Resource Library, vedrai la
miniatura delle immagini all'interno di quella cartella. NOTA: Se la tua
cartella ha sottocartelle, clicca il **+** per espandere la struttura ad
albero della cartella.

**NOTA**: Siccome le cartelle che appaioni nella Resource Library sono
solo puntatori a directory sul tuo hard drive, non devi pensare che
MapTool stia duplicando ogni file -- La Resource Library è solo un modo
per MapTool di sapere da dove prendere le immagini richieste.



## Creazione di una Map

![Map-newmap.jpg](Map-newmap.jpg "Map-newmap.jpg")

![Map-new-dialog.jpg](Map-new-dialog.jpg "Map-new-dialog.jpg")

1\. Seleziona **Map -\> New Map**. Si aprirà la finestra di dialogo *Map
Properties*.

2\. Nella parte sinistra della finestra di dialogo di *Map Properties*
vedrete diverse opzioni e campi di testo.

  - **Name**: questo è il titolo della map. Notate che selezionando una
    map image il titolo acquisirà il nome di questa. Scegliere il titolo
    alla fine risulta l'idea migliore, così da poter chiamare la map
    come si preferisce invece di un generico "mappa001.jpg" o come era
    originariamente chiamata l'immagine.
  - **Cell Type**: map esagonale, squadrata oppure completamente priva
    di griglia.
  - **Distance Per Cell**: questo è il valore arbitrario di una
    cella(*Es.*, Nella la 4a edizione di Dungeons & Dragons è tutto
    calcolato in quadrati, quindi si può impostare semplicemente questo
    valore ad 1)
  - **Pixels per cell**: questo è quello che copre una cella in pixel –
    il valore predefinito è 50. E' molto importante per la scalatura
    delle map images che scaricate.
  - **Vision Distance**: MapTool comprende visione, nebbia-di-guerra ed
    altre funzioni, sicché questo valore indica la distanza predefinita
    fin dove un personaggio può vedere


![Background-dialog.jpg](Background-dialog.jpg "Background-dialog.jpg")

3\. Cliccate sul bottone **Background**. Verrà visualizzato un pop-up di
dialogo contenente diverse opzioni. La texture di background e/o il
colore scelto saranno ripetuti infinitamente in ogni direzione.

  - **Swatch**: consente di utilizzare un colore uniforme come sfondo
    della map.
      - <font color="red">**Attenzione:** Nella recente versione
        1.3.b53, se selezionate il campione in alto a sinistra (quello
        bianco), Maptool restituirà un errore. L'errore non causerà
        crash o altro, ma non imposterà nemmeno il bianco come sfondo.
        Una valida alternativa è ottenere il medesimo risultato tramite
        la scheda Hue o RGB.</font>
  - **Hue/RGB**: consente di specificare i colori invece di selezionare
    uno swatch.
  - **Texture** (che io uso più di frequente): da accesso alla propria
    resource library, dove potete selezionare una texture che sarà
    utilizzata come background.


![Map-mapbutton.jpg](Map-mapbutton.jpg "Map-mapbutton.jpg")

4\. Se avete un'immagine di map in mente (come una scaricata, o creata
con Gimp, o qualcosa del genere) cliccate sul bottone **Map**. Verrà
visualizzata una finestra di dialogo con la tua Resource Library.
Selezionate l'immagine che avete intenzione di usare. Questa immagine
sarà sovrapposta al layer del background che avete già selezionato.


![Map-create-done.jpg](Map-create-done.jpg "Map-create-done.jpg")

5\. Nel momento in cui vi riterrete soddisfatti di background e map
(potete osservarne un'anteprima a controprova, come nell'immagine di
fianco) dategli un nome e cliccate su **OK**. La map verrà caricata
nella finestra principale di MapTool.



### Creare molteplici Maps in una Campaign

MapTool consente di creare più mappe comprese in un unica campagna. Il
procedimento è semplice: ripetere i passi elencati in [Creazione di una
Map](Introduction_to_Mapping/it#Creazione_di_una_Map "wikilink") per
ogni map, selezionare una nuova immagine, la texture/colore di
background ed il titolo per ognuna di esse.

Ogni nuova map creata lo sarà automaticamente all'interno della campaign
a cui lavorate in quel momento (creare una nuova map non salva
automaticamente la campaign, assicurarsi di [salvare i tuoi
lavori](Introduction_to_Mapping/it#Salvare_i_tuoi_lavori "wikilink")
ogniqualvolta ne completate una).

E' inoltre possibile aggiungere nuove maps ad una campaign
precedentemente salvata - basta aprire il file di campaign (andando su
*File \> Open Campaign*') e seguire i passi per creare una nuova map.

## Finestra Principale di MapTool

### Layers di MapTool

![Layer-window.png](Layer-window.png "Layer-window.png")

Quando una map è caricata potete vedere un piccolo box al suo interno
chiamato *Layer*. Le maps di MapTool possiedono quattro layers:

  - **Background**: questo è il layer per le immagini, maps di sfondo e
    qualsiasi cosa non possa muoversi.
  - **Hidden**: per le partite online, questo è un layer che solo il GM
    può vedere.
  - **Object**: questo è il layer per gli oggetti simili ai tokens, cose
    che potrebbero muoversi o essere spostate dai giocatori (lampade,
    tavoli, ecc.).
  - **Token**: questo è il layer dove vanno i tokens (i tokens sono
    piccole immagini che rappresentano i personaggi giocanti e non).
    Siate sicuri di aver selezionato il layer token quando aggiungete
    personaggi e nemici sulla map.

Pensate ai layers di MapTool come quattro differenti fogli di acetato
oppure carta da lucido uno sopra l'altro. Il più basso - il
**Background** - è dove disegnate le parti base della map: muri, scale,
alberi, ecc. Sul foglio superiore, quello chiamato **Objects** disegnate
le *cose* che i personaggi possono usare, scompigliare o rompere: porte,
casse, tavoli, sedie e così via. In quello ancora seguente - il layer
**Hidden** - potete mettere le cose che solo il GM può vedere (che ad
esempio possono essere oggetti *o* personaggi nascosti\!). Infine, nel
layer in cima - il layer **Token**, mettete le miniature - mostri,
personaggi e PNG del mondo di gioco.

I tokens possono essere posati su uno qualsiasi dei 4 layers in MapTool.
Per farlo basta premere il tasto destro del mouse sopra l'immagine del
token e selezionare **Change To \>**. Nel menù selezionate il layer dove
volete che sia spostato il token e questo lì vi si posizionerà.

### Selezionare Maps

![Blueglobe.jpg](Blueglobe.jpg "Blueglobe.jpg")

![Maplist.jpg](Maplist.jpg "Maplist.jpg")

Se create una sola map nella vostra campaign, questa verrà caricata e
sarà l'unica map che vedrete.

Se voi [create più
maps](Introduction_to_Mapping/it#Creare_molteplici_Maps_in_una_Campaign "wikilink")
o avete una campaign che ne possiede potete scegliere fra di loro
cliccando sull'icona del globo in alto a destra della finestra di
MapTool - questa presenta un elenco di possibili maps. Notate che se c'è
una sola map, cliccando sul globo blu sarà mostrato il nome della map.



### Scalare e Spostare

Per scalare la map potete usare la rotellina del mouse oppure il segno
di uguaglianza per ingrandire ed il trattino per rimpicciolire.

Premere il segno di addizione renderà la scalatura 1:1 .

Per muovere la map premete cliccate il tasto destro su di essa e
spostate il mouse. Questo trascinera la map in qualsiasi direzione.

## Basi dei Token

[I MapTool Tokens](Token/it:token "wikilink") (o semplicemente
"Tokens")sono semplici immagini che agiscono come rappresentazione
visuale di molte cose in una map di MapTool. L'uso più comune che hanno
è la rappresentazione dei personaggi giocanti e non giocanti; in altre
parole, i tokens prendono il posto delle miniature sulla map virtuale.

I Tokens, come tutto il resto, partiranno come file immagine memorizzati
all'interno della tua [Resource
Library](Macros:Glossary/it#R "wikilink"). MapTool viene fornito con
alcuni tokens inclusi (e abbiamo un bel programma separato chiamato
[TokenTool](http://www.rptools.net/index.php?page=tokentool) che ne
consente la creazione), oppure potete supplire a propria scelta
prendendone dovunque ne troviate.

Questa sezione della guida di Introduzione al Mapping si occupa solo di
alcune delle più basilari, comuni cose si potrebbe voler fare con
MapTool Tokens. Ci sono *molte* caratteristiche, trucchi e fantastiche
funzioni disponibili lavorando con i tokens - talmente tante da
meritarsi una guida tutta per loro.

### Placing Tokens on the Map

![Default-library.jpg](Default-library.jpg "Default-library.jpg")

1\. Per vedere i tokens predefiniti menzionati prima, andate nella
cartella Default nella vostra *Resource Library* e cliccate sul**+** per
espanderla.


![Default-tokens.jpg](Default-tokens.jpg "Default-tokens.jpg")

2\. Selezionate la cartella Tokens.


![Token-drag-to-map.jpg](Token-drag-to-map.jpg "Token-drag-to-map.jpg")

![Token-on-map.jpg](Token-on-map.jpg "Token-on-map.jpg")

3\. Nella finestra sottostante (dove appaiono le miniature), usate il
mouse per trascinare un token sulla map. Il cursore si trasformerà in
una mano, vi basterà trattenere il token e rilasciarlo su un punto
qualsiasi della map.

Quando rilascerete il pulsante del mouse, il token apparirà sulla map
come mostrato nella miniatura.



### Muovere i Tokens

Una volta che un token è sulla mappa è possibile spostarlo usando il
mouse oppure muoverlo selezionando il token (cliccandoci sopra) e usando
le frecce direzionali per muoverlo e premendo **D** per completare il
movimento.

Se cercate di creare un sentiero complesso potete premere la barra
spaziatrice per creare un waypoint ad ogni tappa.

### Cambiare Token's Name, GM Name e Label

![Token-default-name.jpg](Token-default-name.jpg
"Token-default-name.jpg")

![Edit-token.jpg](Edit-token.jpg "Edit-token.jpg")

I tokens possiedono tre tipi di "nome" che potete assegnargli. Nel
momento in cui un token viene trascinato la prima volta sulla map gli
viene assegnato un nome predefinito (tipicamente lo stesso del
*filename* privo di estensione che il token ha sul tuo computer). Per
esempio, il token mostrato nell'immagine di fianco è stato trascinato
dalla selezione predefinita di token di Maptool ed il suo nome ereditato
è "Hero".

I tre nomi che un token può avere sono:

  - **Token Name**: Il nome del token che appare a tutti gli utenti.
    Questo non è opzionale.
      - <font color="red">**NOTA**: Assicuratevi che ogni token abbia un
        nome unico\! Altrimenti le macros di Maptool potrebbero assumere
        un comportamento imprevedibile.</font>
  - **GM Name**: Questo nome appare solamente alle persone connesse a
    MapTool con il ruolo di "GM".
  - **Label**: Questo testo appare al di sotto del Token Name, ed è
    visibile a tutti.

Per cambiare il name, GM name e/o label dei token:

1\. Doppio-clic sulla immagine del token sulla map. Questo aprirà la
finestra di dialogo **Edit Token**, come illustrato di seguito.


![Edit-token-changednames.jpg](Edit-token-changednames.jpg
"Edit-token-changednames.jpg")

![New-token-names.jpg](New-token-names.jpg "New-token-names.jpg")

2\. Nel campo **Name** inserire il nome che preferite. In questo esempio
ho inserito "Bork the Brave".

3\. Nel campo **GM Name** inserite un nome. Per questo esempio ho
inserito "Cork the Cowardly".

4\. Nel campo **Label** inserite un'etichetta. Per questo esempio ho
inserito "Human Warrior".

5\. Cliccate su **OK** per salvare i cambiamenti.

Una volta che avrete confermato vedrete il token cambiato:

Potete effettuare questo processo di cambio nome per ogni token
depositato sulla map.



### Cambiare immagine ad un Token

Saltuariamente, quando create un nuovo token, potreste voler cambiare
l'immagine sulla sua facciata. Poniamo che, per esempio, troviate un
ganzo disegno giusto a punto adatto per il vostro signore supremo del
male, ma che abbiate già un token a lui associato - non volete
cancellare tutto il token solo per cambiarne l'immagine vero? E' un
suicidio. Piuttosto, cambiate semplicemente l'immagine del token tramite
i seguenti passi:

![Edit-token.jpg](Edit-token.jpg "Edit-token.jpg")

1\. Assicuratevi di avere la nuova immagine nel formato PNG o JPG già
disponibile nella vostra Resource Library. Se gettate un occhio sopra,
alla sezione [Inserire immagini nella tua Resource
Library](Introduction_to_Mapping/it#Inserire_immagini_nella_tua_Resource_Library "wikilink"),
questa parla di come aggiungere un immagine di map alla propria Resource
Library: bene, le immagini dei token (o in effetti *qualsiasi* immagine)
possono essere aggiunte esattamente nello stesso modo.

2\. Doppio-cliccate sopra il token per aprire la finestra di dialogo
**Edit Token**.


![Edit-token-changeimage.jpg](Edit-token-changeimage.jpg
"Edit-token-changeimage.jpg")

3\. In alto a sinistra di questa finestra di dialogo cliccate sul
piccolo segno di addizione in verde.


![New-image-picked.jpg](New-image-picked.jpg "New-image-picked.jpg")

4\. Nella finestra di dialogo **Choose Image**, selezionate la cartella
della Resource Library dove risiede la nuova immagine del token (un
bordo rosso e bianco indica l'immagine che avete selezionato) e cliccate
su **OK**.


![Token-image-changed.jpg](Token-image-changed.jpg
"Token-image-changed.jpg")

5\. Quando avrete premuto **OK**, tornerete nella finestra di dialogo
Edit Token e vedrete l'immagine cambiata in quella che avete
selezionato.



### Cambiare la grandezza dei Tokens

![Token-rightclick.jpg](Token-rightclick.jpg "Token-rightclick.jpg")

I Tokens assumono automaticamente la dimensione di un quadrato della
griglia (notare che una griglia predefinita misura 50x50 pixel). Se
premete il pulsante destro su uno di essi un menù esibirà un vasto
numero di opzioni - una di queste è **Size**. E' quindi possibile
configurare il suo valore e generare creature grandi, enormi o
gigantesche e via dicendo. L'immagine di fianco mostra il menù che
appare alla pressione del tasto destro su un token.

NOTA: questi valori di taglia (large, huge, gargantuan, ecc.) vengono
applicati solo alle maps che hanno una griglia (ricordate, quando create
una map avete l'opzione di crearla senza griglia). Se usate una mappa
senza griglia i valori di size sono molto più finemente graduati.



## Salvare i tuoi lavori

Il formato di "salvataggio" predefinito di MapTool si chiama *Campaign
File*. Questo Campaign File (con estensione *.cmpgn*) contiene le maps e
i tokens che avete sistemato. Se siete interessati a questo genere di
cose, il file della campagna è in realtà un file XML zippato.

Per salvare il lavoro appena svolto scegliere **File -\> Save
Campaign**, date un nome alla vostra e questo è quanto.

Quando salvate una campagna Maptool salva la locazione dei tokens su
tutte le maps così che possiate riprendere immediatamente da dove
avevate lasciato\!

## Esportare Map Images

MapTool può esportare le tue map images su file immagine (Formato PNG).
Per esportare un immagine su una locazione a tua scelta:

1\. Andare su **File-\>Export** e selezionare **Screenshot As**.

2\. Alla comparsa della finestra di dialogo selezionare "View" (la vista
GM, dove potete vedere tutto, oppure la vista Player, dove le uniche
cose visibili sono quello che i *players* possono vedere...I lo dicevo
che Maptool ha diverse capacità di visualizzazione molto cool\!)

3\. Selezionare la destinazione del tuo file utilizzando il pulsante
Browse (o, alternativamenete, spediscilo ad un server FTP)

4\. Clicca su **Export**.

## Prossimi Passi

Ora ciò che avete fra le mani è una map base con alcuni tokens al di
sopra, il prossimo passo è connettervi con i vostri amici su internet (o
faccia a faccia) e usare tutto questo per una sessione di gioco\! Questo
argomento viene trattato in This topic is covered in the [Introduzione
al Game Hosting](Introduction_to_Game_Hosting/it "wikilink").

[Category:MapTool](Category:MapTool "wikilink")
[Category:Tutorial](Category:Tutorial "wikilink")