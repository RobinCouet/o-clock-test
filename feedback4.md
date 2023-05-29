
# Feedback apprenant 4

Bonjour "apprenant 4", je vais te faire un retour sur ton projet, en précisant les points positifs et les points à améliorer !

# .htaccess
En PHP, quand tu veux faire un **router** (donc faire en sorte de linker des URLs et des methods de ton controller), **tu as besoin d'un fichier .htaccess**. Il te permet grâce à Apache2 d'autoriser la **redirection de l'URL demandé** par le navigateur vers ton fichier index.php par exemple afin d'appeler la method correspondante. Dans ton projet, il manquais ce fichier et donc, mis à part la page d'accueil (qui fonctionne grâce au nom index.php et qu'il est dans le dossier public de ton site), aucune autre URL ne fonctionne.

## use MainController 
Dans ton `index.php`, tu fais ligne 14 un `use App\Controllers\MainController`, mais ce fichier n'existant pas nous arrivons sur une erreur bloquante qui m'empêche d'aller plus loin sur le site. Pour aller plus loin et tester les autres fonctionnalitées j'ai donc supprimé cette ligne ainsi que la route pour la page d'accueil

## Erreurs

Dans tes controllers Teachers et Students, ligne 19 il manque un `;` a la fin, ce qui empêche le code de bien s'exécuter car chaque instruction en PHP se terminent par un `;`.
Tu `extends` ta `class` de `CoreController`, mais tu n'as pas de fichier / class `CoreController` dans ton projet, cela ne peux donc pas fonctionner.

Tu appels ta fonction `teachers()` dans ta fonction `teachers()`, ce qui n'est pas une erreur en soit, si l'on souhaite faire des fonctions récursives mais ce n'est pas le cas ici, il faut donc supprimer cette ligne pour éviter une boucle :

 - La fonction `teachers()` se lance
 - On instancie un nouveau prof
 - On lance la fonction `teachers()`
 - La fonction `teachers()` se lance etc

Sur ta ligne : `$teachers = $teachersdModel->findAll();`, tu as un "d" en trop a la fin de "teachers" donc la variable n'est pas reconnue.

Pour le reste, je te conseil de regarder la structure du corrigé afin d'ajouter le `CoreController` pour gérer entre autre la partie render de ton controller

## Conclusion

Le projet n'est pas terminé donc je n'ai pas énormément de retours à te faire. N'hésite pas à revoir la structure de tes controllers, afin de gérer facilement l'affichage de tes vues via la fonction render. Penses à toujours avoir un `.htaccess` également afin de faire fonctionner correctement ton router. Les parties manquantes sont dans le corrigé, je ne peux que te conseiller d'essayer de refaire le projet après avoir bien lu le corrigé pour essayer d'aller plus loin par exemple dans le développement des controllers
