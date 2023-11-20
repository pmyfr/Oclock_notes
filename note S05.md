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

Le dossier pro... pendant le TP, si vous démontrez vos compétences en présentant votre projet... on le regarde pas beaucoup honnêtement. C'est si  votre projet ou votre présentation ne couvre pas toutes les compétences du titre pro qu'on vient le regarder pour vous posez des questions sur le compétences manquantes

https://kourou.oclock.io/ressources/fiche-recap/le-dossier-professionnel-du-titre-professionnel-dwwm/

## problème db : il faut installer db

[nodemon] starting `node index.js`
node:internal/validators:163
    throw new ERR_INVALID_ARG_TYPE(name, 'string', value);
    ^

TypeError [ERR_INVALID_ARG_TYPE]: The "url" argument must be of type string. Received undefined
    at new NodeError (node:internal/errors:399:5)
    at validateString (node:internal/validators:163:11)
    at Url.parse (node:url:183:3)
    at Object.urlParse [as parse] (node:url:154:13)
    at new Sequelize (/var/www/html/S05/PP/OQuizz-Atelier-Thomas-Trehou/node_modules/sequelize/lib/sequelize.js:185:28)
    at Object.<anonymous> (/var/www/html/S05/PP/OQuizz-Atelier-Thomas-Trehou/app/database.js:9:19)
    at Module._compile (node:internal/modules/cjs/loader:1254:14)
    at Module._extensions..js (node:internal/modules/cjs/loader:1308:10)
    at Module.load (node:internal/modules/cjs/loader:1117:32)
    at Module._load (node:internal/modules/cjs/loader:958:12) {
  code: 'ERR_INVALID_ARG_TYPE'
}

Node.js v18.16.0
[nodemon] app crashed - waiting for file changes before starting...
^Cstudent@teleporter:/var/www/html/S05/PP/OQuizz-Atelier-Thomas-Trehou$ 



const mainController = {

    homePage: (req, res) => {

        Quiz.findAll(
            {
                include:[
                    "author"
                ]
            }
        ).then(
            (quizzes) => {
                res.render('index', {quizzes});
                //for (let quiz of quizzes)
                //{
                    //console.log(quiz.id, quiz.title, quiz.author.firstname);
                //}
            }
        );
    }

};

\i dossier/nom_du_fichier_de_creation.sql 

psql -h localhost -U user -d dbname
\i dossier/nom_du_fichier_de_creation.sql

## S05E07

const { request } = require("http");
const { User } = require("../models");
const bcrypt = require("bcrypt");

## bcrypt

## index.js

app.use((request, response, next) => {
  //https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Optional_chaining
  response.locals.user = request.session?.user;
  next();
});

In this case, the optional chaining operator is used to access the user property of the session object, which is stored in the request object. The session object may or may not exist, depending on whether the request has a valid session cookie or not. If the session object does not exist, the expression session?.user will return undefined, and the response.locals.user will be set to undefined as well. This is a convenient way to avoid writing something like this:

response.locals.user = request.session && request.session.user;


## pg-hstore

Pghstore is a Python module that allows you to format and parse data in hstore format, which is a key-value pair data type supported by PostgreSQL12. Hstore is useful for storing semi-structured data or attributes that vary across records3. Pghstore can serialize and deserialize Python objects, such as dictionaries and lists, into hstore strings, and vice versa2. Pghstore also supports NULL values, escaping of quotes and backslashes, and different return types2.

## email validator

const emailValidator = require('email-validator');

## signup controller : signup page 

resumé:
**POST : req.body** ex: login/signup page
**GET : req.query** ex:search
**GET /:id req.param**

req.body.  => POST
req.body.password  => POST
req.body.passwordConfrim  => POST

req.params.id => "/:id"
req.query => formulaire => GET

POST postSignup =>  
const { firstname, lastname, email, password, passwordConfirm } =
        request.body;
POSt postSignin
    const { email, password } = request.body;

parcours solo : search => GET req.query

router.get("/search/element", searchController.searchByElement);
router.get("/search/values", searchController.searchByValues);
router.get("/search/name", searchController.searchByName);

GET: http://example.com?name=John&Age=25

req.query = {
    name: "John", 
    age: "25"
}
req.body = empty

POST:  http://example.com?gender=male&city=New York
req.query = {
    name: "John", 
    age: "25"
}

req.body = {
    gender: "male", 
    city: "New York"
}

 For req.query, you can simply use dot notation or bracket notation to access the properties. For example, req.query.name or req.query[“name”] will return “John”. For req.body, you need to use a middleware like body-parser to parse the body data and make it available in req.body. For example, after using app.use(bodyParser.json()), you can access req.body.gender or req.body[“gender”] and get "male"

. By using this middleware function, you can access the parsed data in the req.body object. For example, if you have a form like this:

<form method=“POST” action=“/submit”> <input type=“text” name=“name” /> <input type=“text” name=“age” /> <input type=“submit” value=“Submit” /> </form>

And you use this middleware function in your app:

app.use(express.urlencoded({ extended: true }));