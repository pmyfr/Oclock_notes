## S05E01
Kanban Desk

backlog : todo list

Stories|To Do| In Progress|Testing Done
Story|To Do|In Progress|To verify|Done 
Scrum boards

|En tant que...| J'ai besoin de                      | afin de                         |sprint|
|--------------|-------------------------------------|---------------------------------|------|
|visiteur      | page d'accueil                      |d'accéder au contenu du site     |      |
|visiteur      | visualiser les quizz                |visulaiser les quizz disponibles |      |
|visiteur      | me connecter                        |répondre aux quizz               |      |
|membre        | accéder aux quetsions d'un quizz    |répondre aux questions           |      |
|membre        | visualiser mes réponses et mon score|savoir si j'ai bein répondu      |      |   
|membre        | accéder à son profil                |pouvoir le modifier              |      |
|membre        | me déconnecter   

## Propositions
|En tant que...| J'ai besoin de                                              | afin de                         |sprint|
|--------------|-------------------------------------------------------------|---------------------------------|------|
|membre        | sauvegarde mes réponses et mes scores, les quizz déjà joués |d'accéder au contenu du site     |      |
|membre        | faire des suggestion de quizz/theme                         |visulaiser les quizz disponibles |      |
|membre        | consulter ma progression                                    |                                 |      |
|membre        | partager mon score sur les rseaux sociaux                   |                                 |      |
 membre        | consulter ma progression                                    |                                 |      |
 admin         | CRUD des quizz                                              |                                 |      |
 admin         | CRUD des questions                                          |                                 |      | 
 admin         | CRUD des tags                                               |                                 |      | 
 admin         | CRUD des membres et de leurs statistiques                   |                                 |      |

SCRUM
PO = Product Owner: répresentant des clients


receuil les besoin des clients
créer le backlog
faire un scrum 


sites pour faire le wireframe

homepage 
signup 
signin 
quizz


https://wireframe.cc/

https://draw.io/

https://whimsical.com/wireframes

https://marvelapp.com/features/wireframing

https://www.figma.com/wireframe-tool

## 

éviter maximum le couplage 
limiter le couplage
injection des indépendence  require => passer en fonction

## Architecture

MVC: Model - Vue - Controller

Model = les données
Vue = représeantation graphique que l'utilisateur peut manipuler
controller = 

plusieur vuez à la base d'un même model



Et les middlewares et les routers qu'on a fait en S4 ne font pas partie de MVC ? non

Avantages du MVC
- séparation claire des concept/préoccupation (seperate of concern)
- DRY : un même model peut être utilisé par plusieurs views
- DRY : une même view peut être utilisée dans plusieurs contexte
- Modularité: je veux changer l'affichage, je n'ai que les views à faire

Partials : le bout de vue

SOA : service oriented Architecture

Un service consiste en une fonction ou fonctionnalité bien définie. C'est aussi un composant autonome qui ne dépend d'aucun contexte ou service externe


Le cockpit O'clock, par exemple, suit une architecture SOA. Les différents services sont : 
-l'authentification (ex: Auth0)
- le partage d'écran
- la gestion des webcams et du son
- le chat
- et d'autres, moins visibles (comme des stats...)

Tous ces services sont indépendants, et contactés par une application centrale, codée en REACT

vend le service d'au

## D'autres pattern

SAM: State-action-Model (utilisé par Angular2)
Micro-services:  le principe du SOA poussé à l'extrme (Amazon)

## Liaison avec la BDD

2 grands modèles : DataMapper, Active Record

DataMapper : Un object centralise tous les appels à la db

utilisé par Doctrine, Java Hibernate, Alchemy(un framework Python), Microsoft.NET


- avantages: 
Performances supérieurs (moins d'appels à la DB)
changement de DB facilité
plus felxible

- inconvénients:
Un peu lourd à l'utilisation (bcp d'instructions)

iot
Johnny-Five : the js robotics 

## Active Record

Chaque objet porte les requêtes qui le concernement !
Toutes les classes des modèles auront donc des méthodes d'accès à la db.

utilisé par Eloquent (Laravel-PHP)
Django (Python)
Ruby On Rails
Sequelize
Prisma

Avantage:
Facile et intuitif à manipuler (code léger)
inconvénients:
Un peu moins optimisé (plus d'appels à la db)
Difficile de changer de DB: il faut refiare lse models


## npm trends
comparer 

## ORM: CoreModel.js

Tous les méthodes, fonctionnalités lié 

factoriser 

ORM = Object relationnal Mapping = Librairie

différence Framewrok vs Library

Context : "Je veux un Quizz, avec son auteur, ses questions, et que chaque question oit associée à son answer."

Avec notre CoreModel à la main, on a 2 solutions:
- soit faire une cascade de requêtes, et c'est gentiment horribles
- soit implémenter un méga JOIN, et ça aussi c'est bien horrible

On va utiliser ORM 

C'est un type de programme informatique qui se place en interface entre un programme qpplictafic et une base de données

C'est CoreModel (ou dataMapper, selon ORM) mais en mieux !

ça sert à:
- Mettre rapidement en place les Models
- Voire créer les tables correspondante ("synchronisation")
- Pouvoir changer de db (tant qu'on reste en SQL)sans sembêter avec les différences
- Gérer lse types et les contarintes ("validation") ex.getter setter
- Mettre à jour et modifier la db de façon cadrée et réversible("Migrations") changer la structure de la db
- se connecter à plusieurs serveurs de db en même temps ("Replication")
- Mais surtout gérer les relation avec 


Sequelize
Sequelize is a modern TypeScript and Node.js ORM for Oracle, Postgres, MySQL, MariaDB, SQLite and SQL Server, and more. Featuring solid transaction support, relations, eager and lazy loading, read replication and more.


const { Sequenlize} = require('sequelize');

const { PGUSER, PGPASSWORD, PGHOST, PGPORT, PGDATABASE} = process.env;

const sequelize = new Sequqelize ('postgres://${PGUSER}:${PGPASSWORD}@${PGHOST}:$

define: {
updatedAt: 'updated_at',
createdAt: 'created_at'

}

module.exports = sequelize;

})

Est-ce que mon module npm est secure? :
https://snyk.io/advisor/


https://sequelize.org/docs/v6/core-concepts/model-querying-finders/
