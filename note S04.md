## .sort()

-[ ]

```js
 //     const promo = promosList.find(promo => promo.id === Number(id));
    //     const students = studentsList.filter(student => student.promo === Number(id)); // [{}, {}]

    //     const sortedStudents = students.sort((a, b)=> {
    //       if (a.first_name < b.first_name) {
    //         return -1;
    //       }
    //       if (a.first_name > b.first_name) {
    //         return 1;
    //       }
    //       return 0;
    //     });

    //     // console.log(promo);
    //     if (!promo) {
    //       next();
    //     }

```





## S04

GDP = Gestion de projets

L'ensemble des outils qui vont nous permettre d'organiser notre travail pour la résolution d'un besoin donné

## Traduire la demande du client / son besoin


- Demnade du client:

```js
Bonjour, nous sommes une école qu'elle est bien, et nous voulons un outil pour faciliter les contacts entre étudiants.
Nous aimerions donc pouvoir lister les promotions ainsi que les étudiants qui les composent, mais aussi accéder aux détails d'un étudiant, photo de profil comprise, l'accès aux profils serait libre et gratuit.
Dans un second temps l'outil pourrait servir à éditer les profils et promotions.

En espérant que vous pourrez répondre favorablement à notre demande.

**système d'identification**  accès aux photos
```


## dans le cas où on creer un nouveau projet sur github. on suit les démarche pour associer ce nouveau projet a github

 
- Step 1: sur Terminal, arriver dans le bon dossier, avec le fichier tout prêt à pusher

   -Par avance: Créer l'architecture des fichier (app, data, .eslintrc, .gitignore ), des packages( express ejs dotenv pg etc)


- Step 2: Ouvrir Github : créer un répo depuis https://github.com/MeiyinPU?tab=repositories

   - repository name
   - public

- Step 3: Commands sur Terminal : 
   - git init
   - git add .
   - git commit -m "add text"
   - git remote add origin  git@@github.com.....................
   - git push --set-upstream origin master

   Après on peut tourjours utiliser comme d'hab:
    git add .
    git commit -m "update"
  - git push
 
- error message: 

```js
To github.com:MeiyinPU/S04E03-challenge.git
 ! [rejected]        master -> master (non-fast-forward)
error: failed to push some refs to 'git@github.com:MeiyinPU/S04E03-challenge.git'
hint: Updates were rejected because the tip of your current branch is behind
hint: its remote counterpart. Integrate the remote changes (e.g.
hint: 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

=> 把既有的.git手動刪除，再reprendre git init, git add ., git commmit......

## 
on peut pas interdire les injections de script dans l'url ?
Pratique à voir => plusieurs étapes des vérifications : controller ou middlewares
un middleware apres routage qui va contrôler la nature de la req et son format


## UI/ UX

UI = nterface utilisateur ex: 
UX = user expérience, du confort utilisateur  ex: button ressort en vert

## 
https://www.tldraw.com/r/9vXt8B7c-rvH5U8zAQKLI?viewport=-980%2C-507%2C3710%2C1978&page=page%3Apage


- [] tableau condant ? 

- [] Sprints

- [] user stories

- [] wireframes

- [] mettre en place de git

## npm run "NOM DU SCRIPT"


-[ ]le port , on l'écrit en minuscule ou majuscule, j'ai vu les 2 il y a une convention?


## Page promo

Preview
- [] créer route => méthode GET + URL '/promos/' (router)
- [] créer une view (views)
- [] créer le controller =>allPromosPage => (mainController)
- [] dynamiser la view 

**Seulement dans mainControllers on a besoin de recuperer la data json**

```js

const promosList = require("../../data/promos.json");


const mainControllers = {


allPromosPage: (req, res)=> {
    res.json(promosList);

}

};

module.exports = mainControllers;

```

- Pourquoi forEach fait déjà le tri?

-[ ] pour les dossiers sur une même ligne, tu peux modifier un setting dans VsCode : il faut décocher Compact Folders je crois, et tu auras bien l'indentat demain ?

const { id, name } = req.params; //attention, id sera une string 

  la description complète/ d'une fonctionnalité se trouve dans **use-case**

  - dotenv permet de charger des variables d'environnement:

    emêcher de versionner les variablees d'environnement 

  - process.env.port permet de récuperer les variables dans un js:


- [ ]mais tu peux avoir du 1.1 - 0.1 qui donnera une relation 1/1 aussi non ?

## MLD

- PROMO (id, github_organisation, name)

- STUDENT (id, github_username, first_name, last_name, profile_picture_url, promo_id #PROMO(id))


## S04E02

- correction: router怎麼寫?

### base de données (BDD)
les données sont disponible sur le serveur mais on va y piocher dedans a travers des requête

- Un BDD n'est pas dépendant au serveur

- Un service indépendant:
  - Tourne tout seul dans son coin
  - Peut être attteint depuis plusieurs autres servicese en même tmeps 
  - Possède une interface pour dialoguer
  - se ressemble au serveur

- A quoi ça sert?
  - à stocker, organiser, gérer et bien sûr renvoyer des données

- SG

Outil pour créer des bases de donnés
Système de gestion de bases de données

dbms - database management system:

1  SGBDR relationnel
2. Les NoSQL

SGBDR
MySQL
MariaDB
POstgreSQL
SQLite

-[ ] D'ailleurs je précise que malgré le fait que le NoSQL soit attrayant, maitriser les requêtes SQL est une obligation pour le TP 


NoSQL = Not only SQL

Un serveur contient X bases de données


- nom du table: singulier, miniscule

Après coté Javascript, les 0 ou 1 sont aussi interpretés comme True ou False donc pas de soucis sur les booléens

-[ ] type : SERIAL

  - snake_case
  - kebab-case
  - camelCase
  - PascalCase

## Processus de créeation

- On va utiliser la méthode MERISE: MCD -> MLD
  -MCD : Modèle Conceptuel de Données
   Le but: identifier les différents entités et leurs associations.

   On liste les attributs des entités
   On associe les entités entre


  -MLD : Modèle Logique de Données
   possible d'avoir 3è table

-[ ] tu paies le serveur, sauf si tu l'héberges sur un serveur chez toi 

-[ ] Pour les projets personnels mongoDB propose une offre gratuite

-[ ] au fait, rien a voir mais Oracle met a disposition un espace gratuit pour stocker ses VM en ligne OracleCloud


-[ ] slides.
https://kourou.oclock.io/ressources/fiche-recap/mcd-modele-conceptuel-de-donnees/


- [ ] c est peut etre pour avoir une multitude de combinaison de requete ...possible ?



## sur un db à distance
- Our own db
**psql -U trombi -d trombi**

- db o'clock
**psql -h  pg.oclock.lan -U etudiant -d trombi**
mdp:js4life

Nullable : not null  => il faut pas mettre nul sur ce column
character varing(128) => 128 characters maxi

\q qui SQL db in terminal

## documentation

- node-postgres is a collection of node.js modules for interfacing with your PostgreSQL database.
  https://node-postgres.com/


- [ ] je mélange encore l'utilisation .env et appLocals
appLocals: res.locals

## S04E03

"scripts": {SE
    "dev": "nodemon index.js",
    "connect-db": "psql -h pg.oclock.lan -U etudiant -d trombi"
  },

  SELECT * FROM promo ORDER BY last_name ASC ORDER BY first_name ASC;

  ! pas obligatoire de préciser `ASC` vu que c'est le sens de tri par défault;

  primary-key = pk
  foreign-key = fk

https://stackoverflow.com/questions/17538549/what-does-the-symbol-mean-in-the-command-line-in-mysql


- W3School
   - Select all records from the Customers table, sort the result alphabetically, first by the column Country, then, by the column City.

   SELECT * FROM Customers ORDER BY Country, City;


## promise

- Une promess peut avoir 3 états
  - Pending => la promesse est en cours d'execution
  - Fulfilled/resolved => la promesse est résolue, aucune erreur
  - Rejected => la promessse a rencontré une erreur

Syntaxe:
**.then((sucess,error) =>{}).catch((error)=>{});**

- [ ] https://node-postgres.com/features/queries#parameterized-query

color break => natif

- [ ] DROP TABLE Shippers; // delete a table

**sudo -i -u postgres psql**

**postgres=# CREATE USER trombi WITH PASSWORD 'trombi';**
<!-- CREATE ROLE -->
**postgres=# CREATE DATABASE trombi OWNER trombi;**
<!-- CREATE DATABASE -->

**psql -U trombi -d trombi -f create_db.sql**
```sql
Mot de passe pour l'utilisateur trombi : 
psql:create_db.sql:1: NOTICE:  la table « student » n'existe pas, poursuite du traitement
DROP TABLE
psql:create_db.sql:2: NOTICE:  la table « promo » n'existe pas, poursuite du traitement
DROP TABLE
CREATE TABLE
INSERT 0 175
CREATE TABLE
INSERT 0 7942
```
**psql -U trombi -d trombi**

- Pour activé la couleur des lignes des brackets avec :

Open the Settings window by pressing down CTRL + , (comma) or go to File -> Preferences -> Settings and search for “bracket pairs“.

## db SQL

### PSQL (programme en LDC pour PostgreSQL)
- `\dt` display tables => afficher toutes les tables présentes dans la db courante
- `\d nomTable` =W affiche la structure de la table spécifiée

### SELECT - afficher les données

structure

- `SELECT colonne1, collone2 `


### INSERT - Créer des enregistrements
### DELETE

```sql
DELETE FROM nom_du_Table;
-- Attention! supprimer tous les enregistrements de la table;
DELETE FROM nom_du_Table WHERE condition;

DELETE FROM student WHERE promo_id=1;
```

- [ ] si student etait en 0, N on aurait pu supprimer la promo avant le transfert?

### UPDATE student

- [ ] alias?


```sql
UPDATE nomTable SET nomColonne = nouvelleValeur; 
<!-- Attention: modifie la valeur de al colonne pour tous les enregistrements de la table -->

UPDATE nomTable SET nomColonne = nouvelleValeur WHERE  
UPDATE student 
```


UPDATE student SET promo_id = 5 WHERE promo_id = 1;
UPDATE student SET promo_id = 5 WHERE first_name ILIKE '%max%';
UPDATE student SET github_username='patate' WHERE id=7945;


## INSERT

```sql
INSERT INTO nomTable (colonne1, colonne2) -- on ne précise que les colonnes pour lesquelles on va ernseigner des valuers
VALUES (ValeurColonne1, valeurColonne2); -- L'ordre doit être le même que celui de la déclaration des colonnes
-- on peut créer plusierus enregistrement à la fois
INSERT INTO nomTable (colonne1, colonne2)
VALUES ()
```

INSERT INTO promo (id, name, github_organization) VALUES (900, 'NouvellePromo', 'zuigyfizur');
INSERT INTO student (first_name, last_name, promo_id) VALUEES ('Nouveau', 'Student', 901)

SELECT * FROM student WHERE promoID=900;


- [ ] l'ordre a une importance ? 

CREATE TABLE IF NOT EXISTS "promo" (
  "id" INT NOT NULL PRIMARY KEY,
  "name" VARCHAR(128),
  "github_organization" VARCHAR(255)
);

- [ ] ### constraint
Jamais deux même emails dans un même table 


- [ ] PGURI="postgres://trombi:trombi@localhost/trombi" +> CONST DB + NEW Client(process.env.PGURI)


## reconstruire bd

1. Terminal : re-situer /re se met dans l'emplacement ou mon db sql a été crée: (avec chemin absolu)
2. commande: 
```SQL
psql -U trombi -d trombi -f create_db.sql
```

## S04E04

id SERIEL 自動遞增
沒有orga =>


comparaison async/await vs promise:
https://www.smashingmagazine.com/2020/11/comparison-async-await-versus-then-catch/

````


``
promoPage: async (req,res, next) => {

  const { promoId } = req.params; 
    const sqlPromo = {
      text: 'SELECT * FROM promo WHERE id = $1',
      values: [promoId],
    };

  const sqlStudents = {
    text: 'SELECT * FROM student WHERE promo_id = $1 ORDER BY last_name, first_name ASC',
    values: [promoId],
    };

try {
  //execute en synchrome
  //sauvegarder des reqêtes dans les variables
 const result1 = await db.query(sqlPromo);
 const result2 = await db.query(sqlStudents);

 console.log(result1.rowCount);
 console.log(result2.rowCount);

if(!result1.rowCount) {
  console.log("Aucune promo trouvé");
  throw new Error("Aucune promo trouvé");
}


if(!result2.rowCount){
  console.log("Aucun étudiant");
  noStudents = true;
}

res.render('promoDetails', {
promo : result1.rows[0],
sortedStudents : result2.rows,
noStudents
});


https://node-postgres.com/features/queries#parameterized-query

^
branche
Modulariser tous les requêtes sql : data mapper


##S04E05

Regex

Les données de tout les compte sont dans le fichier .env, ou on verra aussi un autre moyen pour gérer autant de comptes? visible par parsonne. PGUSER=ADMIN PGUSER=UTILISATEUR

comment tu changes la connections a la DB ? en fonction des pages  ? 

dbAdmin = new Client({
  user

})

- pour interdire les caracters spéciaux
regex = 'zier'
string = 'hello'
string.match(regex)

- formik.doc
plusieurs librairie: ex: yup
[yup](https://github.com/jquense/yup)
[regex](https://regexr.com/3e48o)

## Cookies

Rappels sur HTTP
Stateless : pas de mémoire

app.Locals = mémoire écraser une fois le serveur étient


le serveur a demander le navigateur de stocker les info pour moi

Stocké par le navigatuer, envoyée à chaque requêtes
uen requête = toutes ls cookies liés au serveur

dev 
Accès côté navigateur
document.cookie = "username=xxxx";

pour vérifier =>application => serveur;
les cookies ne sont que des strings ? ou on peux envoyer des objets?que les stirngs

On ne peut accéder q

Accès côté Express
req.headers
un Object ! moddleware coolie-parser

Peux-tu reexpliquer la différence entre localStorage et cookies? 

cookies founctionnele
cookies 

https://chrome.google.com/webstore/detail/i-dont-care-about-cookies/fihnjjcciajhdojfnbdddfaoknhalnja


Session:

comment 

Le serveur qui 

express session : 


https://github.com/O-clock-Gyoza/Ocode-Gyoza


## S04E07 correction

ici on n'utilise pas de try/catch pour gérer l'erreur pour 2 raisons:

1. Cette methode (qui est une promesse) va être appllé par une controller, on va donc lui laisser la gestion de l'erreur en retournant le resultat de la promesse tel quel : peu importe qu'elle soit resolved ou rejected, c'est le controller qui va gérer les 2 cas

2. si on gère l'erreur dans le dataMapper, on en peut pas faire grand choses avec => on n'a pas accès à res, req


## 
SID =identifiant de la session de l'utilisateur

## erreur classique

Cannot GET/article : La route ne correspond pas
                  : pas importé, soit module pas exporté, soit erreur de syntaxe
                  
## URL vs. URI


Une URL (Uniform Resource Locator) est une sorte d’URI (Uniform Resource Identifier) qui indique l’emplacement d’une ressource sur le web, comme une page web, une image ou un fichier. Par exemple, https://www.bing.com est une URL qui localise le moteur de recherche Bing.

Une URI est une chaîne de caractères plus générale qui identifie une ressource de manière unique, soit par son nom, soit par son emplacement, soit par les deux. Par exemple, ISBN 0-476-35557-4 est une URI qui nomme un livre spécifique, sans indiquer où il se trouve.

Toutes les URL sont des URI, mais l’inverse n’est pas vrai. Une URL est un sous-ensemble de l’URI qui fournit non seulement l’identité, mais aussi le moyen d’accéder à une ressource. Une URI peut être un nom (URN) ou un localisateur (URL), ou les deux.

La syntaxe d’une URI se compose de plusieurs parties, telles qu’un schéma, une autorité, un chemin et une requête. La syntaxe d’une URL est similaire à celle d’une URI, mais son autorité comprend un nom de domaine et un port.

Voici un exemple d’URI et d’URL :

URI : data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAA 
URL : https://www.bing.com/images/search?q=cat

L’URI est un format de données qui contient une image codée en base64, tandis que l’URL est une adresse web qui permet de rechercher des images de chats sur Bing.


```
<% for (let i = 0; i < 5; i++) {%>



<% if (i < review.note) { %>
&#9733;
<% } else { %>
&#9734;
<% } %>
<% } %>


```


<% 
const noteGlobal = Math.round(reviews.reduce((compteur,review) => compteur + review.note , 0) / reviews.length);
let note = "";
for( let index = 1; index <= 5; index++ ) {
if ( index <= noteGlobal ) {
note+= "&#9733; ";
} else {
note+= "&#9734; ";
}} %><%- note %>


SELECT ROUND(AVG(note)) as moyenne, COUNT(id) as nbrReviews, name as NomDeLaFigurine FROM review WHERE figurine_id = $1",
values

SELECT figurine_id, ROUND(A VG(note)) moyenne FROM review GROUP BY figurine_id

## Associations : les liens entre les relations/tables

## cardinalité:
1:1 1 student = 1 first name:  nouveau champ qui porte directement la valeur
1:N 1 promotion concern N studnet: nouveau champ qui porte un ID revoyant à une autre table
N:N N professors concern N promo: table de liaison

DBEAVER

TablePlus

SELECT * FROM student JOIN promo ON promo.id = student.promo_id WHERE student.id = 1;

## SQL JOIN

Permet d'aller chercher des données dans plusieurs tables à la fois(si elles sont liées via une clé étrangère)

Pour chercher les étudiant et les infos de la promo 5:

SELECT * FROM student WHERE promo_id = 5;
SELECT * FROM promo WHERE id=5;
=>
SELECT * FROM promo JOIN student ON student.promo_id = promo.id WHERE promo.id = 5;

## syntaxe

Aller chercher les élements de la table A et ceux qui y sont liés dans la table B
SELECT * FROM tableA JOIN tableB ON tableA.primaryKey = tableB.foreignKey;

optimiser plusierus requêtes:
```
const figurine = await dataMapper.getOneFigurineById(figurineId)
const reviews = await dataMapper.getReviewsByFigurineId(figurineId)
const stats = await dataMapper.getOneFigurineAvgNote(figurineId)
```
SELECT * FROM figurine JOIN review ON figurine.id = review.figurine.id WHERE figurine.id = 1;


http://cluedo.oclock.lan/

https://mystery.knightlab.com/


correction atelier PP: https://github.com/O-clock-Gyoza/Gyoza_S4_Blue_Charly


## challenge S04E08

- [ ] différence MySQL vs SQL
- [ ] requêtes imbriquées? 
// correction Charly:

SELECT * FROM rapport_police WHERE date= 11122019 AND type="caricature..."

SELECT * FROM temoignage JOIN personne ON t.personne_id = p.id WHERE p.nom LIKE 'Beth Rave' 

SELECT * FROM temoignage t JOIN personne p ON t.personne_id = p.id WHERE p.rue LIKE 'Sadi Carnot' ORDER BY p.numero_rue DESC LIMIT 1;

temoignage t = temoignage AS t 

LIMIT 1 => limit à un résultat

SELECT * FROM personne AS p
JOIN promo ON promo.id = p.promo_id
JOIN projet ON projet.id = p

une qestion bête:
on est bien d'accord sur la requête sql qu'on ne met pas le double quote sur la valeur d'un integer

SELECT * FROM temoignage JOIN personne ON personne.id = temoignage.ersonne.id WHERE personne.nom = 'Cyruk Hique';


SELECT * FROM personne AS p
JOIN role ON role.id = p.role.id
WHERE p.taille BETWEEN 180 AND 190
AND p.age BETWEEN 40 AND 45 




// moi

1. SELECT * FROM personne JOIN temoignage ON personne.id = temoignage.personne_id
WHERE personne.nom='Beth Rave' OR rue LIKE '%Sadi Carnot%' ORDER BY numero_rue DESC;


=> personne.nom='Alex Trémité'; (id=549)
=> Je n'ai pas vu le coupable, mais il faisait partie de la promo de couleur pourpre.
=> J'ai vu le coupable mais je ne connais pas son nom ! En revanche, je sais qu'il a travaillé sur le projet O'asis !


2. SELECT * FROM personne JOIN promo ON personne.promo_id = promo.id JOIN projet ON personne.projet_id=projet.id
WHERE promo.couleur = 'pourpre' AND nom_projet = "O'asis";

=> Cyril Hique

3.SELECT * FROM personne JOIN temoignage ON personne.id = temoignage.personne_id
WHERE  personne.nom = 'Cyril Hique';


SELECT * FROM personne JOIN role ON personne.role_id = role.id
WHERE  role.nom_role = 'helper' AND age BETWEEN 40 AND 45 AND taille BETWEEN 180 AND 190;

=> Gédéon Groidenmabaignoire

## 如何修改commit -m 已推送的comment ?

- 若還沒push => git commit -amend -m "新的 commentaire"
- 若已push => 您可以使用 git rebase -i HEAD~n 来交互式地修改您的 commit 信息，其中 n 是您想要修改的 commit 的数量。然后，您需要使用 git push --force 来覆盖远程仓库的历史记录。请注意，这种方法可能会影响其他人的工作，所以请谨慎使用。

## html: form

option disabled selected =>預設是停留在同行選項，一旦選擇其他選項，就不能回到原同行選項

## for(const promo of promoList){

}


## result de notre requête dans le dataMapper

// c'est la db qui nous a envoyé ces infos
```js
Result {
  command: 'INSERT',
  rowCount: 1,
  oid: 0,
  rows: [],
  fields: [],
  _parsers: undefined,
  _types: TypeOverrides {
    _types: {
      getTypeParser: [Function: getTypeParser],
      setTypeParser: [Function: setTypeParser],
      arrayParser: [Object],
      builtins: [Object]
    },
    text: {},
    binary: {}
  },
  RowCtor: null,
  rowAsArray: false,
  _prebuiltEmptyResultObject: null
}
controller sucess
{
  id: 185,
  name: 'Kraken',
  github_organization: 'https://github.com/O-clock-Kraken'
}


```

yesWeHack

## Cookies et Sessions

- Une **session c'est** :
  - stocké par le serveur ( dans la mémoire du serveur)
  - identifié par un numéro unique confié au client
  - sécurisé : innaccessible aux autres utilisateurs
  - fiable: repose uniquement sur le principe des cookies, lui même fiable

un cookie c'est:
  - stocké par le navigatuer
  - envoyé au serveur via le header à chaque fois qu'on fait une requête (c'est le navigatuer qui fait ça tout seul)
  - un bout de texte/chaine de caractere au format name = value (clé = value)
  - fiable : envoyé aun serveur à chaque requête (sans exception)
  - non sécurisé : totalement lisible et modifiable par l'utilisateur
  - qaund on refresh la page, il ne change pas. 

Note:

- Un cookie ne peut être créé que côté client
- mais un serveur peut demander à un navigateur de créer un cookie

(Pour sécuriser il faudrait mettre en place https, mais c'est pas le sujet d'aujourd'hui)

inspecteur -> Application -> Cookies
Request -> Headers -> Cookie


1er requête: pas de cookie, le serveur va demander au client de générér un cookie pour être stoké dans le navigatuer =>
2nd requête avec le cookie généré, le serveur le stock (pour générer son cookie?) 


## express-session

`express-session` est un middleware qui permets de mettre en place toute la gestion des sessions, des tokens, etc..en 2 temps 3 mouvements!!

DOC:https://github.com/expressjs/session

npm install express-session

Dans index.js, on branche le middleware

```js
app.use(session)







```



Dans la console on va voir: Application > Cookies: un cookie est apparu !

- Le serveur demande au navigatuer de se créer un cookie avec ces infos là (encodédes avec mon super password secret)

- Ce cookie (appellé `sid`) = mon ticket avec mon identifiant, qui me donne accès au vestiaire, ou caiser à la piscine (espace dans la mémoire du serveur)

- Et surtout le plus important : si on refresh la page: le `sid` ne change pas !


= Pour l'instant dans ce casier est vide. Je peux stocker des choses dedans.

J'y accès dans le code via request.session. C'est un objet tout ce qu'il y a des plus simple. Je peux y ranger les informations que je souhaite, et y accéder partout où j'en ai besoin


req.body:
{ login: 'ryry' }

request.session:
Session {
  cookie: {
    path: '/',
    _expires: null,
    originalMaxAge: null,
    httpOnly: true,
    secure: false
  }
}

## Ofig sql requête catégorie

Pourquoi (req, res, next){

  next();
}

Je comprend pas pourquoi par rapport aux autres méthodes dans le mainController, leftMenu a " next()" à la fin mais pas un return ?
 
 - [ ] sql: when "" when ''

rajouter une figurine
Search

SELECT * FROM fi


if(req.query.search){




}

()? OUI:NON 


  if (req.query.search) {

        figurinesList = await dataMapper.searchFigurinesByName(req.query.search)

      } else {

        figurinesList = await dataMapper.getAllFigurines()

      }



      // Opérateur ternaire 



      // const figurinesList = req.query.search 

      //   ? await dataMapper.searchFigurinesByName(req.query.search) 

      //   : await dataMapper.getAllFigurines()

      https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Operators/Conditional_operator

      Plus à jour, near Charly's version
       
      https://kourou.oclock.io/ressources/objectifs/creer-une-nouvelle-base-de-donnee-sur-postgresql/

doc SQL (Romuald)
https://sql.sh/fonctions/mathematiques

TablePlus
https://tableplus.com/blog/2019/10/tableplus-linux-installation.html
version 20.04
cat/proc/vesrion terminal

# SEO

## Acronyme

## SEO = Search Engine Optimization

serach engine = moteur de recherche
ex: google, yahoo, qwant

Les crawlers: Les robots des moteurs de recherche = des programmes, donc des lignes de code. Ils savent parcourir les sites internet, analyser le ocde html, lire CSS et la plupart peuvent exécuter le JS.

=> mot de clé pour transférer aux rebots

optimization = Adapter son site pour optimiser sa visibilité

Aussi appelé "référencement naturel" ou "référencement organique"


## SEA = Search Engine Advertising (référencement payant, non-naturel)

- Les campagnes Google ADS (les résultats sponsoriés en haut de recherche)
- Les pubs réseaux sociaux (postes sponsorisés etc)

## Fonctionnement SEO
Google va attrivuer un "score" (virtuel et non consultable) à notre site. C'est ce score qui va déterminer sa position dans les résultats d'une recherhe donné.

Il anaylse notre code + le contenu de notre site vai des robots qu'on appellent des "crawlers". 
Il se comportent comme un utilisateur lambda du site: ils vont cliquer sur les liens, les boutons, consulter les images etc.. Mais ça reste des robots !! Il faut donc que le code leur parle (soit clair pour eux)

ex: attribut 'alt' sur les images pour les décrire


Il faut distinquer 3 étapes:
- site en ligne
- site connu par Google (je tape le nom de mon site, je le trouve)
- site bien référencé par Google (je tape des mots clés sur lesquels j'ai positionné mon site, et il apparait dans les premiers résultats de recherche)


la robot va regarder que le front ou le back aussi? OUI que sur le navigateur

https://sites.google.com/view/webcrawlerlatency/experiment

la différence entre être connue par google est être en ligne 

Il faut disto

en tant que développeur, on focus sur SEO


si tu va sur ton site plusieurs fois ca compte comme visite pour le référencement ou c'est base par ip est autre 
- ip counté
- durée de sesssion de navigateur
- pages consultés
- temps de chargement


qui génère le cryptage? Serveur 


https://chrome.google.com/webstore/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd?utm_source=ext_sidebar&hl=fr

How to meet WCAG

https://chrome.google.com/webstore/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd?utm_source=ext_sidebar&hl=fr

Colour Contrast Analyzer

https://chrome.google.com/webstore/detail/wave-evaluation-tool/jbbplnpkjmmeebjpijfedlgcdilocofh

https://www.npmjs.com/package/eslint-plugin-jsx-a11y


Q: 
Refresher une page Web = relancer le serveur ? le cookie ne se change pas ?
Quand on rafraîchit une page web, on ne relance pas le serveur, mais on demande au navigateur de recharger la page depuis le serveur. Le serveur peut alors renvoyer la même page ou une page mise à jour, selon le cas. Le rafraîchissement d’une page web permet de voir les dernières informations disponibles sur le site, ou de corriger certaines erreurs de chargement1.

Un cookie est un petit fichier stocké par le serveur dans le terminal de l’utilisateur et associé à un domaine web. Les cookies servent à mémoriser des informations sur l’utilisateur, comme ses préférences, son identifiant, son panier d’achat, etc. Les cookies sont renvoyés au serveur à chaque fois que le navigateur contacte le même domaine2.

Quand on rafraîchit une page web, les cookies ne changent pas, sauf si le serveur envoie de nouveaux cookies au navigateur. Les cookies ont une date de péremption, qui peut varier selon les sites. Si un cookie est périmé, il est supprimé du navigateur et n’est plus renvoyé au serveur3

# [SEO](https://developers.google.com/search/docs/crawling-indexing/javascript/javascript-seo-basics?hl=fr)



## Acronyme



SEO = Search Engine Optimization



Aussi appelé "référencement naturel" ou "référencement organique"





### Référencement



La place de votre site dans les résultats de recherche d'un moteur de recherche (Google étant le plus important, on va s'intéresser à ses critères avant tout) sur une recherche donnée





## SEO vs SEA



En tant que développeur, on agira sur le SEO



### SEA ???



SEA = Search Engine Advertising



(= référencement payant, non-naturel)



Les campagnes Google ADS (les résultats sponsorisés en haut de recherche)







## Fonctionnement SEO



Google va attribuer un ""score"" (virtuel et non consultable) à notre site. C'est ce score qui va déterminer sa position dans les résultats d'une recherche donnée.



Il analyse notre code (HTML, CSS, JS) + le contenu de notre site via des robots qu'on appellent des "crawlers".



! Les robots ne parcourent que le code que vous envoyez au navigateur (que le front)



Ils se comportent comme un utiilisateur lambda du site : ils vont cliquer sur les liens, les boutons, consulter les images etc... Mais ça reste des robots !! Il faut donc que le code leur parle (soit clair pour eux) (ex: attribut 'alt' sur les images pour les décrire)





### Il faut distinguer 3 étapes : 



- Site en ligne (site trouvable via l'url exacte)

- Site connu par Google (je tape le nom de mon site, je le trouve)

- Site bien référencé par Google (je tape des mots clés sur lesquels j'ai positionné mon site, et il apparaît dans le spremiers résultats de recherche)



## Prérequis pour un bon SEO



- Site rapide à charger (performant)

- Agréable à utiliser (mobile first)

- Accessible (ARIA, contraste)

- Sécurisé (HTTPS)





### Respecter les bonnes pratiques



- Sémantique HTML

- Optimisations (Images)





### Eviter les pratiques dites "black hat"



Ces pratiques sont connues de Google, et fortement sanctionnées.



(texte blanc sur fond blanc, texte en 'display : none', page qui contient uniquement des liens pour s'auto backlink, duplication de contenu ...)





### Accessibilité 

 

- [ARIA](https://developer.mozilla.org/fr/docs/Web/Accessibility/ARIA)

- [Normes d'accessibilité WCAG](https://www.w3.org/WAI/WCAG22/quickref/?versions=2.1)

- WAVE Evaluation Tool pour un audit d'accessibilité 





### Performances



- Audit de performance avec Lighthouse (dans les devtools)





### Les images



#### Format



.svg => logo

.png => image (généré par ordinateur, png conserve des bords droit et intersection nette)

.jpg => photo (il vaut mieux préférer le format webp plus puissant)

.webp => photo (meilleur format de compression pour les photos, mais tout les navigateurs ne supporte pas ce format: https://caniuse.com/webp)



Convertisseurs d'image : 



- [CloudConvert](https://cloudconvert.com/) (limite de 10/jour)

- [Image Online Convert](https://image.online-convert.com/fr/convertir-en-webp)



#### Srcset



Servir la bonne dimension d'image pour la bonne taille d'écran/d'affichage



[Lien MDN](https://developer.mozilla.org/fr/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images)



#### Loading



L'attribut 'loading' permet de déterminer de quelle manière le navigateur doit charger les images : 



- eager => charger les images dès que possible (affecte le temps de chargement du la page et consomme des ressources potentiellement inutiles (dans le cas d'une image qui serait en bas de page si l'utilisateur ne scroll pas jusque là))



- lazy => le navigateur ne va charger l'image que lorsqu'elle se trouve proche de la zone d'affichage (window) --> donc que si c'est réellement nécessaire

















### Sitemap.xml





Liste des URLs de votre site + d'autres infos complémentaires (dernière modification de chaque page, priorité, fréquence de modification...)



Ce fichier est uniquement à destination des "crawlers", c'est ce qui va leur permettre de parcourir votre site en d'en indexer les pages.



Si on ne souhaite pas qu'un epage soit indexée (disponible via la recherche google), il suffit de ne pas la préciser dans le sitemap.xml



(Les robots trouvent le sitemap car il est indiqué dans le fichier robots.txt)



Exemple pour Ofig : 



```xml

<?xml version="1.0" encoding="UTF-8"?>

<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">

  <url>

    <loc>http://localhost:5000/</loc>

    <lastmod>2018-06-04</lastmod>

    <priority>1</priority>

  </url>

  <url>

    <loc>http://localhost:5000/article/1</loc>

    <lastmod>2018-06-04</lastmod>

    <priority>0.5</priority>

  </url>

   <url>

    <loc>http://localhost:5000/article/2</loc>

    <lastmod>2018-06-04</lastmod>

    <priority>0.5</priority>

  </url>

</urlset>

```



##### Robots.txt



Informations/Instructions à destination des robots crawlers



[exemple](https://www.anthedesign.fr/referencement/fichier-robots-txt)



Pour Ofig : 



```

User-agent: *

Allow: /

Disallow: /bookmarks



Sitemap: https://urlSiteWeb/sitemap.xml

```





### Metadonnées



Ofig : 



```html

<meta name="description" content="Site web de review de figurine. Par les fans pour les fans, vous permettant de commenter vos figurines.">

<meta name="author" content="O'Clock 'n Co">

```



### Résultats enrichis (données structurée JSONLD)



Permet d'afficher certains types de contenu de manière enrichie dans les résultats Google (évènements, recettes, produits...)



- [Différents types de contenus enrichis possibles](https://developers.google.com/search/docs/appearance/structured-data/search-gallery?hl=fr)

- [JSONLD](https://developers.google.com/search/docs/appearance/structured-data/intro-structured-data?hl=fr)

- [Générateur de JSONLD](https://webcode.tools/structured-data-generator/recipe)

- [Pour tester l'affichage des résultats enrichis](https://search.google.com/test/rich-results?hl=fr)



13 h 52

Article synthétique sur les PWA : 
https://www.progressive-web-apps.fr/definition-progressive-web-apps-pwa


Détails sur la page GoogleDev dédiée (avec études de cas notamment Excalidraw) : 
https://web.dev/explore/progressive-web-apps?hl=fr


Mais en gros on peut résumer le concept en 1 terme : "simplicité d'utilisation".

C'est juste relou pour l'utilisateur de devoir installer une appli, dans laquelle il faut se log etc etc... Alors qu'une PWA c'est juste une appli web qui "ressemble" à une app native (mobile, tablette...) mais qui va intégrer des fonctionnalités natives (utilisation de la caméra, du micro, du système de fichiers etc...) et tout ça sur navigateur, pas besoin d'installer d'app

S05
- Gestion de projet (wireframes)
- POO orienté objet(classes)
- On soi même un ORM (gentil tranquillou): design pattern active record
- ORM : sequelize 'remplaçant du dataMapper
- Atelier PP
- Authentification
- Git

Une fois un développeur senior m'a dit que le marché d'emploi dans le dev est en train de se tendre. Les entreprises embauchent plutôt les profils non-junior.  Votre avis? 


SELECT pokemon.*, type.name, type.color (選擇在table pokemon裡所有proriete, table 裡type)
FROM pokemon 
JOIN pokemon_type AS p_t ON p_t.pokemon_numero = pokemon.numero 
JOIN type                ON type.id = p_t.type_id WHERE numero = $1

SELECT pokemon.* 
FROM pokemon 
JOIN pokemon_type AS p_t ON p_t.pokemon_numero = pokemon.numero 
JOIN type                ON type.id = p_t.type_id WHERE type.name ILIKE $1



const searchController = {

  searchPage: (req, res) => {

    res.render('search');

  },

  searchType: (req, res) => {

    // récupérer les valeurs du formulaire

    const type = req.query.search



    res.send(type)

  }

};



module.exports = searchController;


    // les guillemets simples '' indiquent une valeur, alorsq que les guillemets doubles "" indiquent un nom de colonne



const sql = {

      text: "SELECT * FROM pokemon WHERE $1 = 'attaque' AND attaque >= $2 OR ",

      values: [stat, value],

    };


        // les guillemets simples '' indiquent une valeur, alorsq que les guillemets doubles "" indiquent un nom de colonne


correction Pokedex:
    https://github.com/O-clock-Gyoza/Gyoza_S4_Blue_Charly