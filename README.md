Bibliothèque universelle : Maxitheque
==========

Projet amateur français visant à constituer une bibliothèque 
universelle selon différents types d'oeuvres et à pouvoir les lister dans
une autre bibliothèque personnelle.

Les types d'oeuvres configurés seront : 

- Jeux-vidéos
- Films
- Séries
- Mangas
- Séries animées

Tous ces types contiendront des genres que des gestionnaires 
pourront ajouter et attribuer à des oeuvres

# Lancement du projet

### Prérequis techniques : 

- Php 7.1
- Symfony 3.3
- Composer
- Projet développé avec phpstorm

### Pratiques de base : 

- Pour créer une entité et gérer l'ORM, utiliser l'yml

### Commandes à effectuer

- `git clone` 
- `composer install`
- `bin/console server:run`

# Fonctionnalités implémentées dans l'application

# Fonctionnalités attendues de l'application



### Gestion basique d'inscription/et de connexion. (0.1)

- Création du projet
- Création d'une première vue index
- Création du formulaire d'inscription contenant username, password, verifPassword et mail
- Création des validators sur le formulaire
- Gestion sous mysql des données (config.yml)
- Création de la base de données à partir du parameters.yml 
- Création de l'entité User (username,password,mail)
- L'username doit faire entre 3 et 100 caractères
- Le mail doit faire 5-150 caractères
- Vérifier que le mot de passe comprenne au moins une majuscule et 8-64 caractères
(utilisation https://symfony.com/doc/3.3/doctrine/registration_form.html)
- Vérifier en base que l'username et le mail sont uniques
- Permettre la connexion avec un email ou un pseudo
- Création du repository associé et de son service en yml
- Création des méthodes find($id) et findAll() dans l'UserRepository
- Création du Controller et des actions pour l'inscription, la connexion et la déconnexion
- Gestion du routing des premières actions
- Création du formulaire de login et de logout
- Création des vues associées twig qui reprendront une base
- Ajout du fichier css général dans web/styles/styles.css
- Création d'un menu.html.twig appelé dans le base dans un block (surcharge possible)




### Ajout de trois rôles et vérification par mail (0.2)

- Création de l'entité rôle ?  (ManyToMany)
- Création du rôle "utilisateur"
- Création du rôle "administrateur"
- Le rôle de base sera le rôle anonyme
- Ajout d'une vue pour gérer les utilisateurs si le rôle de l'utilisateur est "administrateur"
- Création du UserController.php avec l'action index disponible seulement pour les administrateurs
- Possibilité pour un administrateur de modifier/supprimer un utilisateur
- Ajouter une vérification à l'inscription par mail pour s'inscrire

### Interface utilisateur et avatar (0.3)

- Modification du UserController.php avec les actions show/edit
- Création d'une vue d'édition pour l'utilisateur
- Faire les vérifications pour qu'un utilisateur puisse seulement se modifier
- Ajout d'un champ d'upload d'image pour l'avatar
- Vérification de l'extension, de la taille de l'image et renommage en username.extension
- Prise en charge d'une propriété "avatar" qui sera un chemin vers un dossier avatar
- Affichage de l'avatar redimensionné dans le menu
- Gestion de tous les cas de sécurité/routing
  - Un utilisateur peut accéder à /users/{username} 
  - Un utilisateur peut accéder à son /users/{username}/edit
  - Un utilisateur ne peut accéder à /users et donc à la liste des utilisateurs
  - Un administrateur peut accéder à /users/{username}/edit
  - Un administrateur peut accéder à /users
  - Un administrateur est un utilisateur
  

  
### Création d'une bibliothèque générale (0.4)

- Création de l'entité library et son repository
- Une library aura de base : un name (jv, animes ...) 
- Création d'un controller LibraryController
- Création d'une route /libraries menant à un index avec toutes les bibliothèques 

### Création de la bibliothèque associée aux jeux-vidéos (0.5)

- Création de l'entité GameLibrary qui extends Library
- Création du controller GameLibraryController
- Création de la route /libraries/games
- Création de l'indexAction dans le GLC qui affichera une vue sur des oeuvres


### Création des catégories (0.6)

- Création de l'entité category et son repository
- Une category aura : 
  - name entre 3 et 150 caractères

### Création des oeuvres (0.6.1)

- Création de l'entité Work
- Un Work aura : un title, sera rattachée à une et une seule library, 
aura une collection de categories (créer la manytomany en yml), une image (upload)
- Ajout d'un controller WorkController
- Ajout d'une route /works et de sa vue

### Vues de bibliothèque et affichage (0.6.2)

- Création de la vue GameLibrary/index.html.twig
- Ajout d'une route /works/new disponible seulement pour les administrateurs
- Permettre la création d'une oeuvre par un administrateur sur la route new
- Ajout d'un WorkType pour créer une oeuvre avec : 
  - title entre 3 et 120 caractères
  - library un entityType
  - 




### TODO 

- La vue /works doit seulement afficher des filtres pour ensuite afficher des oeuvres
- Voir comment gérer le cache
- Penser aux préférences
- Ajouter un thème par library?
- Ajouter une plateform pour les works ? 
- Prendre un nom de domaine, déployer et héberger


  
### Mise en forme basique de l'application (x.x)

