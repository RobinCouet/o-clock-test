# Feedback apprenant 1
Bonjour "apprenant 1", je vais te faire un retour sur ton projet, en précisant les points positifs et les points à améliorer !

# .htaccess

En PHP, quand tu veux faire un **router** (donc faire en sorte de linker des URLs et des methods de ton controller), **tu as besoin d'un fichier .htaccess**. Il te permet grâce à Apache2 d'autoriser la **redirection de l'URL demandé** par le navigateur vers ton fichier index.php par exemple afin d'appeler la method correspondante. Dans ton projet, il manquais ce fichier et donc, mis à part la page d'accueil (qui fonctionne grâce au nom index.php et qu'il est dans le dossier public de ton site), aucune autre URL ne fonctionne.

## Modification d'un professeur / d'un élève

Quand tu fais ton formulaire de modification de professeur par exemple, tu génères ta route `teacher_update_post` ce qui est parfait, mais il manque un petit détail c'est l'identifiant du professeur que tu veux modifier. Par exemple, sur ton site actuellement, si je veux modifier Jean (#3), l'URL de mon formulaire POST est `action="/teacher/"`, donc mon back-end ne peux pas savoir de quel professeur je parle. De plus, la route `/teacher` en POST n'existe pas dans ton fichier index.php. Tu dois donc rajouter dans ton URL de POST l'identifiant du professeur par exemple comme ceci : `action="<?=  $router->generate('teacher_update_post') .  $teacher->getId() ?>"` ce qui te donnera une fois ton site lancé ce résultat : `action="/teacher/3"`. Maintenant, nous pouvons récupérer l'ID du professeur Jean (l'ID numéro 3) afin de le modifier en base de donnée de manière sécurisé.

Tu as le même problème coté étudiant

## Liste des utilisateurs

Dans la liste des utilisateurs, tu as mis un bouton pour supprimer un utilisateur, de la même manière que les profs et les étudiants, sauf que tu n'as ni de route, ni de method pour supprimer un User. Si tu veux la faire fonctionner, tu peux rajouter une route `'/student/[i:studentid]/delete'` par exemple et créer une fonction `studentDelete` dans ton controller UserController (même si cela n'est demandé que dans le megabonus). Idem pour l'édition d'un utilisateur

## Ajout / Modification / Suppression
Après l'ajout, la suppression ou la modification d'une entité (tel que teacher ou student par exemple), il est préférable de rediriger vers la page qui liste plutôt que de réafficher la page. Cela permet d'éviter toute erreur d'ajout en double par exemple. Pour cela tu peux remplacer ta fonction `$this->show` par `$this->redirectToRoute('nom-de-la-route');`

## &lt;select&gt;&lt;/select&gt;

Lors de la mise à jour d'une entité, tel que l'étudiant ou le prof, il est important d'avoir la bonne option sélectionnée de base. Par exemple, quand je met un jour un  étudiant sur ton projet, par défaut aucun prof n'est sélectionné même si en base de donnée il l'est.
Tu peux par exemple ajouter une condition dans chaque options pour verifier si l'ID du teacher est égal à l'id lié a l'étudiant : 

    <?= $student->getTeacher_id() == $teacher->getId() ? 'selected' : '' ?>
Cela va vérifier si les ID correspondent, et si c'est le cas, l'attribut selected va être ajouté sur notre option afin de l'avoir par défaut


## Conclusion

Dans son ensemble, le projet est bien développé, il y avais quelques coquilles, et à part le htaccess, rien de trop bloquant. Continues comme ça, n'hésites pas à tester toutes les fonctionnalités de ton projet pour être sur de ne pas avoir de soucis de création, modification suppression.