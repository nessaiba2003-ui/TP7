## Description

Ce TP pratique vous permet de maîtriser les techniques d'optimisation des performances dans les applications Java utilisant JPA/Hibernate, en vous concentrant sur le **cache de second niveau** et la résolution du **problème N+1**.

##  Objectifs du TP

-  Comprendre et activer le cache de second niveau dans Hibernate
-  Mesurer les performances avant et après l'activation du cache
-  Identifier et résoudre les problèmes de requêtes N+1
-  Utiliser JOIN FETCH et les entity graphs pour optimiser le chargement des relations
-  Configurer EhCache comme provider de cache
-  Comprendre l'impact des différentes optimisations sur les performances

##  Prérequis

- Java 11 ou supérieur
- Maven 
- JPA/Hibernate


 ## Concepts Clés
       Problème N+1
Le problème N+1 se produit lorsque :
Une requête récupère N entités parentes
Pour chaque entité, une requête supplémentaire est exécutée pour charger les relations
Résultat : 1 + N requêtes SQL
      Solutions :
Utiliser JOIN FETCH dans les requêtes JPQL
Utiliser @EntityGraph
Configurer le fetch strategy approprié


