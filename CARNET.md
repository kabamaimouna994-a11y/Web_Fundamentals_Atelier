# 📒 Mon carnet de bord

**Nom :**    KABA

**Prénom :**  Maïmouna

**Adresse de mon site :** https://___maika___.pythonanywhere.com

> Modifiez ce fichier directement sur GitHub (icône crayon ✏️) pour répondre aux questions de chaque exercice.
> Écrivez avec vos propres mots : une réponse courte et juste vaut mieux qu'un long copier-coller ! 🙂

---

## 🟢 Exercice 1 — Mon premier déploiement

1. Où se trouve physiquement le code qui fabrique votre page : sur votre ordinateur, sur GitHub ou sur PythonAnywhere ?

   > _Ma réponse :_ Le code source est hébergé et sauvegardé sur GitHub, mais le code qui s'exécute physiquement pour générer la page web se trouve sur le serveur de PythonAnywhere

2. Pourquoi votre voisin(e) peut-il voir votre site, alors que vous n'avez rien installé sur son ordinateur ?

   > _Ma réponse :_ Parce que l'application tourne sur un serveur distant (PythonAnywhere) accessible en permanence via Internet. Le navigateur du voisin a simplement besoin de l'URL pour demander la page au serveur.

---

## 🟢 Exercice 2 — Les URL et les routes

1. Dans l'URL `https://www.google.com/maps`, quel est le nom de domaine ? Quel est le chemin ?

   > _Ma réponse :_ Le nom de domaine est https://www.google.com et le chemin est /maps

2. Que veut dire le message *Not Found* ? Qui l'a envoyé : votre navigateur ou le serveur ?

   > _Ma réponse :_ 

3. Que se passe-t-il si deux fonctions portent le même nom dans `flask_app.py` ? (Indice : essayez, puis lisez l'Error log.)

   > _Ma réponse :_ Not Found" (ou erreur 404) signifie que la page demandée n'existe pas. C'est le serveur qui l'a envoyé après avoir cherché la route correspondante sans la trouver

---

## 🔵 Exercice 3 — Le langage HTML

1. Quelle est la différence entre ce que le serveur **envoie** et ce que le navigateur **affiche** ?

   > _Ma réponse :_Le serveur envoie du texte brut contenant du code HTML et des balises, tandis que le navigateur interprète ce code pour afficher une page visuelle mise en forme 

2. À quoi servent les balises `<h1>`, `<p>`, `<ul>` et `<li>` ?

   > _Ma réponse :_<h1> sert à afficher un titre principal, <p> définit un paragraphe de texte, <ul> crée une liste à puces non ordonnée, <li> représente un élément (une ligne) à l'intérieur de cette liste. 

3. Pourquoi l'image s'affiche-t-elle alors qu'elle n'est pas sur votre serveur ?

   > _Ma réponse :_ Le serveur plante (généralement une erreur de type AssertionError ou un conflit de nom dans l'Error log) car Flask ne sait plus quelle route associer à quelle fonction.

---

## 🔵 Exercice 4 — Les templates

1. Pourquoi est-ce une bonne idée de séparer le code Python et le HTML ? (Pensez à une équipe avec un développeur et un graphiste.)

   > _Ma réponse :_Cela permet une séparation claire des rôles et une meilleure organisation. Un développeur peut se concentrer sur la logique et le traitement des données en Python, tandis qu'un graphiste ou un intégrateur peut modifier la mise en page et le design en HTML sans risquer de casser le code du serveur. 

2. Les `{{ prenom }}` sont-ils remplacés par le serveur ou par le navigateur ? Comment l'avez-vous vérifié ?

   > _Ma réponse :_Ils sont remplacés par le serveur avant même que la page ne soit envoyée 

---

## 🔵 Exercice 5 — Le CSS et les liens

1. Quelle est la différence de rôle entre le HTML et le CSS ?

   > _Ma réponse :_ Le HTML définit la structure et le contenu de la page, tandis que le CSS gère l'apparence visuelle et la mise en forme (couleurs, polices, marges).

2. Pour afficher votre page `/presentation`, combien de fichiers le navigateur doit-il télécharger ? (Vous pourrez le vérifier à l'exercice suivant !)

   > _Ma réponse :_ Il doit télécharger 2 fichiers : le fichier HTML principal et le fichier de style externe style.css

3. Pourquoi faut-il parfois faire **Ctrl + F5** pour voir les changements de CSS ?

   > _Ma réponse :_ Pour vider le cache du navigateur et le forcer à télécharger la toute dernière version du fichier CSS depuis le serveur

---

## 🟣 Exercice 6 — Espionner le navigateur

1. Que signifie HTTP ? Qui envoie la **requête** et qui envoie la **réponse** ?

   > _Ma réponse :_HTTP signifie HyperText Transfer Protocol. Le navigateur envoie la requête (pour demander une ressource) et le serveur envoie la réponse (qui contient le fichier demandé). 

2. Combien de requêtes votre page `/presentation` a-t-elle déclenchées ? Lesquelles ?

   > _Ma réponse :_ Elle a déclenché 3 requêtes principales : La requête presentation, La requête style.css, La requête favicon.ico

3. Que signifie le code `200` ? Et le code `404` de la favicon ?

   > _Ma réponse :_ Le code 200 signifie que la requête a réussi (OK). Le code 404 signifie que la ressource demandée est introuvable (Not Found), ce qui est normal pour la favicon puisque nous n'en avons pas encore ajouté sur le site.

4. Pourquoi les modifications faites dans l'onglet Éléments ne sont-elles pas visibles par les autres visiteurs ?

   > _Ma réponse :_ Parce que ces modifications sont faites en local directement dans la mémoire vive du navigateur sur ta machine. Le code source d'origine stocké sur le serveur (via GitHub) n'a pas bougé, donc les autres visiteurs reçoivent toujours la version initiale.

---

## 🟣 Exercice 7 — Envoyer des informations dans l'URL

1. Dans l'URL `https://www.youtube.com/results?search_query=chat`, quel est le nom du paramètre ? Quelle est sa valeur ?

   > _Ma réponse :_Le nom du paramètre est search_query et sa valeur est chat 

2. Pourquoi le serveur plante-t-il avec `a=bonjour` ? Que faudrait-il faire pour l'éviter ?

   > _Ma réponse :_ Le serveur plante (erreur de type ValueError) parce qu'il essaie de convertir de force la chaîne de caractères "bonjour" en un nombre entier via la fonction int(). Pour l'éviter, il faudrait vérifier au préalable que la valeur transmise est bien un nombre valide (par exemple en testant si elle est numérique) avant d'effectuer la conversion, ou gérer l'exception proprement

3. Pourquoi est-il dangereux d'afficher **tel quel** ce que l'utilisateur envoie ?

   > _Ma réponse :_C'est dangereux car cela expose l'application à des failles de sécurité majeures, comme le XSS (Cross-Site Scripting). Un utilisateur malveillant pourrait injecter du code arbitraire (du HTML ou du JavaScript) qui s'exécuterait directement dans le navigateur des autres visiteurs, permettant par exemple de détourner des sessions ou de modifier l'affichage de la page à leur insu.

---

## 🟣 Exercice 8 — Les formulaires

1. Quelle est la différence visible entre GET et POST ?

   > _Ma réponse :_ En GET, les données du formulaire s'affichent en clair dans la barre d'adresse. En POST, les données voyagent de manière invisible dans le corps de la requête HTTP, et la barre d'adresse reste propre.

2. Pour un formulaire de **recherche**, quelle méthode choisiriez-vous ? Et pour un formulaire de **connexion avec mot de passe** ? Pourquoi ?

   > _Ma réponse :_ Pour une recherche, on choisit GET pour pouvoir copier ou partager l'URL. Pour une connexion, on choisit impérativement POST pour des raisons de confidentialité et de sécurité (le mot de passe ne doit pas apparaître dans l'historique).

3. Les données envoyées en POST sont-elles vraiment « secrètes » ? (Pensez à ce que vous avez vu dans l'onglet Réseau.)

   > _Ma réponse :_ Non, elles ne sont pas secrètes : n'importe qui ouvrant les outils de développement (F12 > onglet Réseau > Charge utile) peut lire très facilement toutes les données envoyées en POST. Seul le chiffrement HTTPS protège leur transport.

---

## 🔴 Exercice 9 — Les codes de statut

1. Quelle est la différence entre une erreur `4xx` et une erreur `5xx` ? Qui est « fautif » dans chaque cas ?

   > _Ma réponse :_ Les erreurs 4xx (comme la 404) concernent une erreur du client (URL incorrecte, ressource inexistante). Les erreurs 5xx (comme la 500) indiquent une erreur interne du serveur (bogue dans le code Python).

2. Comment fonctionne une redirection ? Qui fait la deuxième requête : le serveur ou le navigateur ?

   > _Ma réponse :_ Le serveur répond avec un code de redirection (comme 302) et une en-tête Location. C'est ensuite le navigateur qui effectue automatiquement une deuxième requête vers la nouvelle adresse.

3. Donnez un exemple de situation où un vrai site utilise une redirection.

   > _Ma réponse :_ Lorsqu'on se connecte à un site web, on est automatiquement redirigé vers la page de notre profil ou le tableau de bord.

---

## 🔴 Exercice 10 — Ce que le serveur sait de vous

1. Citez trois informations que le serveur connaît sur vous, sans que vous ayez rien rempli.

   > _Ma réponse :_ L'adresse IP (la localisation approximative), le type de navigateur / système d'exploitation utilisé (User-Agent), et la langue préférée du système (Accept-Language)

2. À quoi peut servir l'en-tête `Accept-Language` pour un site comme Wikipédia ?

   > _Ma réponse :_ Il permet au serveur de savoir quelle langue le navigateur préfère afin d'afficher directement les articles dans la bonne langue.

3. Dans l'Access log, retrouvez une requête qui a reçu un code `404`. Quelle page était demandée ?

   > _Ma réponse :_ La requête demandait généralement favicon.ico, car le navigateur cherche cette icône par défaut sans la trouver.

4. Après cet exercice, que pensez-vous de la notion de « navigation anonyme » ?

   > _Ma réponse :_ La navigation « privée » cache l'historique sur l'ordinateur local, mais elle n'empêche pas du tout le serveur distant de voir de nombreuses informations techniques (IP, navigateur, système

---

## 🔴 Exercice 11 — Le Web des machines : API et JSON

1. Quelle est la différence entre une page HTML et une réponse JSON ? À qui chacune est-elle destinée ?

   > _Ma réponse :_ Le HTML est destiné à un humain (il contient de la mise en page visuelle). Le JSON est destiné à une machine ou une application (c'est un format de données brut sous forme de texte structuré).

2. Dans la page `/horloge`, quel code s'exécute sur le **serveur** et quel code s'exécute dans le **navigateur** ?

   > _Ma réponse :_ Le code Python Flask qui récupère l'heure s'exécute sur le serveur, tandis que le code JavaScript ou l'affichage final s'exécute dans le navigateur

3. Citez une application de votre téléphone qui, selon vous, utilise une API. Quelles données échange-t-elle ?

   > _Ma réponse :_ L'application Météo, qui interroge une API distante pour récupérer les températures et prévisions sous forme de données brutes

---

## 🏁 Pour conclure

En quelques phrases, expliquez à un ami ce qui se passe entre le moment où il tape une adresse dans son navigateur et celui où la page s'affiche :

> _Ma réponse :_ Quand on tape une adresse, le navigateur envoie une requête HTTP à travers Internet jusqu'au serveur distant. Le serveur reçoit cette demande, analyse l'URL, exécute le code nécessaire (par exemple en Python avec Flask), assemble le template HTML et renvoie une réponse HTTP contenant le contenu. Enfin, le navigateur reçoit ce code et l'interprète pour afficher visuellement la page web à l'écran.
