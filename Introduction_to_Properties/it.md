Campaign Properties
-------------------

Una delle caratteristiche più utili in MapTool è la capacità dei [tokens](Introduction_to_Tokens/it "wikilink") di portarsi dietro un assortimento di **Properties** (proprietà) allegate ad esse, che possono essere manipolate dalle macro ed usate per creare rapide esposizioni di informazioni. Di base le proprietà dei token sono come schede del personaggio incorporate.

Tuttavia, per il fatto che queste opzioni sono così utili, gli sviluppatori di MapTool hanno creato molti differenti modi di usarle e manipolarle. La presente guida tratterà della creazione di gruppi di Campaign Property (proprietà campagna), di come regolarli affinché abbiano valori predefiniti e del modo in cui impiegarli per plasmare gli Statsheet (scheda delle statistiche).

Il Regolamento d'Esempio o MTRPG
--------------------------------

Al fine di avere utili riferimenti durante lo svolgimento della guida, diversi collaboratori ed utenti di MapTool hanno creato il [Regolamento d'Esempio](Sample_Ruleset/it "wikilink") -- un semplice sistema di gioco di ruolo prodotto specificatamente per illustrare parti di Maptool. Chiameremo le suddette regole “MapTool RPG” - o in breve MTRPG. Quello che andremo a fare sarà creare un nuovo Campaign File (file di campagna) e impostare diverse *campaign properties* che corrispondano agli attributi delle MTRPG.

La Finestra Campaign Properties
-------------------------------

![](Edit-campaign-props.png "Edit-campaign-props.png")

Per cominciare ad operare sulle Campaign Properties (Proprietà Campagna), la prima cosa da fare è andare su **Edit &gt; Campaign Properties** così da aprire l'apposita finestra. Una volta dentro vedrete diverse schede e una mole considerevole d'informazioni.

Le schede presenti nella finestra **Campaign Properties** conteranno sei elementi:

-   **Token Properties**: qui dimorano tutte i gruppi di proprietà che un token potrebbe adoperare nella campaign corrente
-   **Repositories**: qui è dove potete designare un “[repository](Introduction_to_Campaign_Repositories/it "wikilink")” (deposito) online per contenere i campaign files, specialmente le immagini, allo scopo di migliorare i tempi di caricamento e la velocità quando ospitate o partecipate ad un gioco online
-   **Sight**: qui è dove si configurano le opzioni per i tipi di campi visivi della campaign corrente
-   **Light**: qui si configurano le sorgenti di luce e le aure della campaign corrente
-   **States**: questa scheda permette la configurazione degli [stati dei token](Token:state/it "wikilink") per la campaign corrente
-   **Bars**: qui è dove si configurano le [barre dei token](bar.name/it "wikilink") per la campaign in corso

Questa guida terrà in considerazione solamente la prima scheda, **Token Properties**.

La scheda Token Properties
--------------------------

![](Camp-props.png "Camp-props.png")

La prima scheda visualizzata all'apertura di Campaign Properties è la “Token Properties”. Questa appare relativamente semplice, ma li si annidano enormi potenziali. Ci sono 3 campi di testo in questa scheda:

-   Name: questo è come chiamerete una gruppo di proprietà esposto in basso. Quando aprite la finestra campaign properties nessun gruppo di proprietà sarà evidenziato, perciò il campo sottostante risulterà vuoto.
-   Token Type: la colonna sul fianco sinistro non è editabile, elenca per nome tutti i gruppi di proprietà appartenenti alla campaign corrente. L'unico gruppo predefinito esistente è **Basic**, è presente anche se non si carica nessuna campaign.
-   Una larga area di testo dove potete immettere le proprietà per la campaign corrente. In primo luogo apparirà vuota, lo sarà fintanto che non evidenzierete il nome di gruppo di proprietà dalla lista di sinistra **Token Type**, in questo caso compariranno le nomenclature di quella selezione con i loro valori.

### Token Type

In questo campo potete vedere i nomi della serie di “Property Types” differenti (potremmo immaginarli come insiemi di proprietà) che sono stati configurati nella campaign corrente. Se nessuna campaign è caricata, l'unico gruppo di proprietà presente sarà il *Basic*, quello predefinito. Il campo **Token Type** non sarà direttamente editabile dall'utente.

### Name

Questo è un semplice campo di testo dove potete inserire il nome che volete dare al rispettivo gruppo di proprietà. Questo nome comparirà nella colonna “Token Type” una volta fatto l*'update* (aggiornamento) cliccando in basso a destra. I nomi possono essere come preferite; per esempio molti utenti creano gruppi chiamati “PNG” per distinguerli dai “PG” nei giochi dove le statistiche e i tratti fra queste due entità differiscono.

### Properties

Qui è dove vi dovrete sbizzarrire. In questa area di testo potrete creare qualsivoglia proprietà che rifletta tutti i possibili valori numerici o statistiche attribuibili ad un personaggio da GDR (e anche altre proprietà, molti utenti ne creano alcune utili per scrivere macros ma che poi non appaiono in nessuna scheda del personaggio!).

Creare Properties
-----------------

### Properties Senza Valori Predefiniti

![](Basic-default-props.png "Basic-default-props.png")

Se andate a guardare gli [Attributi Primari del MTRPG](Sample_Ruleset/it#Attributi_Primari "wikilink"), potrete vedere che ce n'è sono quattro basilari per un personaggio: *Forza*, *Destrezza*, *Intelligenza* e *Resistenza*. Stiamo per sbarazzarci delle proprietà predefinite e sostituirle con queste nuove.

1. Andate su **Edit &gt; Campaign Properties**. Vedrete nel lato sinistro, sotto *Token Type*, che l'unico gruppo presente è “Basic”. Ora gli creeremo una nuova selezione di proprietà.

2. Nell'elenco **Token Type** a sinistra, selezionate *Basic*. Una volta fatto, vedrete molte proprietà stagliarsi con simboli di ogni sorta, come @, \#, e simili.

3. Selezionate tutto quello che è nell'area di testo e premete il tasto Cancella sulla vostra tastiera per eliminare ciò che concerne le proprietà. Avanti - non siate timidi!

4. Lasciate il campo **Name** inalterato - MapTools necessita obbligatoriamente di avere un gruppo di proprietà chiamato *Basic*, non potete cambiargli nome.

![](Default-props-replaced.png "Default-props-replaced.png")

5. Nell'area di testo sotto al campo **Name**, inserite il nome di ognuno dei quattro Attributi Primari del MTRPG in questo modo:

> `Forza`
> `Destrezza`
> `Intelligenza`
> `Resistenza`

Quando avete finito la vostra finestra assomiglierà a quella della schermata qui di fianco.

6. Una volta finito d'inserire le proprietà che volete, cliccate sul pulsante **Update**. Niente Panico! Le proprietà sono scomparse ma se riselezionerete *Basic* dalla colonna di sinistra riappariranno nell'area principale di testo.

7. Cliccate su **OK** per confermare tutti i vostri cambiamenti e chiudere la finestra **Campaign Properties**.

8. Andate su **File &gt; Save Campaign As** e salvate la vostra campaign col nome di **MTRPG.cmpgn**. A questo punto avete creato un nuovo file di campaign con un rinnovato gruppo di proprietà.

Quando create le proprietà in questo modo -- semplicemente elencando gli attributi uno dopo l'altro -- all'apertura di un token vedrete che queste proprietà non hanno alcun valore. Questo non significa che valgano zero o come se fossero una riga vuota - loro hanno letteralmente *nessun valore*. Generalmente questo non significa molto, ma è una distinzione importante in termini di scrittura delle macro (nella programmazione c'è una grossa differenza fra una stringa lasciata in bianco ed una variabile al momento *vuota*!).

Una volta aggiornato la scheda Token Properties tutti i nuovi tokens e quelli già presenti sulla map “erediteranno” le nuove proprietà impostate.

**NOTA**: Il Name dei gruppi di proprietà non può contenere al suo interno degli spazi - quindi se avete dei gruppi chiamati ad esempio “Punti Ferita”, dovrete necessariamente inserirli come *PuntiFerita*.

### Creare Properties comprensivi di Valori Predefiniti

![](Newprops-defvalues.png "Newprops-defvalues.png")

Ora, sappiamo che le MTRPG contemplano un valore minimo di 1 per ogni attributo primario. Ha quindi senso impostare il “valore predefinito” di queste proprietà a 1, cosicché ogni token non possa scendere al di sotto del punteggio minimo consentito per gli attributi. Le direttive di conseguimento sono::

1. Aprire la finestra Campaign Properties.

2. Selezionare il gruppo *Basic*.

3. Editare le proprietà copiandole dalle seguenti (come anche dall'immagine):

> `Forza:1`
> `Destrezza:1`
> `Intelligenza:1`
> `Resistenza:1`

4. Cliccate su **Update**.

Inserendo i due punti alla fine di ogni attributo seguiti dal numero 1, avete detto a MapTool che il valore predefinito per le proprietà corrispondenti è 1 (in altre parole, qualsiasi valore mettiate dopo i due punti diventerà il *valore prerdefinito* per quella proprietà). Notate che in basso alla finestra Token Properties c'é una legenda descrittiva sulle varie opzioni utilizzabili nelle proprietà.

Adesso, se trascinate un nuovo token sulla map e guardate le sue proprietà (doppio-cliccate sul token ed entrate nelle scheda Properties all'interno della finestra di dialogo **Edit Token**), vedrete che ha i valori predefiniti.

Approposito: non preoccuparti di nessun tokens che potresti aver già configurato - aggiungere o modificare i valori predefiniti *non* ne sovrascriverà le proprietà. MapTool è sufficientemente furbo da gestire la cosa.

### Mettere in Mostra le Properties nello Statsheet

![](Statsheet-props.png "Statsheet-props.png")

MapTool integra una funzionalità chiamata **Statsheet** (scheda delle statistiche) che abbiamo brevemente accennato nel capitolo [Introduzione ai Tokens](Introduction_to_Tokens/it "wikilink") - in pratica è una finestra a scomparsa che appare nell'angolo a sinistra della map ogni volta che indugiate con il mouse sopra un token.

Potreste dire: “Un momento... quando punto il mio token non c'è nessun statsheet! dove sta?” Il motivo per cui non lo vedete è che lo Statsheet è gestito dalle Campaign Properties - mostrerà le proprietà di un token (insieme ad una versione larga della sua immagine) *solo* dopo aver soddisfatto un paio di requisiti:

-   Le proprietà sono configurate per essere mostrate dallo statsheet; e
-   Le proprietà da mostrare devono avere effettivamente un valore

#### Configurare le Properties per essere visualizzate

![](Newprops-visible.png "Newprops-visible.png")

Se guardate in basso della parte adibita alle **Campaign Properties**, nella scheda **Token Properties**, vedrete una legenda dei caratteri che serviranno a rendere visibile una proprietà nello Statsheet. Ci sono tre opzioni di visualizzazione, ognuna di queste va indicata ponendo il simbolo corrispondente prima del nome della proprietà:

1.  **\***: un asterisco significa “mostra questa proprietà sullo statsheet”
2.  **@**: significa “mostra questa proprietà solo al proprietario del token (ed al GM)”
3.  **\#**: significa “mostra questa priprietà solo al GM (nemmeno il proprietario del token può vederla)”

L'asterisco è **richiesto** per ogni statistica da mostrare in generale - se non mettete un asterisco per prima, niente verrà mostrato a prescindere di quant'altro scriviate li. D'altro canto i simboli @ e \# sono facoltativi.

Quindi, per il nostro gioco, andremo a configurare tutte le proprietà per essere visibili a chiunque (solo con una stellina). Per farlo, aprite le vostre proprietà ed editatele come mostrato in seguito:

> <tt>
>
> `*Forza:1`
> ` *Destrezza:1`
> ` *Intelligenza:1`
> ` *Resistenza:1`
> </tt>

Da adesso, quando sposterete il mouse sopra un token, vedrete la finestra a scomparsa dello Statsheet (guardate la schermata sopra) con i valori delle proprietà di Forza, Destrezza, Intelligenza e Resistenza. Inoltre, poiché ogni nuovo token parte con dei valori predefiniti, lo Statsheet apparirà subito per tutti quanti.

#### Short Names

![](Newprops-shortnames.png "Newprops-shortnames.png")

A volte, i nomi delle proprietà possono diventare troppo lunghi (o risultare poco amichevoli - niente spazi e via dicendo). MapTool vi permette di inserire uno *Short name* (abbreviazione) per ogni proprietà. Per farlo inserite semplicemente la sigla fra le parentesi dopo il nome della proprietà, in questo modo:

> <tt>
>
> `*Forza(For):1`
> ` *Destrezza(Des):1`
> ` *Intelligenza(Int):1`
> ` *Resistenza(Res):1`
> </tt>

Queste sigle verranno mostrate nello Statsheet al posto del nome intero della proprietà.

**Le sigle hanno una sola funzione espositiva - quando vi riferirete alle proprietà in una macro, dovrete utilizzare il nome completo appropriato.**

### Creare Properties Derivate

![](Newprops-derived.png "Newprops-derived.png")

![](Statsheet-with-allnewprops.png "Statsheet-with-allnewprops.png")

Bene, ora faremo qualcosa di bello. In molti giochi di ruolo ci sono attributi dei personaggi che derivano da altre statistiche - ad esempio, nel regolamento di *Savage World*, la statistica di “Parata” è basata sull'abilità *Combattimento*; similmente, in Dungeons & Dragons, i “Punti Ferita” si ricavano in parte dal punteggio di “Costituzione”.

Tornando a noi, potete creare questi altri attributi derivati come proprietà separate, immettendo manualmente i loro valori per ogni token - ma come potreste farli calcolare direttamente a MapTool? Proprio così, le campaign properties di MapTool non devono essere per forza numeri o testo, ma anche calcoli o equazioni basati su altre proprietà che il token possiede.

In MTRPG, ci sono tre statistiche *derivate*: Punti Ferita, Armatura e Movimento. Queste statistiche si abbreviano con “PF”, “AR” e “MV”. Per fare un esempio, stiamo per impostare i *Punti Ferita* e il *Movimento* per far si che vengano calcolati tramite le proprietà già esistenti. Lasceremo l*'Armatura* in un secondo tempo (ci vuole un calcolo più complesso per esplicare il suo valore e noi ce la stiamo prendendo comoda).

Prima di tutto abbiamo bisogno di aggiungere le proprietà per questi tre valori derivati:

1. Aprire il gruppo di proprietà “Basic”.

2. Sotto *Resistenza*, inserire quanto segue:

> <tt>
>
> `*PuntiFerita(PF)`
> ` *Armatura(AR)`
> ` *Movimento(MV)`
> </tt>

A questo punto noterete che non abbiamo impostato nessun valore predefinito. Non premete ancora **Update** - immettete del codice macro per creare i valori derivati.

Nel [MTRPG](Sample_Ruleset/it "wikilink") possiamo osservare che i “Punti Ferita” sono il valore della “resistenza” moltiplicato per 6. Replicare questo calcolo nelle campaign properties è veramente banale. Editate la proprietà “Punti Ferita” come leggete:

> <tt>
>
> `*PuntiFerita(PF):{Resistenza * 6}`</tt>

Quello che abbiamo fatto qui è inserire [codice macro](Introduction_to_Macro_Writing/it "wikilink") nella proprietà come fosse un valore predefinito (ricordate, i valori predefiniti si mettono sempre dopo i due punti) in grado di far calcolare a MapTool il suo punteggio effettivo. Due cose accadono in questa procedura:

1.  Abbiamo racchiuso il calcolo in { } per far sapere a MapTool che il testo racchiuso nelle parentesi graffe deve essere gestito come una macro e non solo come testo.
2.  All'interno delle parentesi graffe abbiamo detto, “Trova il valore della proprietà *Resistenza*, moltiplicalo per 6, e rendi ciò che ne risulta il valore della proprietà *Punti Ferita*”

Ora, per gestire l'attributo *Movimento*, il nostro lavoro sarà altrettanto semplice: ci serve istruire MapTool a prendere il valore della proprietà *Destrezza* e assegnarlo invariato alla proprietà *Movimento*. Per farlo, effettuate le modifiche seguenti:

> <tt>
>
> `*Movimento(MV):{Destrezza}`</tt>

Quando avete finito, la serie completa delle proprietà risulterà come questa:

> <tt>
>
> `*Forza:1`
> ` *Destrezza:1`
> ` *Intelligenza:1`
> ` *Resistenza:1`
> ` *PuntiFerita(PF):{Resistenza * 6}`
> ` *Armatura(AR)`
> ` *Movimento(MV):{Destrezza}`
> </tt>

Quando passerete il puntatore del vostro mouse sopra il token, lo Statsheet dovrebbe somigliarsi a quello nella schermata in alto a destra. Ricordate, anche se abbiamo specificato che *Armatura* dovrà comparire nello Statsheet, solo le proprietà aventi un valore verranno effettivamente mostrate - *Armatura* è ancora vuoto, lo vedrete solamente quando gli verrà assegnato un valore.

Salvare la Vostra Campaign
--------------------------

A questo punto, avete creato un gruppo di proprietà della campagna, collocato un token sulla map e pasticciato con le proprietà da voi create. Probabilmente dovreste salvare il vostro lavoro in un file \[Campaign file\]. Questo salverà i tokens, le proprietà che avete creato e tutte le informazioni che avete messo nella campaign finora.

Inoltre, questo vi permetterà di lavorare sulla stessa campaign in futuro, per provare i trucchi degli altri tutoriali di MapTool.

Per salvare la vostra campagna:

1.  Andate su **File -&gt; Save Campaign As...**
2.  Nella finestra di dialogo inserite il nome del file. Qualcosa di simile a **MTRPG.cmpgn** va bene!
3.  Cliccate su **OK**

La vostra campagna è stata salvata e voi potete riaprirla quando volete, lavorandoci di nuovo!

Per piacere fate caso al fatto che il salvataggio creato ha una versione ben specifica ed incompatibile con una versione *vecchia* di MapTool; tuttavia la maggior parte di campaign files possono essere riaperti con una versione più nuova del programma (non è garantito, nonostante...MapTool sia in costante evoluzione!)

Alcuni Dettagli Tecnici
-----------------------

Un paio di volte in questa ed altre guide i token properties sono stati descritti come “le proprietà *visibili*” nella campaign, oppure le proprietà impostate “*per questa campaign*”. C'è un motivo per l'utilizzo di queste diciture.

Vedete, un token - ipotizzando di averlo scomposto per analizzare il suo funzionamento interno - è un file XML che contiene una *carrellata* di informazioni. Esso contiene le informazioni riguardo la propria immagine, la dimensione, il campo visivo, la luce, la sagoma, ed ovviamente le sue proprietà. Ciò che è importante capire è che il token memorizzerà non soltanto le proprietà del MTRPG, ma, nel caso venga salvato in un file **.rptok** o ripreso da un altro campaign file, terrà registrate anche le proprietà della campagna da dove proviene. Queste informazioni non saranno visibili, ma saranno comunque stipate al suo interno.

Quindi, in realtà, un assortimento di Campaign Properties indica le proprietà che:

-   Potete vedere con un doppio clic a ridosso di un token, e
-   Potete modificare direttamente cliccando nella cella accanto a loro

Potrebbe suonarvi come una ricetta per il disastro - cosa succederebbe se configurereste una proprietà già stabilita in precedenza ma invisibile? Fortunatamente Maptool, durante l'esecuzione di una macro, non tenterà di accedere a nessuna proprietà nascosta se non gli verrà chiesto *Specificatamente* tramite due funzioni speciali ben precise. Dunque state tranquilli, non potete accedere accidentalmente a proprietà che non configurabili nelle Campaign Properties.

Tirando le somme, se un Property Type (come il gruppo predefinito *Basic*) ha una proprietà chiamata **PF**, questa verrà registrata nel file XML del token con il nome di **PF**. Se un altro property type che avete creato (ad esempio il gruppo personalizzato *Pathfinder*) possiede anch'esso una proprietà chiamata **PF**, entrambe si riferiranno allo stesso parametro nel token. Modificare il valore di **PF** quando il token è *Basic* mostrerà lo stesso valore anche quando si cambierà il gruppo in *Pathfinder*.

Proseguire da qui
-----------------

MapTool supporta proprietà e derivate di proprietà molto elaborate, con svariate funzioni matematiche e operazioni. Alcune delle più comuni utilizzabili sono (gli esempi non si riferiscono per forza a MTRPG, sono solo esempi):

-   **Operatori matematici di base**: addizione (+), sottrazione (-), moltiplicazione (\*), e divisione (/)
    -   **Esempio**: `PuntiFerita: {Resistenza * 6}`
-   **Arrotondamento**: ci sono alcune *funzioni* che consentono di arrotondare i numeri una volta divisi
    -   **Floor**: la funzione floor() arrotonda per *difetto*. **Esempio**: `PuntiFerita:{floor(Costituzione / 2)}` dividerebbe la Costituzione in due arrotondandola per difetto
    -   **Ceiling**: la funzione ceil() agisce nella stessa maniera di floor(), ma arrotonda per eccesso. **Esempio**: `PuntiFerita:{ceil(Costituzione/2)}`

<Category:MapTool> <Category:Tutorial>