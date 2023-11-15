## Tableau = Array
                    
```
const details = (["homme", ["sam", "dujean", 33, "dijon"]]);
            
details[1][3][0]; // "d" 也可以取值
            

```
            
- [ ] groupe rouge
création, 
lecture, 
modification, 
suppression (CRUD)
            
        
## Exos2 

const listeFruits = ['cerise', 'raisin', 'brugnions', 'pommes'];

listeFruits.push('kiwi');
console.log(listeFruits[1]);
listeFruits[2] = 'banane';
console.log(listeFruits);
            
            
- array.splice(index, howmany, item1, ....., itemX)
            
The **shift()** method removes the first item of an array.
            
The **reverse()** method reverses the order of the elements in an array.

The reverse() method overwrites the original array.
- [ ] Array.length();

## boucle
            
- [ ] while, for, for of

while (condition) { action };
for (let index = 0; index < Array.length-1 ; index++){action};
                                          
for (dans le tableau)
                                          
- [ ] git graph
                                          
let i = 0 ;

while (i < 10) {
  console.log(i);
  i++;
}


for (let count = 0; count < 10; count+= 2) {
  console.log(count);
}

const listeFruits = ['cerise', 'raisin', 'brugnions', 'pommes'];
for (let fruit = 0; fruit < listeFruits.length-1 ; fruit++ ) {
  console.log(listeFruits[fruit]);
}
- Erreur: pouquoi ça ne marche pas?
let fruit = 0;
listeFruits.forEach(['cerise', 'raisin', 'brugnions', 'pommes']
{
  console.log(listeFruits[fruit]))
}
  
- [ ] erreur2: let count = 0;

// while (count < 50) {
//   count = count++;
//   count*2;
//   console.log(count);
// }, 10

            
            

while (message != "oui"){
  message = prompt('ça va?')
}
                     
                     
number = parseint en base 10
                     
Littéraux de gabarit
- [ ] revoir while if 
- [ ] typeOf nous retourner le type de variable en enchaine de character
          
                     
- [ ] - > 5 paramètres = il y a un truc à optimiser    
            
- La valeur de retour
            
            

function multiply(nb1, nb2) {
    let resultat = nb1 * nb2;
    return resultat;
}

const re = multiply(3, 4);




- [] object
            
clé:proprité
```JS
const giraffe = {

    nom: 'Sophie',
    taille: 400,
    region: 'Kenya',
    espece: 'giraffe',
    arbresPreferes: ['palmiers', 'baobab'],
}
```
            
```JS
const encoreLaMemePhrase = giraffe['nom'] + ' la ' + giraffe['espece'];
const memePhrase = giraffe.nom + ' la ' + giraffe.espece; 
const phrase = `${giraffe.nom} la ${giraffe.espece}`   
 
```    
            
Sur le challenge d'hier c'est nous qui décidons le plage entre 10 et 20. C'est possible que ce soit le joueur  qui décide le plage pour le jeu? Par exemple  on demande la fonction generateRandomNumber(); de sortir un chiffre entre 30 ou 50 (comme choisi par le joueur)?
   

            
            
            
            
            
- document
            
- [ ] /n 換行
            
## Le DOM

Le dom (Document Object Model) est un grand objet qui contient tout ce qui est affiché dans notre fenêtre de navigation

Lorsqu'on manipule le DOM, on ajoute des éléments au navigateur à l'instant, (pas aux fichiers comme index.html ou index.js ..)

- il nous permet de récupérér des éléments (document.querySelector)

```js
    // imaginons qu'on veuille récupérer le titre de la page
    let titleElem = document.querySelector('h1');
```

- il nous permet de modifier les éléments créés ou venant du DOM 

  ```js
    titleElem.textContent = "nouveau texte";
  ```

- il nous permet de créer des éléments (document.createElement)

```js
    // imaginons qu'on veuille créer une div
    let divElem = document.createElement('div')
```

- il nous permet d'ajouter des éléments au document (ou DOM) (document.appendChild)

```js
    // divElem vient d'être créé, on va l'ajouter au dom
    document.body.appendChild(divElem);
    // à noter qu'on peut aussi ajouter à un élément enfant à n'importe quel élément
    let titleElem = document.querySelector('h1');
    // on peut ajouter une div à notre élément h1 : 
    titleElem.appendChild(divElem);
```

Tous les éléments du DOM possèdent des méthodes et propriétés enc ommun

## propriétés d'un élément (informations d'un élément)


### id 

id est une propriété d'un élément qui permet de définir l'id de celui-ci

```js
    let divElem = document.querySelector('div');
    divElem.id = "score";

```

### innerHTML

- innerHTML est une propriété dans chauqe élément qui nous permet de modifier l'intérieur de l'html de cet élément 
- /!\ à utiliser avec précaution, ça peut créer des pbs de sécurité

```js
let titleElem = document.querySelector('.title');
titleElem.innerHTML = "<span class="otitle">O'</span> <span>NEWS</span>"
```
### textContent

textContent est une propriété qui permet de changer le texte d'un élément
```js
titleElem.textContent = "hello";
```

## méthodes d'un élément

### querySelector - querySelectorAll

querySelector permet de récupérer des éléments via un selecteur css, on peut être aussi précis dans nos selections que sur nos fichiers css 
- on peut chercher des éléments
- on peut chercher des id
- on peut chercher des classes
- on peut utiliser tous les symboles des selecteurs css
- querySelector nous renvoie le premier élément trouvé qui correspond à notre recherche
- querySelectorAll nous renvoie un tableau d'éléments qui correspondent à notre recherche
  - /!\ on recevra bien un TABLEAU d'éléments

### classList

permet d'ajouter une / des classes à un élément 

ex : 
```js
    let divElem = document.createElement('div'); // ici une div a été crée, et elle est stockée dans divElem
    divElem.classList.add('number-list'); // on attribue une classe à notre élément

```

### appendChild

- appendChild permet de rajouter un élément enfant à un élément
- si il y a plusieurs éléments enfant, l'élément sera ajouté à la fin

```js
    let containerElem = document.querySelector('#container');
    let divElem = document.createElement('div'); // ici une div a été crée, et elle est stockée dans divElem
    containerElem.appendChild(divElem);

```

## Méthodes

Les méthodes sont des fonctions dans un objet, on en utilise depuis le début de la saison

ex : 

```js

const objet = {

    text: "plop", // dans un objet on trouve des propriétés liées à des valeurs

    sayHello() { // ou des méthodes
        console.log("hello");
    },

    sayHi() {
        console.log("hi");
    },

    writeMessage(msg) {
        console.log(msg);
    }
}

objet.sayHello();
objet.sayHi();
objet.writeMessage("hola");

```
            
            
            
            
createElement
textContent
AppendChild
            classList.add('class_name')
            
            
            let count = 0 ;
            
            while (count < 10){
        
let divElem = document.createElement('div');
                               divElem.textContent = count;
                               container
                               
                               }
                               
                               
- il faut installer eslintrc
                               
## S02E05

JS exercise
https://jsfiddle.net/user/PLKJS

- [ ] git bash
                                          
- [ ] addEvent
                               
// ici on déclare notre callback, qui est une fonction qui recoit en paramètre un event (un event est un regroupement d'information sur l'event qui vient d'a voir lieu)
function handleClickOnPage(event) {
    console.log(event);
    event.target.style.backgroundColor = '#f0f'
}



// on va écouter les clics sur toute la page

// addEventListener attend 2 informations pour fonctionner : 
// 1 - le type d'évènements (ici 'click')
// 2 - le callback (ou la fonction qui va être la réaction à l'évènement)
document.addEventListener('click', handleClickOnPage);

    Lundi
                -querySelector
                -addEventListener
                -Objets
                Functions
                elements: creatElement, modif proprietes
                boucles
                innerHTML
                -formulaire
- [ ] event.preventDefault(){}
                
- [ ] Select parent element for addEventListener on each child ? ex Fruit
               
                
                
- [ ]                 https://gojs.net/latest/samples/flowchart.html
                
- [ ] Le textContent marche pas sur un input, c'est sur un button plutôt non ?
- [ ] dvh: dynamic viewport hight
                               
- [ ] className ça remplace
          
## 老師筆記
                               
## camelCase

Syntaxe où chaque mot est séparé par une majuscule
Le premier mot n'a pas de majuscule

```js
const exempleDeNomDeVariable = '';
```

## kebab-case

Syntaxe non utilisée en js mais utilisée en HTML où on sépare chaque mot par un tiret 

```html
    nom-de-variable
```


## dataset

Les balises HTML peuvent contenir des informations, ces infos pourront être récupérées côté JS, ce qui pourra nous être utile

```html
    <div data-user-name="michel" data-user-pseudo="Xxx-michel-xxX" >hello</div>
```

Côté html, ces propriétés sont écrites en kebab-case ET commencent toujours par le mot clé `data`


On peut récupérer ces données côté JS :

```js
let divElem = document.querySelector('div');
// on peut maintenant récupérer les données du dataset
console.log(divElem.dataset.userName);
console.log(divElem.dataset.userPseudo);
```

Côté js les données sont stockée dans la propriété dataset, elles sont converties en camelCase et on a retiré le mot clé data
                               
- test title

  您想知道如何用 querySelector 或 querySelectorAll 綁定第2個元素，以及這兩個方法有什麼差別。我為您找到了一些相關的資訊：

  - querySelector 方法會返回文檔中符合指定選擇器或選擇器組的第一個元素，如果沒有找到匹配的元素，則返回 null1。

  - querySelectorAll 方法會返回文檔中符合指定選擇器或選擇器組的所有元素的靜態 NodeList，如果沒有找到匹配的元素，則返回空的 NodeList2。

  - 如果您想綁定第2個元素，您可以使用 CSS 的 nth-child 伪類選擇器，例如 document.querySelector("div:nth-child(2)") 會返回第2個 div 元素3。

  - 如果您想綁定多個不相關的元素，您可以使用逗號分隔的選擇器組，例如 document.querySelectorAll("form, p, legend") 會返回所有的 form、p 和 legend 元素3。
                
ScreenBrush (mac)
                
https://github.com/O-clock-Gyoza/S02E08-decouverte-js-RED-enzoclock    
              
## Histoire de JavaScript

- eslint              
  - faire n'importe de quoi sur annontation: typehinting de 
  - survole une function
- 1995 : LveScript
- 1996 : Javascript
- 1997 : ECMAScript
- 2003 : ES3  
                              
- 2005 : JQuery,  **librairie** la plus populaire en JS
  - même aujoud'hui ( car beaucoup de "code legacy")
  -l'objectif: harmoniser l'API du DOM = harmoniser l'ensemble des fonctions disponsibles dans le DOM
  -                             
- 2009 : Node.js : **runtime** Javascript (côté serveur) 
  - "coté serveur" Ryan Dahl
  - avec Node.js, on popularise une nouvelle syntaxe pour les modules  en JS.
  - `module`= un bout de code dans un autre fichier - également une syntawe de type `ìmport/export` avec `module.exports/require`
  - différence module vs librairie
  - s'inspire beaucoup depuis ES6 sur sa syntaxe

- 2012 : TypeScript : du JS avec des types
  - TS est un **language** compilé, ie. on transforme le TS en JS avant de l'exécuter. Et ce qu'on exécute, c'est du JS !

- 2015 : ES6
  - c'est la version JavaScript qui rend le JS bien plus agréable à lire et écrire !

- 2016-2018 : 
  - Les navigateurs implémentent progressivement la norme ES6
  - ça prend du temps de fiare en sorte que les navigatuers soinet capable de lire le joli code JS proposé par ECMAScript

- 2013-2015 : Polyfil, bundlers, transpilers
  - Outils de **compatibilités** :  capables de prendre du code écrit dans une version "récente" de JS (ex. fonction fléchée)
  - Et de transformer ce code en son équivalent dans la syntaxe "ancienne" de JS (ex: fonction habituelle)
  - dans le but que ça fonctionne sur TOUS les navigateurs, y compris ceux qui n'ont pas encore été mis à jour!


- E2023
  - ARRAY.findLast

## TypeScript

Ecrire du JavaScript, avec une sécurité de type pour éviter des erreurs d'inattention.
- TypeScript est plus fort que Eslint qui ne voit pas le problème de type de variable.
- typeScript peut Typer les variable, Eslint ne peut pas.
- typeScript ne corrige pas le syntaxe, il voit le problème potentiel

```ts
function sum(a: number, b: number): number { //préciser le type de sortie est un nombre
  return a + b;
}

sum(42, 50); //OK !
sum("toto", 50); // ERROR: type "string" is not assignable to type "number"
```
 
 - `JS` : revoie 'toto' au moment ou on exécute le code (que quand on teste)
 - `TS` : l'erreur s'affiche au moment ou tu tapes les lignes (le compilateur)

 N'oubliez jamais : TypeScript est du JS avec du maquillage


## ChatGPT & Copilot

S'il vous plaît, "pour votre bien" :
- n'utilisez pas les outils de génération de code pour écrire du code à votre place
- aucun problème pour poser des questions et comprendre le fonctionnement de certains point (comprendre une doc, comrpendre un vout de code, chercher une fonction dont on ne connait pas le nom)
- utiliser le comme Google
- ne copier/coller pas de code (particulièrement sans comprendre), tant que les bases ne sont pas maitrisé.


## ES6 =  ECMAScript 6 (~2015)

Introduit en 2015 de nombreuses fonctionnalité en JavaScript :

[ES6 features](http://es6-features.org/#Constants)


- `let` / const
- () => {}
Littéraux de gabarit (interpolation) : `J'aime les ${ fruitName } `
- méthode shorthand :  `{ sayHello() {  /*...*/ } } `
- méthode `for.of`/ `forEach`
- fonction fléchée
- Et cf. S06 : import/export/class/destructuration

```js
const app = {
  listenToGrid() {
    /*...*/
  }
}
```
## Moteurs JS

Le Javascript, c'est un langage. en l'état, il ne fait rien d'autre d'exister.

Il faut un outil capable de lire et d'éxécuter du code JS: un moteur !
Il existe plusierus moteurs JS, le plus connu étant V8.
En particulier V8 est embarqué dans Chrome et dans Node !
 

schema de 3 mechanisme: 

1. ECMA est une association qui théorise et standarise les évolutions du lanagage.

2. Moteur(engine) qui implémente les spécifications ECMAScript et permet d'exécuter du code écrit en JS sur sa machine.

Ex. V8 releases v9.9 31/01/2022

3. Navigateur utiliser un moteur JS sous le capot pour exécuter du JS dans le contexte dese pages Web.


- V8 ne corrige pas du code JS , il est capable de le lire et l'execute sur le machine 
- Chrome est basé sur moteur V8
- firefox est basé sur un autre moteur que V8

## Cas problèmatique classqiue en programmation FRONT

- On code un site web avec du super JS.
- J'utilise la fonction `ARRAY.findLast` pour mon site web (parce que j'en ai besoin dans mon algorithme) 

- `Chrome` implémente le findLast : à priori, mon site va marcher sur Chrome
- `IE9` n'implémente pas le findLast : doncpour un utilisateur qui consulterai mon site sur IE9, ça plante !

===> 1. Mettez à jour vos navigatuers régulièrement !
===> 2. Brulons tous ensemble IE.

## Note saison 2

[Note S2] (https://github.com/O-clock-Gyoza/S02-index)


## JavaScript (-> ES14)


- quelques méthodes 'globales' du languages JS :

  - variable : let, const, var
  - parseInt, parseFloat, 
  - Math.floor, Math.random, 

- convertir : explicitement  'parseInt("44"))' implicitement '('!"boujour" === false')'

## DOM 

- selection : querySelector, getElementById
- création : createElement, appendChild
- Manipulation : classList, style, textContent, innerHTML, setAttribute
- Evenement: addEventListener, click, mouseover, submit, preventDefault

## Outils

- Vscode
- Git, Github
- ESLint
- DevTools: console, debugger

## Les grands questions 


backend: S03/S04/S05/S06
- Node 
- Serveur
- HTTP
- Herberger S08
- comment functionne les sites modernes
- template HTML
- 


## correction TripAdvisor 5branche. bonus

https://github.com/O-clock-Gyoza/S02E08-decouverte-js-RED-enzoclock

- toggle = sur un seul élément
- class => css
- id => js
- nextSibling
- document.querySelectorAll('input[type="checkbox"]')
- document.querySelectorAll('#rating-3,#rating-2')

Cet exemple utilise un sélecteur d'attribut pour renvoyer une liste d'éléments iframe dans le document qui contient un attribut nommé "data-src" :


```js
const matches = document.querySelectorAll("iframe[data-src]");
```


- addEventListener ('change')
- blur()
- focus()
- className = ecrase tous les classname
- SOC : separation of concerns 關注點分離
- JSDOC https://jsdoc.app/about-getting-started.html

/**+ enter 會自動產生
 * 
 * 


evénement adossées à Window
alert("hello");
confirmer("text");
prompt("")

