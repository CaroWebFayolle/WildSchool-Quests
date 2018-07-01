# Challenge

Afin de donner plus de style au site findThePrecious, Sauron veut être en mesure d'ajouter des anneaux sur ses pages. Plein d'anneaux, des grands, des petits, avec plein de couleurs différentes !
Tu devras donc, à l'aide de SCSS, créer une mixin appelée ring qui permet de dessiner un anneau.

> Hint : un anneau n'est rien d'autre qu'un carré avec un border-radius important, sans couleur de fond mais avec une bordure assez large.

Cette mixin doit te permettre :

* De choisir une taille et une couleur pour l'anneau
* Une ombre colorée doit apparaître (en fonction de la taille et de la couleur choisie)
* L'épaisseur de l'anneau doit être fonction de la taille choisie
* Une fois cette mixin créée, réalise une simple page HTML, appelée precious.html, correspondant à l'image ci-dessous et reprenant le header
* (et optionnellement le footer) réalisé dans la quête intégration finale.

> Hint : Utilise une boucle for en SCSS pour afficher la succession de 6 anneaux horizontaux imbriqués, de plus en plus grands.