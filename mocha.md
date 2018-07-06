# Mocha

## Framework de test en javascript

### Site officiel : https://mochajs.org/

Basé sur Node.js, Mocha est un outil qui permet aux développeurs
de créer des tests en javascript de façon simple et efficace.

__Installation__ :

Après avoir initialisé son projet avec la commande `npm init` :

`npm install mocha --save-dev`
le préfixe `--save-dev` sert à indiquer que mocha est une dépendance
pour l'environnement de développement.

Pour fonctionner, Mocha a besoin d'un répertoire de test
et d'un fichier test.js :

`mkdir test`
puis `nano test.js` avec le contenu suivant :

```
var assert = require('assert');
describe('Array', function() {
  describe('#indexOf()', function() {
    it('should return -1 when the value is not present', function() {
      assert.equal([1,2,3].indexOf(4), -1);
    });
  });
});
```

On test le bon fonctionnement de l'outil dans le terminal :
`$ ./node_modules/mocha/bin/mocha`

*Mocha va executer les tests contenus dans le fichier /test/test.js et nous renvoi :
 1 passing (9ms)*

On déclare Mocha comme étant notre utilitaire de tests :
dans le fichier *package.json* (généré automatiquement au début avec `npm init`):

```
"scripts": {
    "test": "mocha"
  }
```

Ensuite pour exécuter les tests :
```$npm test```

__Bonne pratique pour l'écriture de tests et démarche globale :__

```
describe('User', function() {
  describe('#save()', function() {
    it('should save without error', function(done) {
      var user = new User('Luna');
      user.save(done);
    });
  });
})
```
1. On décrit en anglais (universalité) ce que l'on attend de la fonction à tester
2. test
3. Utilisation de `done`

__Démarche__

1. Rédiger les tests en fonction de ce que doivent faire les différents composants
2. Executer les tests : la console nous indique en erreur ce que l'on doit coder
3. Ré-executer la batterie de tests pour validation



# ES6
## ECMAScript6
Standard de langage de programmation. Définit entre autres syntaxe et types de variables.

Il évolue pour que les langages basés dessus soient de plus en plus puissants.

Il est utilisé pour activer les scripts côté client.

Permet les fonctionnalités suivantes :
- Prise en charge des constantes
- Block scope
- Arrow functions
- Gestion étendue des paramètres
- Template et Extended literals
- Modules, Class et Itertors

Nécessite Un IDE et Node

### Syntaxes :
- firstName
- first-name
- num1
- $result

ES6 ignore les espaces, onglets et retours de lignes qui apparaissent dans les programmes.

Les ; sont facultatifs MAIS attention à la casse !
````let Mavariable````
sera différente de 
````let mavariable````
ou encore
````let maVariable````

Une seule ligne peut contenir plusieurs instructions si ceux-ci sont séparés par un ;

ES5 introduit le mode strict. Celui-ci impose une contrainte sur JS.

        //whole-script strict mode syntax
        "use strict";
        v = "Hi ! I'm a strict mode script !"; //ERROR : variable v is not declared

Ici intégralité du code s'éxécute en mode strict.

        v = 15;
        function f1(){
            "use strict";
            let v = "Hi ! I'm a strict mode script !";
        }

Ici, tout code en dehors de la function (Scope) s'éxecutera en mode non strict.

## Les fonctions :
En plus des bases déjà vues (fonction simple et paramétrée), ES6 permet d'introduction de différentes functions :
- La function anonyme : est déclarée dynamiquement au moment de l'éxecution.
````let rez = function(arg, arg2){//instructions}````
ex :

        let funct = function(x, y){return x*y};
        function product(){
            let result;
            result = func(10, 20);
            console.log("The product : "+result)
        }
        product()

- le construcor de functions : permet de définir dynamiquement une nouvelle function.
````let variable = new Function(arg, arg2, "Function Body");````
ex :

        let func = new Function("x", "y", "return x*y");
        function product(){
            let result;
            result = funct(10,20);
            console.log("The product : "+result)
        }
        product()

- La function récursive : technique d'itération sur une opération en ayant une function appelée elle même plusieurs fois jusqu'à ce qu'elle arrive à un résultat.
ex :


        function factorial(num){
            if(num <= 0>){
                return 1;
            }
            else{
                return (num*factorial(num-1))
            }
        }
        console.log(factorial(6))

- Function fléchée : expression de function anonyme qui pointe vers une seule ligne de code.
````([arg, arg2])=>instruction````
ex :

        let foo = (x)=>10+x
        console.log(foo(10))

