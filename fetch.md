
# Methode Fetch
Bonjour "apprenant 4", je vais t'expliquer la methode `fetch()` de javascript, comment on s'en sert et te montrer un exemple concret pour ton projet.

# Définition
`fetch()` est une méthode javascript qui permet de faire des requêtes HTTP en javascript afin de récupérer des données de manière asynchrone (sans rechargement de page). Elle remplace la methode XMLHttpRequest qui auparavant nous permettait de faire de l'AJAX, donc des requêtes HTTP mais de manière plus longue et plus complexe.

## Utilisation de la méthode fetch()
 
source: https://www.pierre-giraud.com/javascript-apprendre-coder-cours/api-fetch/

La méthode  `fetch()`  prend en unique argument obligatoire le chemin de la ressource qu’on souhaite récupérer. On va également pouvoir lui passer en argument facultatif un liste d’options sous forme d’objet littéral pour préciser la méthode d’envoi, les en-têtes, etc.

La méthode  `fetch()`  renvoie une promesse (un objet de type  `Promise`) qui va se résoudre avec un objet  `Response`. Notez que la promesse va être résolue dès que le serveur renvoie les en-têtes HTTP, c’est-à-dire avant même qu’on ait le corps de la réponse.

Pour récupérer le corps de la réponse, nous allons pouvoir utiliser les méthodes de l’interface  `Response`  en fonction du format qui nous intéresse :

-   La méthode  `text()`  retourne la réponse sous forme de chaine de caractères ;
-   La méthode  `json()`  retourne la réponse en tant qu’objet  `JSON`  ;
-   La méthode  `formData()`  retourne la réponse en tant qu’objet  `FormData`  ;
-   La méthode  `arrayBuffer()`  retourne la réponse en tant qu’objet  `ArrayBuffer`  ;
-   La méthode  `blob()`  retourne la réponse en tant qu’objet  `Blob`  ;

Exemple : 

     fetch("https://example.com") //On note l'URL que l'on souhaite appeler
    .then(response => response.json()) // On précise que nous voulons une réponse en JSON
    .then(response => alert(JSON.stringify(response))) // On utilise les données récupérées
    .catch(error => alert("Erreur : " + error)); // Si erreur, alors nous l'affichons



## Exemple concret


Pour utiliser fetch dans ton projet, par exemple pour récupérer une carte spécifique, nous pouvons faire comme ça :

     fetch("http://localhost:1234/card/1") //URL de NodeJS avec le /card pour appeler la bonne route et le /1 pour préciser que l'on veux récuperer la carte avec l'ID 1
    .then(response => response.json()) // On précise que nous voulons une réponse en JSON
    .then((card) => {
	    console.log(card.name)
	    console.log(card.element)
    }) // On utilise les données récupérées
    .catch(error => alert("Erreur : " + error)); // Si erreur, alors nous l'affichons
