# Exercice : Mon meuble SOLID, Le KALAX

## Présentation
Le but de cet exercice est de mettre en pratique les principes SOLID, IOD, KISS et Fonctionnel
vs technique.

## Exercice 1 : Le squelette des abstractions
Créer un projet Java (Maven).
Créer une interface meuble avec les specifications suivantes :
* un meuble a une hauteur
* un meuble a une largeur
* un meuble a une épaisseur

Créer une interface meuble kalax avec les specifications suivantes :
* un kalax est un meuble
* un kalax a un certain nombre d'emplacements
* il est possible de mettre un composant d'emplacement Kalax dans un emplacement
* il est possible de retirer un composant d'emplacement Kalax dans un emplacement

Créer une interface emplacement de meuble avec les specifications suivantes :
* un emplacement de meuble peut ranger des objets
* un emplacement de meuble permet de retirer des objets
* un emplacement de meuble permet de lister des objets

Créer une interface composant d'emplacement kalax avec les specifications suivantes :
* un composant d'emplacement kalax est un emplacement de meuble
* un composant d'emplacement kalax peut être tiré pour voir son contenue

Créer une interface tiroir avec les specifications suivantes :
* un tiroir peut être ouvert

Créer une interface composant avec les specifications suivantes :
* un composant possède une couleur

Créer une interface composant en tissu avec les specifications suivantes :
* un composant en tissu est un composant
* un composant en tissu peut être lavé a l'eau

Créer une interface composant en bois avec les specifications suivantes :
* un composant en bois est un composant
* un composant en bois peut être repaint avec une certaine couleur

Créer une interface objet qui peut être rangé avec les specifications suivantes :
* un objet qui peut être ranger possède un nom

Créer une interface composant sécuriser avec les specifications suivantes :
* c'est un composant 
* il faut une clé pour le déverrouiller

Utiliser des termes correspondant aux besoins listé ci-dessus.

Vous venez de faire de la ségrégation d'interface en respectant le principe de responsabilité
unique.

### Exercice 2 : Implementation de Kalax
Créer une classe meuble kalax 4x2 :
* c'est une meuble kalax
* il possède 4 emplacements
* il fait 35 cm de profondeur
* il fait 80 cm de large
* il fait 140 cm d’haut

Implémenté les méthodes necessaries.

Créer un autre meuble kalax 4x4 en ajustant les valeurs du meuble kalax 4x2
```
Bonus :
Créer une classe abstraite permettant de simplifier la création de meuble kalax en généralisant
certaines méthodes.
```

### Exercice 3 : Implémentation des composants

Créer une classe tiroir pour emplacement kalax :
* c'est un composant d'emplacement kalax
* c'est un tiroir
* c'est un composant en bois

Créer une classe boite pour kalax :
* c'est un composant d'emplacement kalax
* c'est un composant en bois

Créer une classe coffre-fort pour kalax :
* c'est un composant d'emplacement kalax
* c'est un composant sécurisé

Créer une classe boite en tissu :
* c'est un composant d'emplacement kalax
* c'est un composant en tissu

Implémenté les différentes méthodes. 

Vous venez de faire un code respectant les principes SOLID et IOD.

### Exercice 4 : Assemblage
Comme avec le meuble. Écrire un code qui assemble des meubles kalax et des composants d'emplacement
kalax.