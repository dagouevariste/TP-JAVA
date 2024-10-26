	Fonctionnement de l'Application

L'application est un système de gestion de location de véhicules qui permet aux utilisateurs de gérer des clients, des véhicules, ainsi que de louer et retourner des véhicules. Voici une explication du fonctionnement l'application :

Menu Principal :

Lorsque l'application démarre, elle affiche un menu avec plusieurs options :
- Ajouter un véhicule
- Ajouter un client
- Louer un véhicule
- Retourner un véhicule
- Lister les véhicules
- Quitter l'application

- L'utilisateur peut choisir d'Ajouter un véhicule en sélectionnant le type de véhicule (voiture ou camion) et en fournissant les informations nécessaires : immatriculation, marque, modèle, année, kilométrage. si il choisit "voiture" : il y'aura les informations supplémentaires telles que le nombre de places et le type de carburant. si il choisit "camion" il y'aura les informations supplémentaires telles que le nombre d'essieux et la capacité de chargement .
Les véhicules ajoutées sont stockés dans une liste.


- L'utilisateur peut choisir d'ajouter des clients en rentrant leurs informations personnelles : nom, prénom, numéro de permis, numéro de téléphone.
Les clients ajoutés sont également stockés dans une liste.


- L'utilisateur peut choisir de louer un véhicule. La consonle va lui monter voir la liste des véhicules avec leur statut (disponible/loué) et il devra choisir celui qu'il souhaite louer, puis il doit également sélectionner le nom du client à qui le véhicule sera loué.
Avant de louer, le système vérifie si le client a le permis approprié pour le type de véhicule .
Si le véhicule est disponible et que le client est autorisé, le véhicule est marqué comme loué, et il est ajouté à la liste des locations en cours du client.


- L'utilisateur peut choisir de retourner un véhicule : il doit sélectionner le client et le véhicule qu'il souhaite retourner.
Le statut du véhicule est mis à jour pour indiquer qu'il est de nouveau disponible.

- L'utilisateur peut choisir d'afficher la liste de tous les véhicules en indiquant leur statut (disponible / loué).

- L'utilisateur peut choisir de quitter le programme


	Structure du Projet

Le projet est structuré de manière modulaire et utilise plusieurs classes et interfaces pour organiser le code. Voici une description des principales composantes :

	- Interfaces Louable : elle définit les méthodes louer() et retourner(). La classe Vehicule va implémenter cette interface.

	-les Exceptions:
VehiculeIndisponibleException: Exception personnalisée pour gérer les cas où un véhicule est déjà loué.
ClientNonAutoriseException: Exception personnalisée pour gérer les cas où un client n'est pas autorisé à louer un véhicule spécifique.

	- Les Classes :

La classe Vehicule : est une classe abstraite qui implémente l'interface Louable. Elle contient des attributs communs à tous les véhicules : immatriculation, marque, modèle, année et kilométrage. Elle contient aussi une méthode abstraite calculerPrixLocation() que les sous-classes doivent implémenter.

Les sous classes Voiture et Camion :sont des classes qui étendent le classe Vehicule. Elles fournissent des implémentations spécifiques pour le calcul du prix de location.

La classe Client : est une classe qui représente un client. Elle contient des attributs pour stocker les informations du client et une liste des véhicules qu'il a loués. Elle inclut également des méthodes pour gérer les locations.

La classe principale ParcAutomobile :contient la méthode main(). Elle gère l'interface utilisateur, les interactions avec les utilisateurs, et coordonne les opérations de l'application. Elle contient des méthodes pour ajouter des véhicules et des clients, louer et retourner des véhicules, lister les véhicules et quitter .