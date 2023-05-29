# Feedback apprenant 2
Bonjour "apprenant 2", je vais te faire un retour sur ton projet, en précisant les points positifs et les points à améliorer !

## Permissions

Par défaut, j'ai accès à toutes les pages et à l'option se déconnecter alors que je ne suis pas connecté. Tu peux gérer ça avec une condition if par exemple. Si la superglobale $_SESSION n'as pas de clé connectedUserId par exemple (selon comment tu définis ta session lors de la connexion, tu n'affiches pas les autres éléments du menu à part le lien pour se connecter. Et si un malin essaye d'aller sur une page dont il n'a pas accès, tu le rediriges vers la page de connexion. 

## Indentation
Ici c'est un détail visuel et non fonctionnel, mais il est très important de bien indenter son code, c'est à dire de bien aligner ses lignes de code en fonction de son contexte, par exemple par défaut on écrit tout a gauche, puis si nous somme dans une fonction on espace les lignes de la fonction de 4 espaces ou une tabulation et on reviens a la fin de la fonction tout a gauche. Cela permet de mieux comprendre notre code, mieux se repérer et donc améliorer la lisibilité de son code

## Liste des étudiants

Dans la liste des étudiants, dans le menu tu as mis ta condition pour afficher la classe active en dehors des guillemets de ta déclaration de classe, cela ne fonctionnera donc pas, il faut juste le replacer dans les guillemets de ta classe et tout sera bon ! J'imagine que tu n'as pas eu le temps de terminer le projet, c'est pour ça que la modification et la suppression d'un étudiant ne fonctionne pas. Si besoin, tu pourras regarder la correction pour voir comment cette partie est faite.

## Conclusion

Le projet n'est pas terminé donc je n'ai pas énormément de retours à te faire. La structure de ton code est bonne, c'est bien ! Les parties manquantes sont dans le corrigé, je ne peux que te conseiller d'essayer de refaire le projet après avoir bien lu le corrigé pour essayer d'aller plus loin par exemple dans la gestion des utilisateurs connectés ainsi que les CRUD (Create Read Update Delete) pour gérer complètement tes entités