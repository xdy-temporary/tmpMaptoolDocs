## Qu'est-ce qu'une Macro?

Une Macro est une méthode simple d'automatiser des actions dans MapTool.
La plupart du temps, les macros sont des scripts lus par un *analyseur
syntaxique*, qui les interprète et garantit que les différentes parties
sont traitées de la bonne manière ( par exemple, en garantissant qu'une
commande pour ajouter deux nombres entre eux et bien traitée comme une
commande de Macro et pas comme du simple texte dans une fenêtre de
discussion).

Les Macros ont commencé tout doucement dans MapTool, mais maintenant, le
langage de script est devenu un ensemble très complet de commandes et de
fonctions qui peuvent pratiquement exécuter toutes les opérations que
vous pouvez imaginer \!

## Ce que vous devriez déjà connaître

Les Macros représentent le point à partir duquel nous commençons à
approfondir les caractéristiques et les fonctionnalités les plus
puissantes - et les plus compliquées - de MapTool. Même si ce guide se
veut le plus accessible possible, il y a quelques points que vous êtes
supposés avoir déjà acquis :

1.  Nous supposons que vous avez lu "[Introduction à la création de
    carte (fr)](Introduction_to_Mapping/fr "wikilink")", et que vous
    êtes maintenant familiarisé avec l'interface de MapTool, que vous
    savez comment créer une nouvelle carte, sauvegarder des fichiers et
    placer des Pions sur la carte.
2.  Vous devez également avoir lu "[Introduction à la gestion des Pions
    (fr)](Introduction_to_Tokens/fr "wikilink")", et avoir les
    connaissances de base pour manipuler les Pions, examiner leurs
    propriétés et tout ce qui s'y rapporte.
3.  Enfin, puisque les Macros sont intimement liées aux propriétés des
    Pions, vous devez avoir lu les étapes qui y sont consacrées dans
    "[Introduction aux Propriétés
    (fr)](Introduction_to_Properties/fr "wikilink")"et vous devez avoir
    créé un nouveau fichier de campagne basé sur [un exemple de règles
    de jeu](Sample_Ruleset "wikilink") créé pour permettre aux nouveaux
    joueurs de se familiariser avec MapTool. Si vous n'avez pas lu ce
    guide, faites-le - cela rendra la plupart des exemples suivants
    *beaucoup* plus compréhensible \!

## Conventions utilisées pour ce Guide

Le maximum sera fait pour conserver le langage et la terminologie les
plus cohérents possible. Dans ce guide :

  - **Macro** renvoie à une collection de commandes qui sont groupées
    ensemble pour exécuter automatiquement une tache.
  - **Commande Macro** renvoie à toute commande individuelle
    particulière ou à toute fonction utilisée à *l'intérieur* d'une
    Macro.
  - **Le langage de Macro** représente l'ensemble des commandes,
    fonctions et opérations que vous pouvez utiliser quand vous écrivez
    une Macro. Vous pouvez consulter la liste des fonctions disponibles
    [ici](:Category:Macro_Function "wikilink").

De plus, Bien qu'il soit possible pour une Macro d'interagir avec une
autre (on dit dans ce cas qu'elle "appelle" une autre Macro), dans ce
guide, nous aborderons uniquement les Macros accessibles depuis l'onglet
Macro et qui peuvent affecter uniquement les Pions auxquels elles sont
associées.

## Dans quels cas les utiliser ?

Il n'y a aucune obligation d'utiliser des Macros pour pouvoir utiliser
MapTool. En effet, la fonction principale de MapTool est de partager une
carte avec des amis et de pouvoir jouer à des jeux ( lisez [Introduction
à la création de carte (fr)](Introduction_to_Mapping/fr "wikilink") et
[Introduction à l'hébergement de partie
(fr)](Introduction_to_Game_Hosting/fr "wikilink") pour apprendre comment
créer et partager des cartes avec votre groupe de joueurs), et MapTool
fournit tout ce dont vous avez besoin pour cela : des cartes, des pions
et un système de discussion (*chat*) pour vous permettre de dialoguer ou
effectuer des jet de dés.

Toutefois, les possibilités sont beaucoup plus importantes, pour peu que
vous souhaitiez en apprendre un petit plus sur les capacités des Macros.
Par exemple, si vous voulez avoir un bouton qui en cliquant dessus vous
permettra de lancer 1D20 et d'ajouter le modificateur automatiquement,
c'est possible en créant une Macro pour cela. Si vous voulez modifier
les points de vie après une blessure, vous pouvez écrire une Macro pour
le faire. Ce guide va vous montrer comment.

## Où trouver ces "Macros?"

Les Macros sont intégrées à différentes parties de l'interface de
MapTool et aux objets à l'intérieur. Il ressort qu'une Macro peut
"résider" à trois endroits :

### Macros de Pion

L'endroit le plus naturel où trouver une Macro est un
[Pion](Introduction_to_Tokens "wikilink"). Les Macros de Pion sont liées
au Pion sur lequel elles ont été créées le resteront tant que vous les y
laisserez.

Les Macros de Pion (''Token macros '') sont directement accessibles
uniquement par les propriétaires du Pion, donc si vous ne possédez pas
le Pion, vous ne pourrez pas interagir (ou même voir) les boutons de ces
Macros.

### Macros de Campagne

Les Macros de Campagne ne sont pas liées à un Pion en particulier, mais
à la campagne toute entière. Ces Macros fonctionnent pratiquement comme
une Macro de Pion, excepté ceci :

1.  Vous n'avez pas besoin de sélectionner. un Pion pour voir les Macros
2.  N'importe qui peut y accéder et les exécuter.

Les Macros de campagne sont particulièrement utiles au MJ et aux joueurs
pour gérer des fonctions communes - en fait, si vous mettez en place une
tache commune en tant que Macro de campagne, vous n'avez besoin que
d'avoir une seule copie de celle-ci (au lieu d'une copie pour chaque
Pion qui en aurait besoin).

### Macros Globales

Les Macros globales se sont liées ni aux Pions, ni à une campagne - en
fait, elles sont liées à votre exemplaire de MapTool. Ces Macros ne sont
visibles de personne d'autre que vous, que vous soyez joueur ou MJ.

C'est un bon endroit pour ranger les Macros exécutant des tâches que
vous ne voulez pas que les autres voient - comme des informations que
vous voudriez montrer uniquement au moment où vous l'avez décidé; ou des
tâches que vous voulez faire faire à vos PNJ mais que vous ne voulez pas
que les PJ puissent faire.

## Les fenetres de Macros

![Macro-panels.jpg](Macro-panels.jpg "Macro-panels.jpg")
![Tabbed-panels.jpg](Tabbed-panels.jpg "Tabbed-panels.jpg")

Avec toutes ces discussions autour des Macros et de leur localisation
(plus spécialement des boutons de Macros), vous vous demandez
probablement où trouver ces boutons ? Vous les trouverez dans une des
quatre fenêtres de Macros qui sont disponibles dans MapTool. Si vous ne
trouvez pas ces fenêtres ou qu'une d'entre elles est manquante, vous
pouvez les faire apparaître en allant dans le menu **Windows**
(Fenêtres) et en cochant les fenêtres suivantes en fonction de vos
besoins :

  - Selection (Sélection)
  - Impersonated (Interprétation)
  - Campaign (Campagne)
  - Global (Globale)

Vous devriez voir ces fenêtres apparaître dans MapTool si elle n'étaient
pas déjà là. Si vous regardez les copies d'écran sur la droite, vous
verrez que la fenêtre Globale est remplie avec un tas de boutons. Chacun
d'eux exécute une Macro; les boutons apparaissent lorsque vous créez une
nouvelle Macro

### Fenêtre Sélection et Interprétation

Il y a deux fenêtres qui traitent directement des Macros des Pions :
Sélection (*Selection* et *Impersonated*)

La fenêtre Sélection montre les boutons de toutes les Macros
actuellement associées au Pion que vous avez sélectionné. Chaque bouton
lance une série particulière de commandes Macro.

La fenêtre Interprétation (*Impersonated*) montre les macros du Pion que
vous avez choisi *d'interpréter*. Interpréter un Pion est un moyen de
faire comme si vous étiez le Pion - lorsque vous discutez, le texte
apparaît comme s'il avait été dit par le Pion. Il est possible
d'interpréter un Pion tout en en sélectionnant un autre, alors faites
attention à la fenêtre que vous êtes en train d'utiliser \!

### La fenêtre Campagne (*Campaign*)

Cette fenêtre affiche toutes les Macros actuellement disponibles pour la
campagne. Souvenez-vous qu'elles sont visibles de tout le monde.

### La fenêtre Globale

Cette fenêtre contient les Macros globales que vous avez créées.
Souvenez-vous qu'elles ne sont visibles *que de vous*.

## Ecrire des Macros

![Camp-panel-nomacros.png](Camp-panel-nomacros.png
"Camp-panel-nomacros.png")

![Camp-panel-rcaddnew.png](Camp-panel-rcaddnew.png
"Camp-panel-rcaddnew.png")

La création de Macros se fait en trois étapes (même si chaque étape peut
en contenir une multitude\!) :

1\. Faites un clic-droit sur la fenêtre où vous voulez voir la Macro
apparaître (la fenêtre Pion (*Token*), Campagne (*Campaign*) ou Globale)
et choisissez **Add New Macro** (*Ajouter une nouvelle Macro*). Un
bouton gris avec l'étiquette **(new)** apparaîtra.

2\. Faites un clic-droit sur le bouton et choisissez **Edit** (*Editer*)

3\. Saisissez du code Macro, attribuez lui un nom et cliquez sur **OK**.
Bien \! Vous avez créé une Macro

Un instant... que voulez vous dire par "code Macro" ?

Comme indiqué précédemment, ces trois étapes peuvent contenir une
quantité énorme de détails, étapes, astuces, réussites, échecs,
frustrations et parfois hurlements et grincements de dents. Donc, nous
allons reculer d'une étape regarder quelque Macros très simples avec une
approche très progressive. Si vous voulez voir quelques Macros plus
complexes, il en existe des tonnes à lire à travers les tutoriels et les
comment-faire sur ce wiki. Pour l'instant, nous nous contenterons
d'écrire quelque Macros très simples mais très utiles.

### Le Jet d'Initiative

![Camp-panel-newbutton.png](Camp-panel-newbutton.png
"Camp-panel-newbutton.png")

![Camp-panel-rceditbutton.png](Camp-panel-rceditbutton.png
"Camp-panel-rceditbutton.png")

![Macro-editor-examplestring.png](Macro-editor-examplestring.png
"Macro-editor-examplestring.png")

![Camp-panel-exbutton.png](Camp-panel-exbutton.png
"Camp-panel-exbutton.png")

Les plus simples des Macros ne sont rien de plus que du texte qui est
re-dirigée vers la fenêtre de discussion (*Chat*). En effet, une Macro
contenant du texte (en fait toutes les Macros) envoie juste une ligne de
commande à la fenêtre de discussion où elle est lue puis interprétée. La
plupart des langages de programmation commencent avec le classique
programme "Hello World\!", donc ce guide ne fera pas cela. A la place,
essayons de faire quelque chose de plus "rôlistique" : créons le
redoutable message "Effectuez votre jet d'initiative \!"

1\. Sélectionnez la fenêtre Campagne.

2\. Faites un clic-droit dessus et choisissez **Add New Macro**.

3\. Faites un clic-droit sur la nouvelle Macro et cliquez sur **Edit**.

4\. Dans le champ **Label** (*Etiquette*), saisissez "Jet d'initiative"

5\. Laissez les champs **Group** et **Sort Prefix** vide.

6\. Dans le champ **Command**, tapez

> `Effectuez votre jet d'initiative !`

7\. Cliquez sur **OK**.

8\. Vous voyez maintenant que votre bouton a changé - il est maintenant
écrit dessus : **Jet d'initiative**, et lorsque vous cliquez dessus, ô
merveilles, le texte "Effectuez votre jet d'initiative \!" apparaît dans
la fenêtre de discussion.

Ceci représente la base de l'écriture de Macros : vous saisissez du
texte dans la Macro, puis, lorsque vous appuyez sur le bouton, ce texte
est lu par l'analyseur syntaxique et envoyé à la fenêtre de discussion.

### Toujours plus intéressant

Le "Jet d'initiative", tout effrayant qu'il soit lorsqu'il est demandé
par votre MJ, n'est par ce qu'on peut trouver de plus intéressant en
terme de Macro. Vous vous êtes probablement demandé "pourquoi ne pas le
taper tout simplement dans la fenêtre de discussion ?" Et la réponse est
"vous auriez sûrement mieux fait \!" Alors essayons de faire quelque
chose de plus intéressant, que nous voudrions garder au premier plan en
utilisant MapTool (après tout, nous ne sommes pas là pour écrire des
programmes - nous sommes ici pour jouer) : nous allons ajouter quelques
*commandes Macro*, en complément du simple texte. Les commandes Macro
sont des instruction spéciales qui, lorsqu'elles sont lues par
l'analyseur syntaxique, lui demandent de faire des choses en plus que
simplement afficher du texte dans la fenêtre de discussion, comme lancer
des dés ou calculer des valeurs.

Les commandes Macro doivent *toujours* être encadrées par des crochets
(\[*commande Macro*\]) ou des accolades ({*commande Macro*}). Les
encadrer de cette manière indique à l'analyseur syntaxique qu'une
commande est en train d'arriver - autrement, il traitera la commande
comme du simple texte et l'affichera dans la fenêtre de discussion.

#### Quelques jets de dés

![Macro-editor-rolldice.png](Macro-editor-rolldice.png
"Macro-editor-rolldice.png")

Ceci est une Macro simple qui va automatiquement lancer un dé 20 et
ajouter le nombre 7 à ce jet, avant d'afficher l'ensemble dans la
fenêtre de discussion.

1\. Créez une nouvelle Macro (à l'endroit que vous voulez - sur un Pion,
dans la fenêtre Campagne ou globale), et ouvrez l'éditeur de Macro
(souvenez vous que pour faire cela, vous devez faire un clic-droit surle
bouton **(new)**.

2\. Dans le champ **Label** donnez le nom "jet d'attaque" ou "jet de
dés".

3\. Dans le champ **Command**, entrez:

> `Mon jet d'attaque est : [1d20+7]!`

4\. Cliquez sur **OK**. Vous devriez voir un bouton avec le nom que vous
avez choisi précédemment. Quand vous cliquez dessus, vous voyez
apparaître quelque chose comme ceci dans la fenêtre de discussion :

> Chris: Mon jet d'attaque est :
> <font style="background-color:lightgray;">8</font>\!

Ce qui s'est passé est que MapTool a lu le contenu de la Macro et quand
il est arrive à la partie **\[1d20+7\]**, il a su qu'il devait :

1.  Lancer 1 dé à 20 faces (ou plus exactement choisir un nombre
    aléatoire entre 1 et 20),
2.  Ajouter 7 à ce résultat,
3.  Afficher le résultat dans la fenêtre de Discussion correctement
    placé après le texte.

Vous avez remarqué que le nombre 8 a un fond gris. Si vous laissez la
souris au-dessus un moment, une info-bulle apparaîtra expliquant comment
ce chiffre a été obtenu. Dans notre cas, j'ai obtenu 1 sur le dé 20 (un
échec critique \!). Si vous ne pouvez pas voir l'info-bulle, vérifiez
vos réglages de [discussion](MapTool_Preferences#Chat "wikilink") et
choisissez **Use ToolTips for Inline Rolls** (*utiliser les info-bulles
pour les jets en interne*).

De plus, vous ne verrez probablement pas le mot "Chris", à moins que
vous ne vous appeliez également Chris. Cette partie de la fenêtre de
discussion est juste pour indiquer qui "a dit" ce morceau de texte en
particulier. Si c'était un Pion, vous auriez eu le nom du Pion avec son
image au lieu de l'ennuyeux "Chris".

#### Autre chose que des nombres ?

Les commandes Macro peuvent fonctionner avec des nombres et avec du
texte -- vous pouvez manipuler les *lignes* (des collections de
caractères alphanumériques) de la même façon grâce au langage de Macros
de MapTool. Disons que pour l'occasion, vous voulez effectuer un jet de
dé, mais vous voulez aussi que le nom de votre cible soit affiché dans
la fenêtre de discussion.

![Macro-editor-basiccommands.png](Macro-editor-basiccommands.png
"Macro-editor-basiccommands.png")

![Prompt-undeclared-variable.png](Prompt-undeclared-variable.png
"Prompt-undeclared-variable.png")

Vous pouvez ainsi modifier votre Macro *Jet de dés* de la manière
suivante :

> `J'ai obtenu [1d20+7] à mon jet d'attaque contre [cible] !`

Lorsque vous lancez cette Macro, une boite de dialogue apparaît vous
demandant : "Value For cible." Que s'est-il passé ?

Et bien, quand MapTool a analysé la Macro, il a vu une commande macro
disant simplement **\[cible\]**. MapTool part du principe que tout mot
entre crochet et qui n'est pas reconnu par l'analyseur syntaxique comme
partie d'une commande macro, représente une variable (en d'autres
termes, sa valeur peut changer).

MapTool a aussi remarqué que nulle part dans la Macro, il n'était
précisé à quoi était égale la variable *cible*. Les langages de
programmation appelle ce genre de situation des *variables non
déclarées* (vous n'avez jamais précisé à quoi elle était égale).
Puisque MapTool n'a aucun moyen de savoir ce que *cible* pourrait être,
il vous le demande \! Si vous tapez un nom, un nombre ou tout ce qui
vous passe par la tête dans cette boite de dialogue, MapTool prendra
cette information et l'attribuera à la variable *cible*, avant de
poursuivre le déroulement de la Macro.

Continuez et saisissez "cet orque désobligeant" (vous pouvez retirer les
guillemets) dans cette boite de dialogue, et cliquez sur **OK**. vous
devriez obtenir dans la fenetre de discussion quelque chose comme :

\<blockquote style="border:1px solid gray;" width:50%;\>Chris: J'ai
obtenu <font style="background-color:lightgray;">23</font> à mon jet
d'attaque contre <font style="background-color:lightgray;">cet orque
désobligeant</font> \!

</blockquote>

Encore une fois, l'analyseur syntaxique parcourt le texte et les
commandes macro que vous avez placés dans la Macro, et à la place
indiquée par les commandes macro (entre crochet), MapTool substitue le
résultat approprié.

## Utiliser des Variables dans une Macro

Nous avons vu une paire d'exemples avec quelques utilisations de
variables (comme  dans l'exemple précédent) dans une Macro, mais nous
n'avons pas encore été très loin dans cette matière. Pourtant, les
variables et leurs utilisations représentent vraiment le cœur de
l'écriture de macro. Il est donc impossible de passer outre ce sujet.

### Qu'est-ce qu'une Variable?

Si vous avez déjà fait de la programmation, vous devez déjà savoir tout
cela, mais si vous venez juste de vous lancer dedans, une définition
simple de *variable* en terme de langage de Macro est :

  -
    **Une variable est une valeur qui peut changer et qui est basée sur
    une propriété d'un Pion, sur un calcul ou une autre commande
    Macro**.

Puisque la valeur d'une variable n'est pas fixe, nous devons lui donner
un nom (on dit qu'on *déclare* la variable pour que le système sache
qu'elle existe) de manière à pouvoir l'utiliser. Ensuite, quel que soit
le moment où nous aurons besoin de la valeur de la variable *à ce
moment*, nous n'aurons qu'à placer son nom dans une commande Macro
(entre crochet), et MapTool remplacera la valeur adéquate à ce moment
là.

Pensez de cette manière : si le résultat d'un jet de dés peut être
n'importe quoi entre 1 et 20, vous pouvez par exemple dire qu'un
résultat particulier a été un 19, un 2, un 7 ou n'importe quoi. Donc, à
la place vous pourriez dire "quel que soit le résultat du jet de dés,
affiche ce résultat-ci \!"

  -
    **Remarque**: cela ne signifie pas que MapTool va substituer la
    valeur *correcte* en fonction de *vos* besoins; cela signifie qu'il
    va remplacer la valeur correspondant à la variable par une autre
    quand vous le lui demanderez. Donc si votre Macro contient une
    erreur, le résultat risque d'être faux - mais MapTool n'a aucun
    moyen de savoir si un résultat est faux, il ne fait qu'exécuter ce
    que vous lui demander.

### Affectation de Variables

Lorsque vous voulez donner à une variable une valeur donnée, cela est
appelé "affecter" une valeur à la variable. "L'opérateur d'affectation"
dans MapTool est le signe égal ( = ). Cela semble facile, mais cela
signifie juste que vous utilisez le signe égal pour dire à MapTool
qu'une certaine variable a une valeur particulière. Un exemple
d'affectation de variables est :

>
>
> ``` mtmacro
> [h:mesPV = 30]
> ```

Comme vous l'avez déjà deviné, ce que fait cette ligne est :

1.  déclarer l'existence d'une variable appelée ,
2.  assigner la valeur  dans cette variable.

Il s'agit ici d'une affectation de variable à la racine - *une variable*
égale *une valeur*.

Vous vous souvenez de l'exemple où vous était demandé de saisir le nom
de la cible que vous utilisiez comme variable sans lui avoir affecté de
valeur. Vous aviez déclaré l'existence de la variable, mais sans lui
assigner de valeur, en conséquence, MapTool vous demandait cette valeur.
Ce qu'il faut retenir ici, c'est qu'une Macro utilisant des variables a
besoin de connaître les valeurs de celles-ci pour pouvoir se terminer.
Il n'est cependant pas toujours nécessaire de les affecter auparavant,
quelquefois il est indispensable de demander à l'utilisateur quel
paramètre utiliser.

### Comment déclarer une affectation

MapTool traite chaque commande Macro à l'intérieur d'une Macro dans
l'ordre, en commençant par le haut. En conséquence, à moins que vous ne
vouliez que MapTool vous demande la valeur de toutes les variables que
vous projetez d'utiliser, vous devrez affecter des valeurs à ces
variables avant *d'utiliser* la Macro \! Par exemple dans la commande
Macro suivante :

A moins que vous ne vouliez que MapTool n'ouvre des boites de dialogue
pour vous demander la valeur de , , et , vous devrez vous assurer de
leur avoir donné une valeur *avant* que MapTool n'exécute cette ligne.
Peut-être avec quelque chose comme ceci :

>
>
> ``` mtmacro
> [h:Dommages = 1d6+4]
> [h:TypedeDommagese = "feu"]
> [h:PVrestants = 30 - Dommages]
> Ce coup inflige [Dommages] points de dégâts de [TypedeDommages], vous laissant avec [PVrestants] points de vie!
> ```

Comme vous pouvez le voir, nous avons fait trois affectations de
variables avant qu'elles ne soient utilisées dans la ligne gérant le
coup reçu. Nous avons affecté la valeur d'un jet de dés à six face plus
quatre à la variable , la valeur  à la variable , et le résultat de
l'opération  à la variable .

si vous regardez attentivement, vous verrez que nous avons même utilisé
une variable pour affecter une valeur dans une autre variable : la
valeur de la variable  est utilisée quand nous affectons une valeur à la
variable  - donc, des variables peuvent être utilisées pour définir ou
manipuler d'autres variables.

### Règles concernant les Variables

Il y a deux règles à se souvenir quand on crée une variable :

1.  aucun espace : les noms de variables ne peuvent contenir d'espace,
    ainsi vous ne pouvez utiliser la variable : , mais plutôt choisir
    celle-ci : .
2.  Variables spéciales : il existe plusieurs "variables spéciales" que
    MapTool se réserve - ce qui signifie que vous ne pouvez pas les
    utiliser pour autre chose que ce qui a déjà été prévu par MapTool.
    En général, vous pouvez les reconnaître facilement car elles ont un
    point dans leur nom, comme  ou . Ces variables spéciales seront
    traitées dans un autre guide, mais pour l'instant vous devez juste
    savoir que vous ne pouvez pas créer de variable avec un nom se
    trouvant dans la [liste
    suivante](:Category:Special_Variable "wikilink").

## Mettre à niveau notre jeu

Les exemples précédents montre des utilisations basiques des Macros :
afficher du texte dans la fenêtre de discussion lorsqu'on clique sur un
bouton, effectuer un jet de dés simple à l'intérieur d'une Macro et même
récupérer des infos de la part de l'utilisateur pour terminer une Macro.

Allons maintenant un peu plus loin : nous allons jouer avec les options
de mise en page, modifier les valeurs des propriétés des Pions et jeter
un œil à quelques boucles très simple (lorsque vous faites et refaites
quelque chose) et au embranchement (faire des choses différentes en
fonction des conditions ou de la situation).

### Options de mise en page

Le résultat d'une Macro (tout comme n'importe quelle ligne dans la
fenêtre de discussion) peut être formaté en utilisant les balises
[HTML](http://www.codeshttp.com/baliseh.htm) de base, de même que
quelques options propres à MapTool. Nous examinerons brièvement la
partie HTML, pour observer quelques [options d'affichage de jet de
dés](:Category:Display_Roll_Option "wikilink").

#### Jets de dés explicites

Dans MapTool 1.3.b54, la manière habituelle d'afficher un résultat d'un
jet de dés ou d'un calcul consiste à n'afficher que le total ou le
résultat final. Ainsi si vous lancez 1D20+7, seul le résultat final
apparaître dans la fenêtre de discussion, avec une info-bulle (si vous
passez la souris sur le résultat) affichant le détail du calcul.

Si vous le souhaitez, vous pouvez demander à MapTool de décomposer le
résultat du calcul également, en utilisant une option de formatage des
jets de dés - appelée **Jets de dés explicites**.

Pensez à ces options de formatage comme à un interrupteur qui dirait à
MapTool comment s'occuper du résultat d'un jet de dés. Pour obtenir la
forme explicite, éditez votre Macro sur le jet d'attaque comme ceci :

> `J'ai obtenu [e:1d20+7] à mon jet d'attaque contre [cible] !`

Lorsque vous lancerez la Macro plus tard, vous obtiendrez dans la
fenêtre de discussion :

> J'ai obtenu <font style="background-color:lightgray; ">« 1d20+7 = 1 +
> 7 = 8 »</font> à mon jet d'attaque contre
> <font style="background-color:lightgray; color:blue;">cet orque
> désobligeant</font> \!

Vous pouvez ainsi voir le détail du résultat de votre jet de dés.

#### Affichage exclusif du résultat

A l'inverse, que se passe-t-il si vous ne voulez pas que qui que ce soit
puisse voir le détail d'un résultat (par exemple, si vous ne voulez pas
que vos joueurs puissent en déduire la puissance ou les faiblesses de
leur adversaire). Pour cela choisissez l'option **d'affichage exclusif
du résultat**. Éditez votre macro de la manière suivante :

> `J'ai obtenu [r:1d20+7] à mon jet d'attaque contre [cible] !`

Et le résultat apparaîtra comme ceci :

> J'ai obtenu 11 à mon jet d'attaque contre
> <font style="background-color:lightgray">cet orque désobligeant</font>
> \!

Remarquez qu'il n'y a plus de fond gris derrière le nombre 11, et
qu'aucune info-bulle n'apparaît lorsque vous passez la souris sur ce
dernier. L'affichage exclusif ne fournit que du texte standard. Si vous
voulez également vous débarrasser sur sur-lignage entourant les mots
"cet orques désobligeant", vous n'avez qu'à éditer la Macro comme suit :

> `J'ai obtenu [r:1d20+7] à mon jet d'attaque contre [r:cible] !`

Et le nom de la cible s'affichera sans sur-lignage particulier.

#### Résultats cachés

Quelquefois, vous ne voulez pas du tout afficher le résultat d'une Macro
- peut-être avez vous juste besoin d'afficher du texte et de faire les
calcul en tâche de fond, sans rien révéler. Dans ce cas, vous devriez
remplacer les "r:" ou les "e:" dans les exemples précédents par des
"h:", comme dans l'exemple suivant :

> `[h:PVmax = 30]`
> `[h:EnPeril =PVmax / 2]`
> `Je suis en péril si j'ai moins de [EnPeril] points de vie.`

L'exemple ci-dessus est caractéristique de l'utilité du **résultat
caché**. Dans cette Macro, nous faisons trois choses :

1.  régler la variable *PVmax* à 30, mais demander à MapTool de ne pas
    afficher le résultat,
2.  attribuer à la valeur de la variable *EnPeril* la moitié de la
    valeur *PVmax*, mais demander là aussi à MapTool de ne pas afficher
    le résultat,
3.  afficher du texte en insérant la valeur *EnPeril* à l'endroit
    approprié.

Si vous lancez cette Macro, vous obtiendrez :

> Je suis en péril si j'ai moins de
> <font style="background-color:lightgray;">15</font> points de vie.

En revanche, si vous *n'utilisez pas* la fonction **résultat caché**, la
sortie ressemblera à :

> <font style="background-color:lightgray;">30</font>
> <font style="background-color:lightgray">15</font>Je suis en péril si
> j'ai moins de <font style="background-color:lightgray;">15</font>
> points de vie.

Les nombres en plus proviennent des deux déclarations de variables
*avant* la ligne de texte. Vous n'avez aucun intérêt à montrer ces
choses, alors il est bien pratique de pouvoir les cacher.

#### Formatage HTML

Les Macros dans MapTool supportent les balises HTML de base. Disons que
vous voulez afficher le nom de votre cible sur une ligne, le résultat du
jet d'attaque sur la suivante et enfin le résultat du jet de dommages
éventuels sur la troisième. Vous pourriez éditer votre Macro de cette
manière :

> `J'ai fait un jet d'attaque !<br>`
> `<b>Cible </b>: [r:cible]<br>`
> `<b>Attaque </b>: [1d20+7]<br>`
> `<b>Dommages </b>: [1d8+5]`

En lançant la Macro, vous obtiendrez :

> J'ai fait un jet d'attaque \!
> '''Cible **: cet orque désobligeant
> **Attaque **: <font style="background-color:lightgray;">15</font>
> **Dommages ''': <font style="background-color:lightgray;">7</font>

Il s'agit simplement d'une mise en page - vous pourriez envoyer le
résultat dans une table, changer les fontes, les couleurs de fond, les
tailles de polices... de nombreuses options sont possibles.

**REMARQUE**: si vous êtes déjà familier avec le HTML, notez bien que
MapTool supporte le format HTML 3.2 - ainsi des balises telles que
\<br\> ne doivent pas être *fermées* - utilisez \<br\> au lieu de
\<br/\>. De plus, MapTool supporte partielement les feuilles de style en
cascade au standard CSS 1. Pour plus d'informations sur les balises CSS
supportées consultez cette [partie](Supported_CSS_Styles "wikilink").

### Utiliser les Propriétés des Pions

Ainsi, nous savons manipuler quelques variables définies préalablement,
ou que MapTool demande à chaque fois que nous lancons une Macro. Nous
savons en outre mettre en forme une attaque en listant la cible, le jet
d'attaque et les eventuels dommages. Pourtant, nous devons encore coder
en dur les valeurs dans les Macro ou laisser l'utilisateur les insérer
lui-meme chaque fois que c'est nécessaire. Puisque les personnages de
JDR ne sont pas tous les memes, nous devons imaginer un moyen
d'automatiser certains de ces nombres, ainsi, nous pouvons :

1.  créer une Macro que differentes personnes ou personnages peuvent
    utiliser
2.  Réduire au strict minimum les différentes saisies au clavier \!

Comme indiqué dans la section [Introduction to
Tokens/fr](Introduction_to_Tokens/fr "wikilink"), tous les Pions
emportent avec eux leur propre "feuille de personnage" à l'intérieur de
l'onglet *properties*. Ces propriétés peuvent etre *référencées* par une
macro - vous pouvez ainsi par exemple écrire une macro disant "lance
1D20, et ajoute la dextérité de mon personnage au résultat." Je suis sur
que vous voyez à quel point cela peut etre utile.

#### Mise en place de quelques exemples de Propriétés

Of course, for token properties to work, we've got to set them up. It's
a good thing you read the [Introduction to
Properties](Introduction_to_Properties "wikilink") and created a
campaign file for the MapTool RPG [Sample
Ruleset](Sample_Ruleset "wikilink")\!

The first step is to open up the **MTRPG.cmpgn** file (or whatever name
you saved it as), and drag a token onto the map (if you don't already
have one on there). If you've got no idea what that means, check out the
[Introduction to Mapping](Introduction_to_Mapping "wikilink") to learn
about making maps and putting tokens on them. Now, follow these steps:

1\. Double click on a token to open the **Edit Token** dialog.

2\. Go to the tab marked **Properties**.

3\. You'll see a spreadsheet-style list of all the properties in the
token that you can edit directly (tokens have other properties that can
be edited only with macros, but for now, let's not worry about them\!).
You should see (if you're using the MTRPG.cmpgn file we set up in
[Introduction to Properties](Introduction_to_Properties "wikilink")):

> <tt>
>
> `*Strength:1`
> ` *Dexterity:1`
> ` *Intelligence:1`
> ` *Endurance:1`
> ` *HitPoints(HP):{Endurance * 6}`
> ` *Armor(AR)`
> ` *Movement(MV):{Dexterity}`
> </tt>

4\. Click in the cell next to Strength. A cursor will appear, showing
that you can type in that cell. Enter a number in that cell as the
token's Strength value. I'm going to use 6.

5\. Repeat step 4 for Dexterity, Intelligence, and Endurance, choosing
whatever number you like (I'm going to use 3, 2, and 6, respectively).
Remember that *HitPoints* and *Movement* will be automatically
calculated\!

6\. Click **OK**. You have just manually updated the token's properties.
If you double-click on the token, and look at those properties again,
you'll see that the numbers you entered are remembered.

You'll also see that now, when you hover your mouse over the token, a
little popup appears in the lower right corner of the map, showing the
values for the properties you've entered. This popup is called the
**Statsheet**, and is a quick way to look at the token's properties -
it's basically a convenient quick-reference "character sheet."

#### Referencing a Token Property in a Macro

Now that we've configured some token properties, let's use them in a
macro. For our first macro, we're going to roll 1d20, and instead of
adding 7, we're going to add the token's **Strength**.

1\. Open up your Attack Roll macro.

2\. In the lower left corner, make sure the box **Apply to Selected
Tokens** is checked (otherwise, the macro won't know which token's
Strength to use\!)

3\. Edit your macro to look like this:

> `I make an attack roll!<br>`
> `<b>Target</b>: [r:target]<br>`
> `<b>Attack</b>: [1d20+Strength]<br>`
> `<b>Damage</b>: [1d8+5]`

You'll note I replaced the 7 with the word "Strength." Since *Strength*
is not in quotes, MapTool will know that you mean it to be a variable,
and it will look on the *current token* (that is, the token that is
selected) for a property called *Strength*. If it doesn't find it (or if
the property has never been set), it will prompt you for it (just like
you were prompted for the value of *target*). If it *does* find it,
MapTool will put the value of *Strength* into the macro when it runs.

4\. Select your token, and run the macro by clicking the button. The
output will look something like:

> I make an attack roll\!
> Target: Nasty Orcses
> Attack: <font style="background-color:lightgray;">27</font>
> Damage: <font style="background-color:lightgray;">6</font>

The important thing to note is that if you hover over the attack roll
result, the tooltip will now say something like *« 1d20 + Strength = 17
+ 10 »* indicating that the value being plugged in to the dice roll is
the property *Strength*.

#### Changing a Property with a Macro

Token properties can also be changed using a macro. Suppose we want to
reduce the token's hit points after an enemy hit the character. You can
manually edit the token and change the value in the *HP* property, or,
you can create a macro that subtracts the amount of damage from the
value of *HP*. Here's how:

1\. Create a new macro on the **Campaign** panel.

2\. In the **Label** field, enter "Damage".

3\. In the **Command** field, enter:

> `Aarrgh! I'm hit! I have [HitPoints = HitPoints - damage] hit points
> left.`

4\. Check the box **Apply to Selected Tokens** (in the lower left
corner).

5\. Click **OK**. When you run the macro, you will be prompted for a
value to put in the variable *damage*. I put in the number 7. The output
will look something like this:

> Aarrgh\! I'm hit\! I have
> <font style="background-color:lightgray;">23</font> hit points left

And, if you double click on the token, you will see that the property
*HP* is now 23. What this macro did was:

1.  Prompt the user for a value for *damage* (in this example, I entered
    7)
2.  Retrieve the value of *HitPoints* from the token (in this example,
    the value is 30, because it is equal to Endurance \* 6)
3.  Subtract the value of *damage* from the value of *HitPoints* (30 -
    7, resulting in 23)
4.  Set the value of *HitPoints* (originally 30) to the newly calculated
    total (23)
5.  Output the text and the new value of *HitPoints* to chat

### String Concatenation

An essential ability to master when writing macros is the ability to
assemble *strings* - that is, collections of alphanumeric characters
that are then manipulated or sent to chat. Frequently, you'll want to
construct a string from some text that is always the same ("hardcoded"
text) and text that can change (text that is the value of a variable, in
other words). The construction of a string is often called
"concatenation," but it just means "building a long string out of
multiple short pieces."

There are two ways to do this in a macro - outside of a macro command,
and inside of a macro command.

#### Outside of a Command

The basic way a macro works is this:

1.  The parser reads through the whole macro, and separates the macro
    commands from the plain text
2.  The parser diverts those macro commands to the appropriate places to
    be processed (so, numbers are added up, dice are rolled, etc.)
3.  The processed commands are sent *back* to the parser, which
    substitutes the *results* of those commands in the place where each
    command was.
4.  The whole mess - plain text, and the results of the commands (now
    sitting in place of the actual commands) is sent to the chat window.

So, when you want to display the result of a command along with some
text (for instance, you want to print the word "Attack:" and then next
to it print the result of a 1d20 roll) in a macro, the easiest way is to
just insert a command in the right place in your text, like so:

>
>
> ``` mtmacro
> Attack: [1d20]
> ```

The parser will read that whole thing, send off the command  to be
processed, and when it gets that result back, plug it in in place of the
command, and send it off to chat. The result will be something like
"Attack: 17."

That's the most straightforward way to send text to chat - just put the
variables you want displayed in the right place in the text, and they
will be shown in the chat window.

#### Inside of a Macro Command

Sometimes, though, you need to use strings *inside* of the square
brackets. In that case, putting them together is a little different.
First of all, within square brackets, you need to use single or double
quotes to surround something you want to be treated as a string.
Otherwise, MapTool will think you want each word to be a variable\! For
example:

**Correct String**

>
>
> ``` mtmacro
> [string = "This is a string"]
> ```

**Incorrect String**

>
>
> ``` mtmacro
> [string = This is a string]
> ```

Remember - outside of square brackets, no need for quotes. Inside?
QUOTES.

So what if we need to build up a string dynamically? That is, what if we
need to make a string that is partly "hardcoded," and partly based on
user input? You can't guess what the user is going to say, so you can't
write that part ahead of time. What you *can* do is *concatenate* the
user input into your hardcoded string. The way to do that is to use the
plus sign (**+**), which - when it's used with *strings* - will piece
them together into a long string.

Here's an example: suppose we want the user to enter the name of a
skill, and we then want to put that skill name into an existing,
hardcoded string, which will be stored in another variable. You would do
that like this:

>
>
> ``` mtmacro numberLines
> [h:existingString = "The skill name you entered is "]
> [h:concatString = existingString+skill+"."]
> [r:concatString]
> ```

What happens here is this:

  - Line 1 sets the "hardcoded" portion of the output
  - Line 2 sets the concatenated string -  to equal the value of  *plus*
    the value of  (which MapTool will prompt for). However, in this
    case, since MapTool knows that  is a string, it will not try to add
    them mathematically, but just append the value of  after the value
    of . To be grammatically correct, we concatenate another little
    string on the end, this time, the period. Remember - strings inside
    square brackets need to be in quotes (but variable names, of course,
    do not\!)
  - Line 3 displays the final value of , after  has been appended to it.
    The output will look something like:

> The skill name you entered is Archery.

That's a very simple example, but it illustrates the essence of
constructing strings - you "add" them together with a plus sign.

## Where do We Go From Here?

This guide barely brushes the surface of the full potential of the macro
language in MapTool. However, using just the basic techniques shown
here, you can create a lot of very handy, convenient macros to make
playing your game easier and more fun. In future guides, I'll cover more
advanced macro commands and techniques. {{\#customtitle:Introduction à
l'écriture de Macro|Introduction à l'écriture de Macro}}

[Category:MapTool](Category:MapTool "wikilink")
[Category:Tutorial](Category:Tutorial "wikilink")