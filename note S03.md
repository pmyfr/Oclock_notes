
## S03E01 

monter les seruveur HTTP basé sur des middlewares avec un moteur de rendu (EJS - Embedded Javascript Templating)

- [Planning S03](https://github.com/O-clock-Gyoza/S03-index/tree/main)
- [Menu du jour](https://github.com/O-clock-Gyoza/S03E01-decouverte-node-RED-enzoclock/blob/main/docs/menu.md)

## Objectif de la saison : construire un serveur HTTP 

- Serveur HTTP = serveur physique (machine) + serveur application (logiciel qui gère les requêtes)

- `Node.js` permet de construire des serveurs applicatifs via divers modules.



![Schema Cleint Serveur HTTP](note-img/client-server.png)]

## Note sur le port
- On peut ouviir une porte de notre machine pour accéder à différents serveurs applicatifs depuis l'extérieur de la machine.

- La norme, c'est d'ouvrir le port 80 pour les requête HTTP et le port 443 pour les requêtes HTTPS

Par exemple, contacter `https://reddit.com` revient à contacter la machine de reddit sur le port `443`:`https://reddit.com:443`

- Des runtimes/languages pour créer des serveurs HTTPS, il en existe pleins:
- PHP (Symphony, Laravel, vanilla)
- Python (Django)
- Java (Spring boot)
- Ruby (Rails)
- ...
- Javascript => Node (le principal)

Un servuer sans language?
- [x] Apache - HTTP serveur, free and open-source cross-platform web server software. Apache2 HTTP Server est un serveur Web qui utilise le protocole http.
- [x] NGINX - web server hta can also be used as a reverse proxy, load balancer, mail proxy and http cache(Web缓存（或HTTP缓存）是用于临时存储（缓存）Web文档（如HTML页面和图像），以减少服务器延迟的一种信息技术。) 

  [comparaison Apache vs. Nginx](https://www.hostinger.fr/tutoriels/apache-vs-nginx)

- [x] minecraft - jeu vidéo de type aventure "bac à sable"

## Vocabulaire

- `LTS` = Long Term Support
- `back-end` = developpement côté serveur
  - écrire dans des fichiers
  - gérer un serveur HTTP
  - gérer une base de données
  - Peu Importe le langage, on peut backend


## Chemin absolu vs. chemin relatif

- chemin absolu:
  - chemin depuis la racine de la machine ou du serveur
  - commence toujours par `/`
  - ex: `/Users/enzopro/Documents/Repositories/Promos/Gyoza/S03E01-decouverte-node-RED-enzoclock/cours/test-node.js`

- chemin relatif:
  - chemin relatif (=par rapport) au dossier courant
  - commence généralement par `./` mais on peut l'omettre par habitude (ou `../` si on veut remonter, obligatoire)
  - ex: `./cours/test-node.js` ou ``cours/test-node.js`



## Testons Node.js

- Verifions d'abord que Node.js est installé
  - `node --version`

- Différence bash != REPL Node : attention à ne pas taper des commandes de l'une dans l'autre
- il faut généralement penser à quitter node avant de relancer node

## Replay Part 1 
style backgournd-color="red">
## REPL
- Lancer la `Read Eval Print Loop`
  - `node`

- Quitter le REPL
  - `Ctrl + C` puis `Ctrl + C`
  - `.exit`

- clean le terminal
  - Win: `Ctrl+L`
  - OS: `CMD + K`

- Regardons un peu le "context" de Node.js
  - global (pour information)

- Pratique ce REPL
  - notamment pour fiare des petits de syntaxe, profitez-en

- Raccourci
  - `fleche haut` dans un terminal (`node` ou `bash`)



[]
- ubuntu (terminal pour window)
- powershell

- Pratique ce REPL
- notamment pour faire des petits de syntaxe

## Exécuter un fichier JS depuis node

c'est plus léger d'ouvrir un terminal qu'un navigateur

`node chimin-relatif-ouabsolu-du-fichier.js`

Penser notamment à utiliser TAB quand vous taper le nom du fichier


global.process.env.PWD



Un outil qui communique avec notre système d'exploitation



## chemin relatif vs. absolu

- chemin relatif (=par rappot) au dossier courant
- comment généralement par `./` mais on peut l'omettre par habitude
- ex : `.\cours/test-node.js` ou `cours/test-node.js`

- [ ]le problème c'est que lorsqu'on fait un "code ." dans le terminal la racine du terminal de vscode n'est pas la racine de la machine.

- 也可以在parameters直接寫入objet anonyme:

ex: 

function formatAddress(address) { // address = { number: "...", road: "...", city: "..." }
  return `${address.number} ${address.road}, ${address.city}`;
}

console.log(formatAddress({ road: "rue de l'ananas", number: 33, city: "Bikini Bottom" }));
console.log(formatAddress(character.address));

</style>

## Documentation de node.js (grammaire de la language JS)

https://nodejs.org/dist/latest-v18.x/docs/api

Voici **l'API de Node.js** :
API - Application  Programming Interface = l'ensemble des fonctions disponsibles dans Node

- `crypto` : encrypter des chaines de caractère 加密字串 將明文轉為密文
- `http` : créer des serveurs HTTP
- `os` : communiquer avec son système d'exploitation pour demander l'uptime de son orodi
- `File system` : créer des fichiers, éditer les fichiers
- `readline` : pour poser les questions à la ligne de commande
- `Assertion testing` : pour tester

Généralement, on se referre:
- au cours 
- aux docs des modules annexes (Express)
- notamment, pas très beginner friendly...



## Testons notre premier module node : `os`

OS = Operating System = Système d'exploitation = Linux, Mac, Window

```js
const os = require("os")  // { machine, freemem, totalmem, arch, ...} On importe le module d'os dont on a besoin
os.freemem(); //on utilise les méthodes du module dont on a besoin
```
- Anecdote :
  - mémoire FREE (libre) != mémoire AVAILABLE (disponible)
  - La mémoire Libre (= permet des calculs annexes en tache de fond) est minimisé par un OS
  - La mémoire AVAILABLE (=attend d'être utilisé) est maximisé par un OS

- [ ] Flutter pour le dev mobile ?

- Module `os`
  - os.arch() => pour afficher l'architecture
  - os.cpus() => pour indiquer le nombre du CPU dans la machine
  - os.freemem() => pour indiquer la mémoire libre de la machine
  - os.totalmem() => pour afficher la mémoire totale de la machine

```js
console.log(os.freemem()); // octet de libre (mémoire vive RAM) sur ma machine au moment où j'exécute le precess
console.log(os.platform()); // darwin
console.log(os.machine()); // arm64
```

## JAVA est un langauge pour développer
- seveur
- application mobile
- devTool
- Android

[brief history of JS](https://gist.github.com/enzoclock/a1ed24057f0bec0f262daae76a9ea0cd)

## Différence Node Chrome vs. JS 

JS language = base = outil de manipulation

```js
`Back`  Node = runtime = motuer + context
             = V8 (moteur JS) + global (dont functions pour manipuler le file system)

`Front` Chrome = Navigatuer = (runtime) + moteur de rendu + des outils networks + etc...
                            = (V8 (moteur JS) + context(window))
                            =                   manipultaion du DOM
```

Imaginons un petit programme qui regarde le %age de mémoire "free" dans notre machine, et si celui-ci dépasse 5%, prévenir que notre machine n'est pas éfficace.

```js

const freeMemory = os.freemem();
const totalMemory = os.totalmem();

// Comment on calcul le pourcentage de mémoire libre ? 

const freeMemoryPercent = freeMemory / totalMemory * 100;

console.log(`Votre mémoire libre est de ${freeMemoryPercent.toFixed(2)} %`);
```
Note (FYI): pourquoi la freemem() est-elle si petite sur un système ? => https://www.quora.com/What-is-the-difference-between-free-memory-and-available-memory-in-operating-systems

## Différence `Math.round()` ≠ `Math.ceil()` ≠ `Math.floor()`
```js
// Arrondir 四捨五入
Math.round(1.3); // 1
Math.round(1.7); // 2

// Partie entière supérieure
Math.ceil(1.3); // 2
Math.ceil(1.7); // 2
math.ceil(3.14); // 返回 4
math.ceil(-1.23); // 返回 -1

// Partie entière inférieure
Math.floor(1.3); // 1
Math.floor(1.7); // 1
math.floor(3.14); // 返回 3
math.floor(-1.23); // 返回 -2

// The Math.trunc() method returns the integer part of a number. 
// The Math.trunc() method removes the decimals (does NOT round the number).
Math.trunc(1.3); // 1
Math.trunc(1.7); // 1

```

## Modulo

reste de la division entière (euclidienne) d'une nombre par un nombre

```js 
5 % 2 === 1;
10 % 2 === 0;
```

```js
```

### Exo: S03E01-02-3 
[How to console.log with color in JS](https://logfetch.com/js-console-colors/)

[**correction Enzo**](https://github.com/O-clock-Gyoza/Ocode-Gyoza/blob/correction/FS-JS/S03/E01/02.system.js)

**Mes questions:**
- [ ] 1. pas de couloeur sur mon terminal VM ?
- [ ] 2. Calcul de loadAverage ?


## Readline : un module qui permets de communiquer avec les utilisateurs

Pour poser la questions aux utilisateurs

Stream: l'endroit on mettre mettre les xxx

readline peux suivre autre chose que le terminal comme les log? ou la sortie d'un processus?

## Pourquoi poser des questions dans le terminal

Généralement ce n'est pas pour un utilisateur final ce genre de fonctionnalité, mais plutôt pour les devs. en tant que dev, on peut être amené à créer des outils pour permettre aux autres devs de fiare mieux lesur travail.

application en ligne de commande Example 
wisdom-cow

callback dans call back : 2015 Async/await S04

```js
rl.question("Number 1 : ", (nb1) => {
  console.log(nb1); // Première réponse, on peut poser une nouvelle question 

  // Maintenant, on peut poser une nouvelle question
  rl.question("Number 2 : ", (nb2) => {
    console.log(nb2);

    console.log(`Le résultat vaut : ${nb1 * nb2}`);
  });

});
```

y a un code qui permet de sauter une ligne pour pouvoir mettre ta rep a la ligne en desous et pas a coter ? entre les strings "\n"

le readline peux servir à recevoir des instruction pour le serveur lors du déploiement comme changé de port d'écoute à chaud?

si tu as plusieurs donnés à récupérer tu fait plusieurs .on("line") ? avec un switch derrière

## S03E02

- quiz
  -- Runtime est un moteur JS associé à un contexte qui permet d'exécuter un programme JS

- prompt(); 
  --context de chrome

- readline est un module natif de Node.js, et aussi un objet qu'on récupère via la fonction `require`

- API : Un tableau (docs) qui liste toutes les fonctions disponibles

## Version Node.js

active : conseillé pour la production
version paire : pour exister sur la long terme


- [ ] quand on crée un projet est-ce qu'on doit mettre à jour notre version de node?
en dév oui ? en prod oui ?

https://github.come/nodejs/Release

Active = version stable pour la production
Current = version stable avec les nouvelles fonctionnalités
Maintenance = ajouts de correctif supportés jusqu'à une date fixe.

En Node, seule les versions paires deviennent 'Active LTS (Long Term Support)

Note : `Breaking-change`

Tab space 2 ?

- Enoncé dévrouillard => rl.on() serait plus pratique 1er
- Enoncé guidé => rl.question()+ function récursive 2ème


rl.question();  juste pour une questions
rl.on(); autant de réponse jusau'à ce qu'on auitte l'interface


- switch vs if
if : on peut faire plus de logique
switch : on compare qu'un valeur d'un variable, et d'agir si celle-ci match une valeur particulière; 


## `string.split()`

Idée:
- couper une string en plusieurs string
- passer d'un string --> array
 
## !NaN vs. !true vs. ! variable

- `!NaN` = la valeur n'est pas un nombre 不是一個數字 (= Not A Number)
NaN = une valeur spéciale qui représente une quantité qui n'est pas un nombre  NaN的類型是數值，但它不等於任何其他數值，甚至不等於它自己

- JavaScript的條件式if(condition)會根據condition的值是真還是假來執行不同的陳述式1。任何值只要不是false、undefined、null、0、NaN，或者空字串(“”)，並且任何物件，包括其值是false的布林物件，仍然會被條件式視為條件成立

- if(!NaN)的意思是如果NaN是假，則執行後面的陳述式。由於NaN本身就是一個假值，所以!NaN就是真，因此if(!NaN)永遠會執行。
if(!NaN)的情況下可能有兩種用途：

- 一種是想要測試一個變數是否是NaN，並且在不是NaN的時候做一些處理。
- 另一種是想要用一個永遠成立的條件來創造一個無限循環


``js
if (NaN) {
  // 执行不到这里
}
``
- `!true`= false

- !variable // si variable === undefined

- 如果變量是一個數值，那麼 ! variable 會把非零的數值轉換為 false，把零轉換為 true。例如，! 3 等於 false，! 0 等於 true。 (3是真值truthy, 0是假值falsy)
- 如果變量是一個字符串，那麼 ! variable 會把非空的字符串轉換為 false，把空字符串轉換為 true。例如，! “hello” 等於 false，! “” 等於 true。
- 如果變量是一個布爾值，那麼 ! variable 會直接取反。例如，! true 等於 false，! false 等於 true。
- 如果變量是一個對象，那麼 ! variable 會把任何對象轉換為 false。例如，! {name: “Alice”} 等於 false。

[JS equality table](https://dorey.github.io/JavaScript-Equality-Table/)

- 在 JavaScript 中，truthy（真值）指的是在布尔值上下文中，转换后的值为 true 的值。被定义为假值以外的任何值都为真值。
（即所有**除 false、0、-0、0n、""、null、undefined 和 NaN 以外**的皆为真值）。

- 假值 : false, 0, -0, 0n, "", null, undefined, NaN

\d

## strings methodes

Quand on manipule des chaines de caractères, pensez à faire un tour sur l'API strings : 

- `slice()`
- `split()`
- `toLowerCase()`
- `substring()`

## Function récursive

## Function hissée

Une fonction déclarée avec le mot clé ``

## créer un serveur HTTP

HTTP = **protocole** de communication sur Internet
Internet = réseau = cables, les antennes 5G, cable sous la mère
Web = l'ensemble des **ressouces** accessibles via internet. La majorité de ces ressources sont accessibles via HTTP.

ressources = pagesHTML, images, JSON (données), vidéos

## Anatomie d'HTTP

## Requête HTTP

- `URL`
- https://reddit.com/programingHumor
- vocabulaire: protocol://host/path

- `METHOD`
- `GET` pour obtenir de l'information
- `POST` / `PUT`/ `DELETE` / ... => plus tard


`HEADER` :

- idsclamers: pas d'inquietude  

## Et HTTPS dans tous ça ?

- `status code` : indique l'état de la réponse
- 2XX : ok
- 3xx : redirection
- 4xx : erreurs serveur

- body: contient ce que l'utilisateur a demandé
  --

  X-Powered-By: header qui indique généralement la téchnologie derrière le serveur. by Next.js

## HTTPS vs HTTP

Quand on fait une requête HTTP, la requête et la réponse ne sont pas encodé sur le réseau

Une reque^te HTTPS assure que la requête et la réponse sont chiffrés sur le reseau
HTTP


## mon premier serveur dont l'objectif est de répondre "Bonjour"

<!-- ovh 

Du coup, si tu fais un site internet, tu dois obligatoirement acheter une machine ? on loue une partie de machine
acheter un domain
un abonnement
S08 herbergement -->

Ajrd: node:http
lundi: express


step 1 : importer le module http de node

const http = require("http");
console.log(http);

step 2 : conifguer notre serveur

const serveur = http.createServer((request, response)) =>{

console.log(request);

}
// Objectif : créer un premier serveur dont l'objectif est de répondre "Bonjour" !
// Aujourd'hui : node:http
// Lundi : express


## code d'Enzo

```js
// 1. Importer le module http de node 
const http = require("http");


// 2. Configurer notre serveur
const server = http.createServer((request, response) => { // 2 paramètres pour le callback !
  console.log(request);
  response.write("Bonjour"); // On écrit dans le flux de la réponse. Pour l'instant, du texte. Bientôt, du HTML
  response.end(); // On expédie la réponse
}); 


// 3. Lancer notre serveur 
server.listen(3000); // On choisit arbitrairement un port pour écouter les requêtes // Généralement entre 3000 et 10000 // 8080, 3000, 3001, 8000, 5500, ... // Attention, on s'assure que le port n'est pas utilisé par un autre serveur ! 

```

## Serveur

Serveur 

Erreurs classique

Error: listen EADDRINUSE : address already in use :::3000

port 3000 le plus utilisé

avant on utilisait principalement les ports 8000, 8080, ou encore 8888

ut8

Du coup si on avait un fichier html avec dans l'entête le charset, on aurait pas nécessité à ajouter un header dans le fichier du serveur ? oui

## ServeNote de Enzo
https://github.com/O-clock-Gyoza/S03E02-decouverte-node-RED-enzoclock/tree/master/cours


pour check le port 3000 dans le terminal :

``js
netstat -a | grep "3000"
``
## Nodemon


## Node.js HTTP

const http = require("http");

const server = http.createServer();

server.on("request)

https://nodejs.org/en/docs/guides/getting-started-guide



server.listen vs. server.on


 網址的基本組成為：通訊協定、子網域 ( sub domain )、網域 ( domain )、埠號 port、路徑、參數 query

- [wifi to isp to internet backbone](https://www.m3isp.com/wireless.html)
- [submarine cable map](www.submarinecablemap.com)

- traceroute

Terminal下 tracert google.com

=> 


C:\Users\mypu>tracert google.com

Tracing route to google.com [142.250.179.78]
over a maximum of 30 hops:

  1     1 ms     1 ms     8 ms  bbox.lan [192.168.1.254]
  2     4 ms     8 ms     4 ms  176.160.192.3
  3    10 ms     3 ms     3 ms  i15-lef01-t2-62-34-3-167.ft.lns.abo.bbox.fr [62.34.3.167]
  4     7 ms     7 ms     7 ms  be11.cbr01-cro.net.bbox.fr [212.194.171.2]
  5     7 ms     7 ms     6 ms  i15-lef01-t2-62-34-3-228.ft.lns.abo.bbox.fr [62.34.3.228]
  6    12 ms     7 ms    14 ms  72.14.204.68
  7     8 ms    10 ms     8 ms  216.239.40.79
  8     7 ms     6 ms     6 ms  142.251.49.133
  9     5 ms     9 ms     7 ms  par21s19-in-f14.1e100.net [142.250.179.78]

Trace complete.


 Internet backbone

http => scheme
www.xxxx.com => nom de domaine
/path  => chemin
?key  => paramètres
#sdfzer => ancre

![](./img/mdn-url-all.png)



 ## S03E03

gestionnaire de snippets

- Alfred
- Espanso (Linux, Mac, Window)

Au niveau de VScode (intégré

Ctrl +shift+p

-Snippets : configuration User Snippets

recommandation : n'en fait surtout pas pour tout et rien

Ctrl + p : search bar vsCode

## quiz

le contenu de la requête HTTP = body
Les metadonnées de la requête HTTP = header
l'adresse de la requête HTTP = url


J'ai un serveur Node lancé sur le port `3000` sur ma machine, je peux accéder à ce serveur via l'URL :

http://localhost:80/3000 = http:://localhost/3000


## Modules Node : require

- Module natifs (`Core Modules`)
- Module locaux (`Local Modules`)
- Module NPM (`Third Party Modules`)

TODO : extraire ce gros tableau dans son propre fichier, pour ganger de la place

```js
const {hitParade} = require('./index.js'); 
```

- il arrive que dans certains codes il est écrit "import" est ce que c'es la meme chose que require ? Même l'idéé mais Node 80% avec l'ancien syntaxe


const server = http.createServer((req, res) => {
    const pathName = url.parse(req.url, true).pathname;})

res.setHeader("Content-Type", "text/html; charset=utf-8");

c'est possible que ce soit "text/plein

[](http://îconoir.com)

png image sur fond transparent
jpg image lourde photo
svg image vectorisée facile à redimmensionner sans perte de qualité
webp format d'ims plus légér pour le web

image/svg+xml

## insérer un fichier CSS par res.write();
Inséer le haut d'un fichier HTML classique 

favicon => return à la fin pour fermer la fonction

par contre là ce n'est pas le client (personne) qui demande le CSS, mais c'est le navigateur du qui procède automatiquement à la requete ?

Client = navigateur (Client HTTP): outil capable de faire des requêtes HTTP

Le navigateur demande une page HTML - request
Le serveur renovie la page HTML- response si on l'a bien configuré
La page HTML contien une balise link donc le navigatuer va demander la ressource associée - request
le serveur renvoie la ressouce associé (CSS) - REsponse

Donc si on a une connexion pourrie avec beaucoup de ping, c'est possible par exemple qu'une page n'affiche que le HTML d'une page avant de recevoir plus tard le CSS ?


## Module dans Node

3 types de modules :

## core modules (modules natifs) : 

- cryto
- http
- os
- readline
- cf la documentation

```js
const http = require("http");

const http = require("node:http"); //syntaxe plus récente 
```

Où se trouve l'association qui permet d'importer implicitement les modules natifs node dans un fichier ? Elle est codée dans node ou placée dans un fichier caché ? 
Node sait donc directement comment résoudre le chemin de ses propres modules alors ?

```
which node //où est mon node
```

## local modules (modules locaux) :

Ce sont les modules qu'on écrit nous même. En général

1.
fileName.js à la racine
2. exporter les données de notre module

module.exports = hitParade. //un tableau

3. importer les données

const hitParade = require("./fileName"); // hitParade est toujours un tableau.  chemin absolu ici


```js
const fruits = ["kiwi", "Mango", "banane"] 
module.exports = fruits;


const fruitList = require("./......")
```

Dans l'export tu dois pas mettre les () de tes parametres ? Attention : on exort la fonction et non pas l'appel à la fonction !

```js

fucntion sum(a,b)

module.exports =  {
 sum : sum,
 multiply : multiply
}
//= module.exports =  { sum, multiply };

```


const { sum, multiply, firstName } = require("./utils); // 可省略.js firstName = variable

lodash.com

l'export et le module sont à ecrir en bas de page ?


```js
// module.js
const app = {
  firstName: "John",
  sayHello: () => { console.log("Hello") }
}

module.exports = app;
```

```js
// main.js
const { firstName, sayHello } = require("./app");
//                                { ... }

console.log(firstName); // "John"
sayHello();             // "Hello"
```

const app = require("./app"); // app = { ... } !!

## 2 méthodes de résolution d'import

raison: historique. A une époque avant (Node.js), il n'y avait pas d'import en JS
JS, avec ES6 a bien évolué et a intégré un système de module

1. CJS : `module.exports / require` (Common JS)
2. ESM : `import` / `export` (ECMAScript module) => Node v.12 就開始引入ESM寫法: import/export

## Modules tiers 

Registre(annuaire) NPM : gestionnaire de package (modules de Node)

ou se trouve l'annuary ? npm.js
The free npm Registry  

function generateRandomNumber (){
}

randomFloat();

il y a pas plusieurs niveaux de license MIT?
Licence MIT
Taille de package
Date de publication sur Github

il y a des commentaires d'utilisateurs ? pour avoir un retour utilisateur ? nombre d'issues

## Initialiser noter dépôt avec `npm`

Se placer (terminal) dans le dépôt dans lequel on souhaite travailler et lancer
- `npm init`
- Eventuellement `npm init -y` (il accepte tous/s'install tout tout d'un coup)

L'iée : permet ensuite d'installer des packages

## installer un package

- `npm install <domain>chance`

2 choses : 
- `package.json` a changé ("dependencies")

on y retourve la version du package qui a été installée. Permet de -
- `package-lock.json` a été crée/modifié : fix la version "exacte
- `node_modules` (dossier) a été ajouté : notre `require("chance)`

## desinstaller un package

il y aura autant de dossier node modules que de dépendance ? il y a au moins autant de dossier dans les `node_modules`

Si je comprends bien, on installe le module sur chaque projet où l'on souhaite l'utiliser. Pas comme une extension VSC qu'on installe qu'une fois ?oui

Pourrais-tu nous expliquer la syntaxe ci-dessus ? npm init @eslint/config
Pourquoi utilise-t-on ici un '@' pour configurer eslint automatiquement par exemple, et non pas npm install eslint/config ?

## Utiliser le package

Se reférer à la documentation 

```
const Chance = require("chance");


```

npm install cli-color

npm init :créer le package de npm 
npm install : install le module

## `gitignore`

On a ostammé des packages, on les a utilisé, on est content, on aimerait bien commit notre travail !

peter un plan ??

- créer un fichier `.gitignore` dans lequel on rajoute "node_module"

recupérer

npm install (il va aller chercher et installer les dependencies à nouveau)

Les dependances sont téléchargées dans le projet donc ? ce n'est pas comme une extension qui reste sur ton pc ? tout à fiat

le gitignore on le fait pas a chaque fois du coup juste au premier push ?

Les modules nodes natifs sont-ils dans node_modules ou dans l'installation de node ?

Mais ça peut arriver de désintaller un truc. Par exemple par moment, tu vas installer un package qui va te poser des questions en entrée. Par exemple la pour eslint, il te pose des questions sur quel langage tu utilises, dans quel contexte etc. Si tu te gourres dans tes réponses, je suppose qu'il faut désintaller et réinstaller non ? C'est pas un truc classique ça ?

Si tu crées un dossier avec un module local et le places dans node_modules sans le télécharger depuis npm, ça fonctionnera ? pas recoomandé

## recap

package.json => manifest de l'app
npm install => installer toutes les dépenances déclarées dans le package.json

npm init = > créer un package.json si pas présent

npm install <package> => ajouter un nouveau package
`.gitignore` => ne pas commit le dossier node_module
`node_modules` => contient les dépendances tierces installées

correction Enzo S03E03 Exo impaire
https://github.com/O-clock-Gyoza/Ocode-Gyoza/blob/enzo/FS-JS/S03/E03/01.evenOrOdd/01.evenOrOddServer.js


chanllenge
https://kourou.oclock.io/o-challenge/?ref=Ty1jbG9jay1GUy1KUy9ib29rc2hlbGZ8Ty1jbG9jay1HeW96YXxTMDNFMDMtYm9va3NoZWxmfDIwMjMtMTAtMTFUMDk6MDB8


npm: Difay.js

## S03E04

Par exemple, Express et ses templates c'est juste une série de res.write() en coulisses ?
nps express-generator--view=ejs esmApp

{}package.json的dependencies上面加入type: "moduleˇ

## Quiz

Quel module Node je peux utiliser pour créer un serveur web ?
- `os`
- `cli-color`
- `http`
- `random`

```js
const http = require("http");

const http = require("node:http"); // Recente ~14 commence à la supporter. // Objectif : différencier les impots Core Node des Third Party modules
```

Quelle est la syntaxe correcte pour un export ? 
- `module.exports({ age : 42, name: 'John });`
- `module.export = 42;`
- `const exports = ["banana", "kiwi", "mango"]`
- `module.exports = { age: 42, name: 'John' };`


Le `package.json` permet :
- d'installer des packages // npm install => consequence
- de lister les dépendences du projets et les métadonnées du projet
- d'initialiser npm // npm init =>
- de faire les cadeaux de Noël

```js
`npm init -y` : initialiser le projet en créant le package.json
`package.json` : liste les dépendances 

`npm install` : installer TOUTES les dépendances qui sont listées dans le package.json
`npm install <package>` : installer UNE dépendance et la DECLARE (ajoute) dans le package.json
```


Lequel de ces "types" de modules n'existe pas dans node 
- `core modules`
- `third party modules` => qu'in trouve sur NPM
- `local modules`
- `require modules` => require permet de fiare des imports


Le `.gitignore` permet 
- aux autres développeurs d'installer les dépendances du projet => npm install avec le package.json
- de ne pas versionner certains fichiers et dossiers = en particulier les node modules qui pèse lourd
- de retirer complètement git du projet
- de se la péter : personne n'a vraiment jamais su ce que ça faisait

## correction du challenge Day.js

if(){return;}

Early return
clause de garde

## boyscoot

const http = require('node:http');

const books = require("./books"); // [{}, {}, {}]

const server = http.createServer((req, res) => {

  if (req.url === '/favicon.ico') { // On court-circuite l'appel automatique du navigateur au favicon.ico
    res.writeHead(200, { 'Content-Type': 'image/x-icon' }); // Ici, on fait semblant d'envoyer une image
    res.end();
    return; // Early return / clause de garde
  }

  res.writeHead(200, { 'Content-Type': 'text/html; charset=utf-8' }); // On envoie les header de la réponse http. Ici nous voulons une réponse de type text encodé en UTF-8
  res.write('<!DOCTYPE html><html lang="en"><head><meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0"><meta http-equiv="X-UA-Compatible" content="ie=edge">    <title>Document</title></head><body>'); // On écrit l'entête de notre page html
  res.write('<p>REMPLIR ICI</p>'); // Corps de la page
  res.write('</body></html>'); // On écrit le pied de page de notre page html
  res.end(); // On à fini d'envoyer nos informations au client
});

server.listen(3000, () => {
  console.log("Listening at http://localhost:3000");
});


module.exports

const books = require(./books)


Comment faire un tableau avec JS ?
table>
thr

${buildTableBody();}


function buildTableBody() {
  return `<tr>
    <td>Titre 1</td>
    <td>Auteur 1</td>
    <td>Pays 1</td>
    <td>Langue 1</td>
    <td>Date 1</td>
  </tr>

  <tr>
    <td>Titre 2</td>
    <td>Auteur 2</td>
    <td>Pays 2</td>
    <td>Langue 2</td>
    <td>Date 2</td>
  </tr>`;
}

on créer une variable `res`
Pour chaque book, on rajoute le <tr> du book !

let res = "";

books.forEach((book)=>{
const tr = `
<tr>
 <td>${book.title}</td>



`;
res +=tr;



});

return res;


crire par map

const trArray = books.map(book)=> {
return `
   <tr>
      <td>${book.title}</td>
      <td>${book.author}</td>
      <td>${book.country}</td>
      <td>${book.language}</td>
      <td>${book.date}</td>
    </tr>`;

return trArray.join("");
  });





1. npm init

git commit => push

2. npm install dayjs => dependencies
npm i dayjs

3. créer le gitignore

du sucre syntaxique 

4. Display > format

const dayjs = require("dayjs");
dayjs().format

<dayjs(book.date)>.format("dddd")

advanced format (pluggin)

all time zones
https://gist.github.com/diogocapela/12c6617fc87607d11fd62d2a4f42b02a

// Ajout du pluging advancedFormat pour dayjs
const advancedFormat = require('dayjs/plugin/advancedFormat');
dayjs.extend(advancedFormat);


// Bonus 1 : afficher la date en FR
i18n = internationalization(" internationalisation is 18 letters between i and n ")
`locale`= langue locale


JS : Intl.DateTimeFormat

## Une librairie JS native qui permet de générer le formatage des nombres, dates, prix, etc.. en JS natif !

const formatedDate = new Intl.DateTimeFormat('fr-FR', { dateStyle: 'full', timeZone: 'Europe/Paris' }).format(new Date(book.date));

Vérifier avant le support de la fonction que vous souhaitez utiliser dans la DOC
https://developer.mozilla.org/fr/docs/Web/JavaScript/Reference/Global_Objects/Intl

## avant d'installer un module iter (`dayjs`), ça vaut le coup de regarder si JS ne supoprte pas de manière simple (relatif) ce que vous chercher à fiare.

cosnt date = new Date();

// Bonus 2 : afficher l'age du livre

// Bonus 3 : trier les livres par date de parution

Array.sort()
toSorted

- Elle est ìn place : elle modifie drectement l'array sur laquelle on l'appelle (en effet de bord)

Si on l'utilise telle qu'elle, elle ne marche qu'avec les strings



// Bonus 4 : extraire la construction du tableau dans un module

une route parametrer

app.get("/fleur/:flowerName")

console.log(req.params.flowerName)

## S03E05

- [ ] fichier sans extension

https://github.com/O-clock-Gyoza/S03E05-decouverte-node-RED-enzoclock

EJS => pour écrire du JS dans du HTML

`partials`

Extension EJS pour VSCode

https://github.com/O-clock-Gyoza/S03-o-recipes-enzoclock-CORRECTION

Express support JSON (pas besoin d'exporter la valeur qui se trouve dedans)

JSON:
format obligatoire:
[
  {
  "nom_du_clé" : .....

},
]

Pas de commentaire

killall node

## EJS
Embbed Javascript Template 
- Un moteur de template pur Node.js qui s'intègre très facilement avec `Express`
- Un outil pour renvoyer du HTML de manière simple
- intégrer du JS dans une page HTML

npm install ejs
app.use("view engine", "ejs"); //on indique le view engine qu'on souhaite
app.use("views", "chemin_relatif_vers_les_vues)


setup EJS

```js
/ Import express
const express = require("express");

// Create app
const app = express();

// Configurer le view engine
app.set("view engine", "ejs"); // On indique le view engine qu'on souhaite utiliser. Pas besoin de require !
app.set("views", "./views");

// Configure app
app.get("/", (req, res) => {
  res.render("home"); // On render le fichier "home" qui se trouve dans le dossier 'views'
});

// Start app
const port = 3000;
app.listen(port, () => {
  console.log(`Server listening at http://localhost:${port}`);
});


Page recette

Passer des données depuis le touter JS vers le fichier EJS
-`res.render("nom_de_la_vue)`
res.render("render", { allRecipes: allRecipes, data: "toto" });
          ^^^^^^^^^^^^
         match /views/recipes.ejs
et dans le fichier .js il faut que ce soit entre { } pour pouvoir l'utiliser dans le fichier .ejs du coup ? dans le Render ?

<% JS %> pour encadrer le JS
<%= variable %> = ${ variable}

<% allRecipes.forEach((recipe))>

`ejsout`
`ejseach`


dans le dossier views

partials


```
J'ai utilisé pug pour le challenge car je pensais qu'on ne peut pas inclure de partials avec EJS. Bien sûr l'indentation m'a fait pété un plomb et il n'existe pas de plugin d'intentation automatique qui fonctionne bien . Si j'avais su qu'EJS peut faire ça aussi j'aurais gagné 1h`
C'est un peu bizarre l'état des view template engines actuellement. 
EJS n'a pas de layout, et pug n'est pas mis à jour depuis 2021, mais pas vraiment déprécié non plus. 

Je sais pas trop lequel utiliser`

on peut mettre de la syntaxe ejs dans les partials? oui

doc on EJS
- https://github.com/mde/ejs/blob/main/docs/syntax.md

- http://web.gregory-bourguin.fr/teaching/node/express#express

CSS => rajouter un dossier que l'on va servir statiquement `public`

app.use(express.static("./public")); tous les fichiers qui sont dans le dossier public seront accessible deirectement via leur nom par le serveur

pexels

https://pixabay.com/fr/

unsplash

librairie CSS : (moins pousé que BS5 )
picocss


## MiddleWare

comparaison
- find(); 
- join();  array => String
- find();  il faut que la fonction retourne true ou false  array => element de l'array
- forEach(); Itère sur l'array

 :emoi:On peut enchainer ces arguments ? .find + .filter etc...? Oui

 lien de depôt 
https://github.com/O-clock-Gyoza/S03-atelier-gamehub-RED-enzoclock

créer un fichier par touch


installation des dépendances

- npm install -g nodemon  (installer le paclage en global sur ma machine, dans tous les projets, on peut s'en servir)
- Avantage: pratique pour aller vite !
- inconvénient: si on clone le projet, par sûr de pouvoir utiliser la dépendance sans l'installer

npm install --save-dev package
installer le package dans 


et il faut l'ajouter au gitiniore? les dependances dev

une fois le projet terminé tu supprime les dépendances de dev ? Pas du tout


# Installations des dépendances

- `npm install <package>` 
  - installer le package dans les `node_modules` du **projet**

- `npm install -g <package>`
  - installer le package en **global** sur ma machine
  - dans tous les projets, on peut s'en servir 
  - avantage : pratique pour aller vite !
  - **inconvénient** : si on clone le projet, pas sûr de pouvoir utiliser la dépendance sans l'installer !

- `npm install --save-dev <package>` : 
  - installer le package dans les `node_modules` du **projet**
  - en précisant que c'est un package qui nous sert uniquement lorsqu'on **développe** le projet


Exemple : 
  - `nodemon` nous sert que pendant le developpement ! 
  - ==> `npm install --save-dev nodemon`
  - Même si on a déjà nodemon en global, ça vaut le coup de le déclarer dans le projet, pour faciliter la prise en main de notre projet par un(e) dev tier.

- configuration du dossier public
```js
app.use(express.static(__dirname + '/public')); atelier
app.use("/static", express.static("./public")); Anthony
app.use("/public", express.static("./public")); Enzo correction
```



L'idée : 

- importer des dionnées depuis le fichier `js`
- passage des données en deuxième argument du 


L'idée : 
- import des données depuis le fichier `js`
- passage des données en deuxième argument du `res.render("VIEW", { data })`
- tester qu'on récupère bien les données côté de la view (ex: `JSON.stringify(data)`) !

prompt arrive avant => setTimeOut

ejs if test variable 


const { } = req.params


sucre synthétique :
if (local.game && locals.game.jsFile) = if  (local.game?.jsFile)

script src= "/public/js/"

bonus 
problème => la majorité des jeux on un HTML spécifique

On pourra pas avoir 1 seul game.ejs
On pourra avoir une game.ejs qui gère le tout + des fichiers qpécifiques pour chaque game

- prefer duplication over the wrong abstraction


outil 

"script"{
  "dev":"nodemon index.js",
  "start":"node index.js"
},

Terminal:
npm run dev
npm run start

npm run start = yarn

npm != yarn != pnpm

## yarn et pnpm sont des surcouche à npm : c'est la même chose, avec des fonctions

script npm
Dans le package.json, on peut ajouter des scripts en leur donnant un nome dans le but de:
pour un dev qui clone le projet, il saura au moins comment le lancer

Si le script s'appelle build, alors on le lancerait avec npm run build

le locals vie uniquement dans app.get?

On aimerais faire en sorte que pour toutes les requetes

app.use((req, res, next)=>{

console.log("hello");
res.locals.games = games


})

locals c'est les données accessible dans toutes les views

router.use


## Middleware

Ex de middleware


```js
app.use((req, res, next) =>{
 console.log("hello");
 next();
})
```

Les requêtes traversent les middlewares de notre application dans l'ordre dans lequel ils sont déclarés.

Note : nos routes sont des middlewares


## 

Un app.get(URL, CALLBack) est un app.use particulier qui fait la chose suivante
- si 

## les locals 
- sont une variable (rangées dans res.locals) qui est accessible depuis les views EJS
- si on met une variable dans `res.lcoals` alors on y aura accès dans une vue.
C'est  une sorte

ex2. un filtre à IP

idée: on veut bloquer l'accès à notre app 

app.use((req, res, next)) => {



}

## Architecture idéale



app.use("404", ())


你的問題是關於express.static這個函數，它是Express框架中的一個內置中間件函數，用於提供靜態文件，比如圖片、CSS文件和JavaScript文件1。它的語法是：

express.static(root, [options])

其中，root參數指定了提供靜態文件的根目錄1。options參數是一個可選的對象，可以設置一些配置選項1。

你的代碼中，app.use是一個用於添加中間件函數的方法2。它的第一個參數可以是一個路徑前綴，用於指定匹配的URL2。如果沒有提供路徑前綴，則默認匹配所有的URL2。

所以，你的代碼中的兩種寫法都是可以的，但是有一些區別：

app.use(“static”, express.static(“./public”))表示只有以/static開頭的URL才會匹配到public目錄下的靜態文件。比如，如果public目錄下有一個image.jpg文件，那麼你可以通過http://localhost:3000/static/image.jpg來訪問它。
app.use(express.static(_dirname+“/public”))表示所有的URL都會匹配到__dirname+“/public"目錄下的靜態文件。這裡的__dirname是一個Node.js中的全局變量，表示當前模塊所在的目錄3。比如，如果__dirname+”/public"目錄下有一個image.jpg文件，那麼你可以通過http://localhost:3000/image.jpg來訪問它。

## S03E08

Quiz

un fichier qui repertoirie toutes les routes de mon applciation =>`router.js`
d'arrêter la requête => il suffit d'y répondre res.end()) res.send() res.render()

Cannot GET /inconnue  par défault

cdn = content delivery network = un ensemble de serveur répartis géographiquement à divers point pour optimiser le temps de réponse d'une requête, généralement vers des des fichiers statiques !


## Jouranlisation (logging in English)

Objectif : monitorer le traffic du serveur. Côté backend uniquement. L'utilis

// J'aurais tendance à également journaliser les appels aux routes statiques afin de vérifier le traffic sur mon site web ! (pourquoi pas !)


il faut reconstruire les views = > cette opération est plus long

il existe des middlewares de journalisation prê à l'emploi
- winston
- morgan

## extraire les middleware dans une fonction ?

## God files

Gros fichiers qui contiennent trop de code et trop de responsabilité. On évite car c'est difficile à maintenir:
- si plusieurs dev bossent en parallèle sur le même fichier => conflits lorqu'on rassemble le tout.
- plus dur 

const express = require("express");

cosnt router = express.Router();


module.exports = router;



Deuxime d

On pourrait avoir un contrôleur par routes "principales" genre : 
/games/... => controler games
/profils/... => controler profils 
Etc.. 


On pourrait avoir un contrôleur par routes "principales" genre : 
/games/... => controler games
/profils/... => controler profils 
Etc.. 

## Nouvelle fonctionnalité 1 : 
Dans la home page, on rajoute cette barre de recherche
- Lorsqu'on valide, l'application nous redireige vers la route `/games` (qui n'existe pas encore)
- On aimerait que cette route `/games` liste les jeux correspondants à la requête

## Fonctionnalité 2 : ajouter une (fausse) zone de connextion pour que l'utilisateur choisisisse sont peudo


html: 
Le `for` du `label` et le `id` du `input` doivent label input 
les lier

Appuyer sur le `button` ou la touche `ENTER` déclenche un évenement `submit`, dont la conséquence est de déclencher une requête 



```js

form 



```
-methode : choix du verbe de la requête HTTP
par défaut, si on met rien, `GET`
-Action : choix de l'url de la requête HTTP
par défaut, si on met rien , 

unexpected token = problème de syntaxe

EJS
<%  : javascript en arriere plan
<%=  : renvoie la valeur entre guillemets
<%- : renvoie la valeur sans décorations

if ( true || searchTerm)

sort=off
sort=on

sort {
if compare return 1;
if compare return -1



}


req.query

## fonctionnalité du faux signup

coté client:
notre formulaire: form
methode=POST 
input name => post, les données passent par le body de la requête


Keypass
GooglePasswordManager

côté serveur

Configuration 

router.post("/signup", mainController.signupUser)


"body parser : un middleware capable d'extraire le body d'une requête HTTP et de l'ajouter 

S05 authenficitation des comptes


https://github.com/O-clock-Gyoza/S03-atelier-gamehub-RED-enzoclock

https://github.com/O-clock-Gyoza/S03-index/tree/main

Quand tu as un texte dans ton JSON. Genre une bio. Comment tu fais pour faire un saut de page dans ton texte. J'ai essayé \n ou <br> dans le JSON mais cela fonctionne pas

{
    "texte": "Ceci est la première ligne.\nCeci est la seconde ligne."
}

<iframe>

par défaut c'est autorisé ou refusé avec express? par defaut c'est interdit


## S03 Bilan


bonus bonus algo
<%=article.text.split(" ", 30).join(' ')%>
<%= article.text.split(/\s+/).slice(0, 30).join(" "); %>


https://blog.pleets.org/img/articles/array-methods-javascript.jpeg


requête du client -> réponse du serveur liée à la requête 

get-post : methodes http

routage => requête caractérisée par Methode + URL

CRUD
interaction client /server
request / response = 1req (client->server) ===1res (server-> client)
port

Ejs = res.render()=> construire une page HTML à partir d'un template EJS + données fournies
Partials = modularisation
locals = données disponibles globalement (accès dans les views EJS) au sein du serveur

Et on peut même utiliser la même view EJS pour plusieurs pages de notre application



## app.local et res.local ?

dossier statique = dossier au sein du serveur qui est public= si on a l'url d'une ressource dans ce dossier, on peut y accéder librement
`npm init` => générer un package Json qui sera la carte d'identité de notre projet => contient la liste des modules externes
`npm install` installer les dépendences d'un projet (s'il estiste un package json)
`npm install nom_du_package` ajoute le package à la liste de dépendances + l'install au sein du projet

## express
Un framework nodeJs pour le Web
abstraction du code NodeJS => permet de faire les mêmes choses bcp plus simplement


## Middleware
?? => fonction qui intervient (ou pas) dans le traitement d'une requête
next() => invoque le MW suivant en lui passant le objets `req` et `res`


Forms
2 méthodes pour envoyer les résultats d'un formulaire HTML
GET = les résultats seront intégrés à l'url => donc visibles
POST = les résultats sont dans le `body` de la requête et de quantité de données acceptées

BODY +> REQ.BODY mais nécessite un middleware pour le décoder ('express.urlencoded( {extended : true}'))


surement il doit y avoir une taille maximale pour le body, faut check, environ 2KB

monsite.com/recettes/crepesausucre
monsite.com/recettes/soupepotiron

req.params  => route.get("recettes/:nomrecette)


monsite.com/recettes/crepes?theme=dark

req.params  => route.get("recettes/:nomrecette) {

   if (req.query.user){


   }


}

https://www.lemahieu.com/t-shirts-homme-coton-bio/941-t-shirt-leger-limpactant.html#/8-couleur-blanc/3-taille-l

Autres exemples :

- monsite.com/recettes/crepe --> page recette crepe

- monsite.com/recettes/soupe --> page recette soupe

- monsite.com/recettes --> page DES recettes

- monsite.com/recettes?ingredients=oeuf --> page DES recettes mais uniquement avec les recettes qui contiennent des oeufs

- monsite.com/recettes?max-duration=60 --> page DES reccette mais unqiuement avec les recettes qui durent moins de 60 min


L'idée : quand on veut la MEME page mais avec des infos différences, on utilise souvent des query params


Planning S04 : 

- S04E01: Gestion de projet & architecture
- S04E02: SGBD, MCD, MLD, Postgres, SQL & client Express
- S04E03: Postgres en local

- S04E04: Sur-apprentissage Postgres/Express (+ async/await & dataMapper)
- S04E05: Sécurité, Session & Cookies

- S04E06 Atelier Pair-programming
- S04E07: Correction Atelier (+ Associations & Jointures)
- S04E08: Agrégations

- S04E09: La pause "SEO" 
- S04E10: Atelier Solo & Vera-cruz
- S04E11: Journée révision

## express static

https://gist.github.com/enzoclock/6295131aee5666cb94bf11af5ec865d0


question pdt l'entretien?

- Pourquoi avez-vous retenu ma candidature ? 
- Comment se déroule la période d'intégration au sein de l'entreprise
- Pourriez-vous me donner de la visibilité sur les missions pour le poste?

Savoir se vendre:

Situation: Quel était le contexte de l'expérience passée?
Tâche: Quel était l'objectif à atteindre?
Action : Quelles actions a-t-il mises en place?
Résultat: Quels sont les résultats obtenus?


"passionné par les métiers de la vente, autonome et rigoureux, je suis à la recherche d'une alternancedans une entreprise à taille humaine PME ou startup sur un poste de business développeur"

Astuces pour décrocher un stage :

1. envoyer un cv personalisé  mot de clé pour le poste
2. mails spontanés: LM
3. Soft skills
4. Audace: pensez aux candidatures spontanées: objectif RDV
5. Homework : 


## Atelier CV

Les plateformes recommandées

- créer uncv (https://www.creeruncv.com/)
- Canva
- europass
- https://www.cvmotivationnel.com/

### Les informations essentielles

- un titre clair

ex: 

x Développeur Web et web mobile Junior
\_Développeur Web font end + spé\_
Développeur Web back end + spé
Développeur Web full stack + spé
Développeuse

- une accroche impactante
- Des coordonnées faciles d'accès
- Des hard skills
- Des soft skills
- Des centres d'intérêts précis
- Une partie formation
- Des expériences détaillées
- 1 page, pas plus
- l'orthographe, un point à ne pas négliger

on détaillera uniquement sur les compétences transverse et si trop d’expériences on ne mettra que les dernière ou les plus pertinente
sur Canva, on peut faire ça aussi pour la photo d'identité
https://www.remove.bg/fr

On fait 3 cv et on distribue en fonction des demande ? 20 modèles diiférents

### Une accroche impactante

racontez nous une histoire

- Pourquoi le dév?
- Mettre en avant une ou plusieurs qualités/compétences
- concis et précis
- 5 ou 6 lignes
- 2 ou 3 phrases
- Préciser ce que l'on recherche à la fin de cette partie


J'avais participé à la réunion CV de l'alternance et la dame nous avait dit :

- ignorer toute l'expérience précédente
- mettre une intro avec les dates recherchées
- mettre le titre de la certification
- indiquer la RQTH au choix

https://immersion-facile.beta.gouv.fr/recherche


- Prénom et Nom
- Code postal + Ville
- Numéro de téléphone
- Adresse email (pro)
- Lien vers profil Github + LinkedIn
- Lien vers site ou portfolio si existent

- Le permis et l'âge ne sont pas obligatoires
- quid des personnes qui ont une RQTH


Paris (253 rue du Faubourg St-Martin 75010 Paris) c'est les adresses des lieux de passages TP, mais pas encore de localisation exact

### hard skills

Exemple de compétences techniques : 

- Intégration Web
HTML5, CSS3, SCSS (SASS) selon les bonnes pratiques d’accessibilité (W3C, RGAA)


- Développement Frontend
ReactJS, Redux, JavaScript Vanilla

- Développement Backend
Framework  Symfony
PHP (Orienté objet, MVC, API Rest, MySQL)

- Gestion de projet numérique
Rédaction d’un cahier de charges, suivi technique, wireframes et user stories, versioning avec Git/GitHub
(pour que vous puissiez le cc)

- HTML
- CSS
- PHP
- Javascript
- MySQL
- Github
- Symfony

### soft skills
https://www.orientaction-groupe.com/test-gratuit-soft-skills-competences-douces/?at_medium=microsoftads&at_campaign=search_soft_skills&msclkid=c54741fe9ca1159044e824c91fa39192

- amélioration continue
- le fait qu'on peut télétravailler

### loisir
Jeu de rôle, tu peux parce que imagination / coopération / Sociabilité

### Formation
exemple pour cc au besoin (à modifier) :
Formation Développeur Web et Web Mobile - Titre professionnel Niveau V
École O’clock - Formation en Téléprésentiel
De {...} à {...}
798 h intensives
-> 3 mois de Socle: HTML5/CSS3/PHP/Javascript
-> 1 mois de spécialisation en {...}
-> 1 mois de projet


### expérience

- Lister les expériences dans l'ordre chronologique inversé, la plus ancienne en bas, la plus récente en haut.

- Préciser le poste, l'entreprise, le leiu et date si besoin. Lister les missions qui peuvent être mises en lioen avec le métier de développeur web.

- Présenter et détailler l'apothéose (projet de fin formation)

- Mettre en avant les compétences "positives".

exemple pour l'apo : 
- Développeur Web PHP

Ecole O'clock - Projet  de fin de formation - dates
Réalisation d'une application web en équipe, de sa conception, jusqu'au déploiement d'un MVP en méthodologie agile.


- donne moi une liste des compétences commune entre le poste d'une vendeuse et une développeurse 

- consulter les compétences transversale parmi les cv, les offres

- mot clé en gras

en gros le nom de l'entreprise et en liste en dessous les compétences tranversales?

Titre de poste
Date
compétence transversale & soft skills professionnel  


## orthographe

Utilisation d'un correcteur en ligne:

- Bonpatron
- Scribens
- Merci-app

https://www.merci-app.com/
https://bonpatron.com/fr/
https://www.scribens.fr/

ce sera pas long du coup, ça te fera deux blocs et tu mets 5-6 compétences transversales


Pas la peine du coup de le faire en site static avec qr code ?

### Les mots clés

- Des mots clés propores au métier
- Des qualités humaines ou techniques recherchées par l'entreprise
- Des informations importantes sur l'offre

## Un CV coloré mais sobre

https://colorable.jxnblk.com

niveau de langes:

https://www.coe.int/fr/web/common-european-framework-reference-languages/table-1-cefr-3.3-common-reference-levels-global-scale

- développeur javascript react


dscription

Le projet

Technologies utilisée

talent individule

formation


liké les entreprises qui nous intéresse
example: 
https://www.linkedin.com/in/remimeullemeestre/

tuto
https://www.linkedin.com/learning/creer-un-profil-linkedin-efficace/presenter-ses-projets?resume=false

## LinkedIn
- Communiquer ses coordonnés
- Changer son titre de poste
- Personnaliser son URL

- Créer un résumé de Profil
- Afficher son expérience professionnelle
- Utiliser le profil Éducation
- Demander des approbations (ajouter des compétences)
- Evaluer ses compétences

- L'ebook pro
https://drive.google.com/file/d/1ax0c8jY8wwkznrR03U7NTHmVDVMMt6_R/view?pli=1

- Deamnde de relecture
https://docs.google.com/forms/d/14xQQ6VAIwbGYkSFgcdU-jA9KaoRxAGWF0PSA0XXR_m8/viewform?edit_requested=true&pli=1



canaux slack : evenements-emploi, jai-trouvé

