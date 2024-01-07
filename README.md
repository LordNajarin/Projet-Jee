Readme - Projet Microservices avec Spring Cloud

Équipe de développement
Abdellah Benabdennour
Nisrine Benabdennour
Hoda El Mgadmi
Introduction

Ce projet, réalisé dans le cadre du DEVOIR N°1 du Module JEE, vise à développer des microservices avec Spring Cloud pour la gestion des commandes.

Microservice-Commandes
Fonctionnalités
Le microservice-commandes permet d'effectuer des opérations CRUD sur une entité "COMMANDE" avec une version (1) de la table comprenant les colonnes suivantes : [id, description, quantité, date, montant].

Configuration
La configuration du microservice-commandes est gérée au niveau de Spring Cloud et stockée sur GitHub. Une propriété personnalisée, "mes-config-ms.commandes-last", est utilisée pour définir le nombre de jours pour afficher les dernières commandes. Par exemple, "mes-config-ms.commandes-last = 10" affiche les commandes des 10 derniers jours.

Chargement à chaud
En utilisant le service Actuator de Spring, la propriété "mes-config-ms.commandes-last" peut être modifiée à chaud. Dans notre cas, il est demandé de changer cette propriété à 20 pour afficher les commandes des 20 derniers jours.

Supervision de la santé
Le service Actuator est également utilisé pour implémenter la supervision de la santé du microservice-commandes. Le statut "UP" est affiché, mais il est personnalisé pour dépendre de la présence de commandes dans la table. Si des commandes existent, le statut est "UP", sinon, le statut est "DOWN".

Étude de cas (2)
La version (2) de la table "COMMANDE" ajoute la colonne "id_produit".

Enregistrement auprès d'Eureka
Les microservices-commandes et microservices-produit doivent être enregistrés auprès d'Eureka pour la découverte de services.

API Gateway
Une API Gateway est implémentée comme point d'accès unique à l'application, facilitant la gestion des requêtes et la redirection vers les microservices appropriés.

Fonctionnalités CRUD
Les fonctionnalités CRUD du microservice-commandes sont implémentées pour prendre en charge la version (2) de la table "COMMANDE".

Gestion des erreurs avec Hystrix
Un mécanisme de contournement est implémenté avec Hystrix pour protéger le microservice appelant en cas de timeout d'un des deux microservices. Cela garantit une meilleure résilience de l'application.

Conclusion
Ce Readme fournit une vue d'ensemble du projet, de l'équipe de développement et des fonctionnalités implémentées. Suivez les instructions ci-dessus pour une exécution efficace des projets. Pour des détails techniques supplémentaires, référez-vous à la documentation du code et aux commentaires dans les fichiers source.
