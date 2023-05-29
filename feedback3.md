
# Feedback apprenant 3

Bonjour "apprenant 3", je vais te faire un retour sur ton projet, en précisant les points positifs et les points à améliorer !

# .htaccess  

En PHP, quand tu veux faire un **router** (donc faire en sorte de linker des URLs et des methods de ton controller), **tu as besoin d'un fichier .htaccess**. Il te permet grâce à Apache2 d'autoriser la **redirection de l'URL demandé** par le navigateur vers ton fichier index.php par exemple afin d'appeler la method correspondante. Dans ton projet, il manquais ce fichier et donc, mis à part la page d'accueil (qui fonctionne grâce au nom index.php et qu'il est dans le dossier public de ton site), aucune autre URL ne fonctionne.

## Menu et routing

Le but du router est de ne plus avoir d'URL avec des .HTML par exemple, comme tu l'as défini dans ton index.php. Le router te permet de générer directement les URL de chaque pages avec la fonction `$router->generate('nom_de_la_route')`, que tu utilises dans ta page `home.tpl.php`. Il faut également l'utiliser pour la page d'accueil afin d'avoir un lien qui fonctionne et qui redirige vers la bonne url donc avec `$router->generate('main-home')`. D'ailleurs, ta page d'accueil à comme URL `/home`, il est préférable de mettre comme page d'accueil uniquement le `/` afin d'avoir la page d'accueil à la racine de notre projet

## Mise en page

Pour simplifier ton projet et éviter les répétitions, je te conseil de découper tes pages en 3 : 
  

 1. Déclaration doctype + `<head>` + `<header>`
 2. Contenu de ta page uniquement sans prendre en compte le menu, le footer et le doctype
 3. contenu du `<footer>`

Tu peux même faire une partie avec juste ton doctype et ton `<head>` puis un autre fichier avec ton `<header>`

L'avantage c'est que tu vas pouvoir inclure uniquement le contenu de ta page à chaque fois et donc réutiliser le même squelette de site pour chaque pages. Ton `<header> et <footer>` ne changent pas entre tes pages, donc autant les réutiliser, et cela t'évitera d'avoir des pages comme la liste des profs qui n'ont pas de `<header>`

## Liens

Il y a bien sur des parties qui n'ont pas été finies mais il faut faire attention à la cohérence de ce qui a été fait. Par exemple quand on est sur la page `teacher_list` et que l'on clique sur "ajouter", cela nous redirige vers la page d'ajout d'un étudiant.

## POST étudiants

Quand on ajoute un étudiant, le select `teacher` n'est pas pris en compte. Il faut donc le rajouter dans ton controller et rajouter les Getters et les Setters dans ton modèle Student afin de pouvoir définir le professeur lié à l'étudiant. Tu as choisis de faire le GET et le POST dans la même fonction, ce qui se fait souvent dans Symfony par exemple (framework PHP français), mais si tu veux tu peux également faire 2 fonctions différentes, une pour afficher le formulaire et l'autre pour le traiter, cela te permet d'avoir des fonctions plus courtes et de s'y retrouver plus facilement. Même si ta façon de faire est souvent utilisé et n'est pas une mauvaise chose !


## Conclusion

Le projet n'est pas terminé donc je n'ai pas énormément de retours à te faire. N'hésite pas à revoir la structure de tes vues, afin de simplifier l'affichage des menus par exemple. Penses à toujours avoir un `.htaccess` également afin de faire fonctionner correctement ton router. Les parties manquantes sont dans le corrigé, je ne peux que te conseiller d'essayer de refaire le projet après avoir bien lu le corrigé pour essayer d'aller plus loin par exemple dans la gestion des utilisateurs connectés ainsi que les CRUD (Create Read Update Delete) pour gérer complètement tes entités