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
