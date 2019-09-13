Qu’est-ce qu’un dépôt ?
-----------------------

Un dépôt de campagne est un ensemble de fichiers (principalement des images) qui sont utilisés dans une campagne. En stockant ce dépôt ailleurs que sur la machine du MJ, vous pouvez rendre plus rapide le téléchargement des images par vos joueurs et rendre ainsi plus agréable le déroulement de la partie.

Vous devez disposer d’un espace Internet externe pour utiliser convenablement un dépôt. De nombeux fournisseurs d’accès Internet (FAI) vous propose un tel espace d’hébergement. Si ce n’est pas le cas, vous pouvez en trouver à pas cher, voire gratuits, si vous cherchez un peu (NdT: Free, iFrance sont deux exemples gratuits).

À moins que vous disposiez déjà d’une connexion très haut débit chez vous (surtout en débit montant, upload), l’utilisation d’un dépôt devrait améliorer les performances (sauf si vous êtes tombé sur un serveur en carton). En effet, vos joueurs pourront télécharger plus rapidement les fichiers de la campagne; et c’est là l’intérêt principal du dépôt.

Créer un dépôt
--------------

Pour créer un fichier de dépôt, chargez votre campagne dans MapTool et allez dans Fichier -&gt; Exporter -&gt; Fichier de dépôt de campagne. Vous pourrez ainsi enregistrer un fichier ZIP qui contiendra les données du dépôt.

Décompressez le fichier (c’est très important ! MapTool ne peut pas utiliser un dépôt s’il reste compressé). Dedans, vous devriez trouver un répertoire nommé «assets» et un fichier «index.gz». Déposez ces deux éléments sur votre espace d’hébergement Internet. Assurez-vous qu’ils se trouvent dans le même répertoire (ne déposez pas le fichier index.gz *à l’intéteur* du dossier «assets»).

Notez l’URL (NdT: l’adresse internet qui permet de télécharger le fichier) de votre fichier index.gz. Vous pouvez tester celle-ci en la copie-collant dans votre navigateur. Si c’est bon, votre navigateur devrait vous afficher une page avec un contenu bizarre ou vous proposer de le télécharger (NdT: l’essentiel, c’est ne pas avoir d’erreur 404).

Dans MapTool, allez dans Édition -&gt; Propriétés de la campagne, puis allez sur l’onglet Dépôts (Repositories). Supprimez tout ce qui s’y trouve et ajouter votre URL.

Sauvegardez votre campagne. Désormais, quand les joueurs se connectent à votre serveur, ils récupéreront les fichiers depuis le dépôt plutôt que depuis votre ordinateur.

Si vous modifiez le contenu de votre fichier de campagne, vous devrez réexporter le dépôt et le redéposer en ligne. Toutefois, vous n’aurez pas à éditer à nouveau les paramètres de votre campagne, puisque l’URL n’aura pas changé.

{Languages|Introduction to Campaign Repositories}}{{\#customtitle:Introduction aux dépôts de campagne|Introduction aux dépôts de campagne}}

<Category:MapTool> <Category:Tutorial>