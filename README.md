# SOLID avec Java

## Présentation
Lors du développement d'un projet informatique avec des language utilisant le paradigme de la programmation orienté objet
nous devons réfléchir comment agencé notre code pour qu'il soit `résilliant`, `évolutif` et facile a maintenir.

La structure de code SOLID define un certain nombre de préceptes qui permettent d'avoir un code mieux structuré.

## Lexique
* __abstractions__ :
    Type qui n'est pas une implémentation. Il n'est pas suffisant a lui-même pour la création d'instance. Il uniquement
    les elements qu'il define.
* __attribut__ :
    Variable appartenant à une classe ou a une instance.
* __class__ :
    Composant d'un programme contenant des méthodes et attributs. C'est un paterne qui permet la création d'instances
    qui ont les mêmes caractéristiques. 
* __cohérence__ :
    Bon déroulement des taches a faire et bonne structure d'un programme.
* __entité applicative__ :
    classe, fonction, module ou autre composant d'un programme.
* __extension__ : 
    Fait de d'ajouter un fonctionnement a un composant deja existant.
* __fonction__ :
    Composant ayant une entrée, effectuant un traitement et retournant (ou pas) une valeur.
* __implémentations__ :
    Type d'une classe. Ce type contient tout les elements permettant la création d'une instance.
    Souvent aussi appelé `type concrét`. 
* __instance__ :
    Cas particulier d'une classe respectant sa responsabilité mais ayant ses propres valeurs.
* __interfaces spécifiques__ :
    Interface contenant un nombre limité de besoins.
* __interface générale__ :
    Interface contenant l'ensemble des besoins d'un type.
* __interface__ :
    Composant listant des besoins.
* __méthode__ :
    Fonction appartenant à une classe.
* __modification__ :
    Fait de changé le fonctionnement d'une entité applicative.
* __remplacer__ :
    Fait de ce faire passer pour un autre type.
* __responsabilité__ :
    Une tache a faire.
* __sous-type__ :
    Type enfant d'un autre type. Il est une extension du type dit parent.
* __type__ :
    Ensemble de méthodes et d'attribut que define une instance. Peut-être une classe ou une interface.

## Qu'est-ce que le SOLID

SOLID est un acronyme de 5 principes qui sont lié les un aux autres :

* __Single responsibility principle__ : 
    une classe, une fonction ou une méthode doit avoir une et une seule `responsabilité`.
    
* __Open/closed principle__ : 
    une `entité applicative`  doit être fermée à la `modification` 
    directe mais ouverte à l'`extension`.

* __Liskov substitution principle__ : 
    une instance de type T doit pouvoir être remplacée par une instance de type G, tel que G sous-type de T, 
    sans que cela ne modifie la cohérence du programme
    
* __Interface segregation principle__ :
    préférer plusieurs `interfaces spécifiques` pour chaque client plutôt qu'une seule `interface générale`
    
* __Dependency inversion principle__ :
    il faut dépendre des `abstractions`, pas des `implémentations`

## Le Kalax d'IKEA
```
Le meuble Kalax d'IKEA est une bonne métaphore des principes SOLID. 
```
Citation de _Benoit Routier_.

### Single responsibility principle:
La responsabilité de ce meuble est de pouvoir agencé des composants ensemble. 
C'est sa seule responsabilité.

Il peut contenir plusieurs emplacements qui auront chacun leurs propres responsabilités.

Grace a ce principe, ce meuble est facile à utiliser et à placer dans beaucoup de situations.

Le principe de responsabilité unique permet la réutilisation et la simplification des entités applicatives.
 
### Open/Close principle:
Il est possible changé ce que l'on peut faire avec ce meuble en ajoutant des emplacements,
en collant un autre meuble ou en changeant les emplacements mais sans avoir à modifier le meuble
en lui-même.

Le Kalax est ouvert a l'extension mais fermer a la modification.

Le principe d'ouvert/fermer permet de ne pas avoir à modifier une entité applicative qui est deja fonctionnel mais de
pouvoir facilement créer des extensions. Comme le premier point, il est plus facile ainsi de réutilisé du code 
deja fonctionnel et il est plus facile de le faire évoluer.

### Liskov substitution principle:
Les emplacements d'un meuble Kalax permettent de facilement interchanger les composants que l'on 
peut mettre à l'intérieur. Ils respectent tous les même dimensions. Les composants que l'on peut 
y insérer respectent eux aussi les mêmes dimensions. Ils est donc facile de les interchanger.

Dans le premier emplacement nous pouvons mettre :
* Deux tiroirs l'un sur l'autre qui forme à eux deux un cube respectant les dimensions d'un emplacement Kalax.
* Une boite en tissu ayant respectant les bonnes dimensions.
* Une boite en plastique ayant divert couleurs.
* Un coffre.
* Un emplacement vide. 
* Notre propre type de composant tant qu'il respecte les dimensions d'un emplacement Kalax.

Tout composants d'emplacement d'un Kalax possédant les bonnes dimensions peut être mis dans un emplacement.

Ainsi, le meuble en lui-même a sa propre responsabilité et chaque emplacement define sa propre responsabilité.

Il respecte le principe de substitution de Liskov ce qui lui permet d'etre un meuble fortement modulable et donc
utilisable dans de nombreux cas.

Ce principe dit qu'une entité applicative de type `T` (ici un emplacement vide) peut être remplacé par 
une autre de type `G` (un composant d'emplacement) si `S` est un sous-type de `T` 
(le composant d'emplacement respecte les dimensions d'un emplacement).

### Interface segregation principle
Il existe un grand nombre de composants d'emplacement pour un meuble Kalax. 
Certains sont des boites, des tiroirs, de plus petits emplacements, ...
Mais ils sont tous des emplacements.

Le composant boite en tissu a les caractéristiques d'un emplacement, d'un objet en tissu et
d'une boite.

Le composant boite en boi a les caractéristiques d'un emplacement, d'un objet en boi et d'une boite.

Le composant double tiroir a les caractéristiques d'un emplacement, d'un objet en boi et d'un tiroir.  

Chaque composant a ses propres caractéristiques mais on retrouve certaines caractéristiques communes à
plusieurs composants. 

Le principe de ségrégation d'interface stipule qu'il est préférable de découper les interfaces 
(ici liste de caractéristiques) plutôt que d'utiliser une seule interface pour chaque entité applicative.
Ainsi pour le typage, nous pouvons assembler des interfaces entre elles et réutilisé ses interfaces sur plusieurs
entités applicatives. 

Ce principe va de pair avec les principes vu précédemment.

### Dependency inversion principle:
Comme dit précédemment, le meuble Kalax n'est pas spécifiques a ce que l'on met dedans. 
Nous pouvons facilement changer de composant d'emplacement par un autre.
Cela est possible car le meuble ne define que des dimensions à respecter pour qu'un composant
puisse être utilisé dans un emplacement.

Nous stockons des composants sous la forme abstraite d'emplacement.
Chaque composant est une implémentation (mise en pratique concrète) d'un emplacement (qui reste abstrait).

Ce principe stipule que nous ne devons pas utiliser directement d'implémentations pour le typage
mais plutôt des abstractions. 

Il vient avec la notion de couplage fort et faible.

Si un meuble ne peut propose pas d'emplacement standard mais oblige l'utilisation d'un
certain composant (ce qui revient à typer avec une implémentation) alors il y a un lien fort
entre le meuble et son composant. On parle alors de couplage fort. 
L'héritage ou le typage par classe forme un couplage fort qui rend plus rigide et moins adaptatif notre code.

A contrario, si le meuble propose juste des emplacements standardisé qui ne force pas l'utilisation
d'un composant spécifique, cela le rend plus modulable et adaptatif aux différents besoins.
On défait le lien fort entre les deux entités. 
On parle alors de couplage faible.
L'utilisation d'interfaces pour le typage permet la création de couplage faible.

Il est en général préférable d'utiliser un couplage faible plutôt que fort dans notre code.

## Notions proches de SOLID

### IOD (Injection of dependencies)
Le principe d'injection de dépendances est une extension des principes SOLID.

Notre meuble ne définit aucun composant deja mis en place. 
Il ne définit qu'un certain nombre d'emplacements disponibles où nous pouvons `injecter`
des composants en fonction des besoins. 

C'est ca le principe d'injection de dépendances. 
Ne pas définir les attributs d'une classe dans celle-ci mais plutôt de pouvoir y injecté
nos instances au besoin.

L'injection de dépendances est un principe important pour la structuration d'un programme car
il permet une plus grande modularité et le rend plus adaptatif aux besoins et aux évolutions future.

L'IOD et SOLID vont souvent de pair.

Spring est un framework Java permettant la mise en place d'Inversion de Control (fait que ce soit le framework qui
assemble nos entités applicatives plutôt que le développeur) et d'IOD. 
Il est fait pour l'utilisation IOD et SOLID. 

### DRY (Don't Repeat Yourself)
Ce principe dit qu'il ne faut pas se répéter.
Si un morceau de code est deja écrit pour faire une certaine tache, 
alors il faut le réutiliser dans le reste du programme.

DRY permet de gagner du temps mais aussi de rendre le code plus consistant et de facilité
la correction d'éventuels bogues.

Il va de pair avec les principes du SOLID et de L'IOD. Respecter le SOLID et l'IOD permet la
réutilisation du code plus simplement.

### KISS (Keep it simple, stupid)
Reste simple et stupide.

Ce principe stipule qu'il est préférable d'avoir un code simple et facile à comprendre.

Le SOLID, IOD et DRY permettent de rendre en général le code plus simple et lisible.

Un code trop complexe, où les entités applicatives ont plusieurs responsabilités,
est plus difficile a maintenir et a faire évoluer.

### Fonctionnel vs Technique
Principe trop souvent oublié : Vous ne coder pas pour vous, votre code n'est pas
pour vous ni à vous mais au client.
Et le client ne parle pas technique.

Si on vous vend un meuble en parlant qu'avec des termes de l'industrialisation de la 
menuiserie, il y a de grande chance que vous ne comprenais pas tout.

Les fonctionnels sont les personnes ne sont pas techniques et qui possèdent le besoin.
Par exemple les clients, les chefs de projets, les product owners, les commerciaux, ...
Ils ont leurs languages et ne comprennent pas les termes techniques comme CRUD, Services, ...
Ou pire... Ils ont d'autre définitions pour ces termes.

Les techniques (vous) sont les personnes qui produisent le produit. 
Ils ont leurs termes, ce comprennent plus ou moins bien entre eux.

L'utilisation de termes techniques dans les présentations, les réunions et même dans le produits
(le code ou la documentation) coupe la discussion avec la partie fonctionnel du projet et
donc peut créer des incompréhensions amenant des erreurs et une perte de temps.

Il faut donc __même dans le code__ utiliser le vocabulaire fonctionnel. 
Celui du metier, celui pour qui nous produisons et non notre language barbare.

Si les fonctionnels parlent en Francais, nous développons en francais pour pouvoir
utiliser le même lexique tout au long de la production du projet.

## Conclusion
Les développeurs ont tendances à faire au plus vide sans réfléchir à créer une structure de code évolutif et 
`future proof`. Cela entraine une difficulté a rendre maintenable notre code sur le long terme.

En ayant en tête les principes de SOLID, IOD, DRY, KISS et Fonctionnel vs Technique nous pouvons mieux structurer
notre code et le rendre plus maintenable.

Un code mal réfléchis vieillit __TRES MAL__ et entraine beaucoup de problèmes par le futur ! 

Structurez votre code pour qu'il soit dur, sec et avec un bisou.

Cela étant dit, ce ne sont que des principes qui ne peuvent pas être toujours suivit a la lettre.
Ils doivent être vus comme des concepts a avoir en tête lors du développement d'un projet.
 


 