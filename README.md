L'Ordinateur Quantique, Mythe ou Réalité ?
==========================================

Michel Casabianca

casa@sweetohm.net

---
Proposition BDXIO 2017
----------------------

On entend parfois parler d'ordinateur quantique. Mais qui en a déjà vu un ?

Après une brève présentation des principes physiques sur lesquels repose l'ordinateur quantique (superposition et intrication quantiques), je présenterai le Qbit ainsi que les principaux algorithmes quantiques (Grover pour la recherche et Shor pour la décomposition de nombres premiers). Je finirai sur les implémentations actuelles, les difficultés de mise ne œuvre, les perspectives et les enjeux de ces ordinateur d'un nouveau type.

---
Plan
----

- Pourquoi un ordinateur quantique ?
  - La loi de Moore
  - Limites de l'informatique classique
  - Besoins croissant en puissance de calcul
- Principes de fonctionnement
  - Superposition quantique
  - Intrication quantique
  - Le Qbit
  - Représentation de l'information
  - Algorithmes quantiques
- Implémentations d'ordinateurs quantiques
  - Implémentations de Qbits
  - Portes quantiques
- Limites de l'ordinateur quantique
  - Réduction du paquet d'onde
  - Copie impossible des Qbits
  - Nombre de Qbits
- Cas d'utilisation des ordinateurs quantiques
  - Cryptographie (algorithme de Shor)
  - Recherche d'information (algorithme de Grover)
  - Problèmes d'optimisation (voyageur de commerce)
- Et maintenant ?
  - Situation actuelle
  - Perspectives

---
On entend souvent parler d'ordinateur quantique. Mais qui en a déjà vu un ?

---
Pourquoi l'ordinateur Quantique ?
---------------------------------

Nos ordinateurs classiques nous ont suffi jusqu'à maintenant...

![](img/amour-ordi.png)

---
### Loi de Moore

```bash
Le nombre de transistors dans les microprocesseurs double tous les deux ans.
```

Cette loi a été énoncée par Gordon E. Moore (un des trois fondateurs d'Intel) en 1975. Elle a été très bien vérifiée pendant très longtemps.

![Loi de Moore](img/loi-moore.png)

---
### Limites Physiques

Cependant, cette loi est **exponentielle**. Or nous savons tous que les lois exponentielles ne peuvent fonctionner qu'un temps, jusqu'à ce qu'on atteigne la **limite du système**.

En ce qui concerne les processeurs, les limites sont les suivantes :

- La finesse de la gravure, et donc le nombre de transistors par centimètre carré, est limitée par la diffraction de la lumière.
- L'effet tunnel, qui permet à un électron de passer une barrière à priori infranchissable, limite aussi la finesse des circuits.
- La fréquence est limitée par l'émission de rayonnement aux hautes fréquences ainsi que l'émission de chaleur par le processeur.

Ces limites physiques conduisent à plafonnement des performances des processeurs, et la fin de la validité de la loi de Moore a été annoncée en **2016**.

---
### Evolution des besoins en calcul

A titre d'exemple, voici l'évolution de la puissance des super-caculateurs de Météo France entre 1992 et 2016 (l'échelle est **logarithmique**):

![](img/evolution-meteo-france.png)

---
### Nombre d'ordinateurs croissant

Voici des estimations du nombre d'ordinateurs dans les datacenters des plus grandes entreprises du web :

- Google : plus de 1.000.000 (en janvier 2010).
- Microsoft : 1.000.000 (en janvier 2013).
- Amazon : 450.000 (en mars 2012).
- OVH : 140.000 (en mars 2013).

Les besoins en calculs des grandes entreprise est donc énorme et va croissant. La consommation des datacenters représente **2 % de la consommation modiale d'électricité**.

**Les besoins croissants en puissance de calcul ainsi que les limites des technologies actuelles rendent nécessaires des avancées majeures dans la technologie informatique.**

---
Ordinateurs Quantiques
======================

L'idée d'ordinateur quantique vient à Richard Feynman dans les années 80 :

```bash
Au lieu de nous plaindre que la simulation des phénomènes quantiques demande
des puissances énormes à nos ordinateurs actuels, utilisons la puissance de
calcul des phénomènes quantiques pour dépasser nos ordinateurs actuels.
```

L'idée est restée assez vague, jusqu'à ce que :

- En 1994, **Peter Shor**, chercheur chez AT&T, démontre qu'il est possible de factoriser de grands nombres en un temps raisonnable à l'aide d'un calculateur quantique.
- En 1996, **Lov Grover** invente un algorithme quantique qui permet de trouver une entrée dans une base de données non triée en *O(sqrt(N))*.

L'intérêt pratique de ces deux algorithmes, pour la **cryptographie** et la **recherche de données**, a poussé à l'implémentations concrète d'ordinateurs quantiques. Et il se truve que les gens qui s'intéressent à ces domaines, comme la **NSA** ou **Google**, ont des moyens.

---
Principe de fonctionnement
--------------------------

L'ordinateur *quantique* traite, comme son homologue *classique*, de l'information. La différence majeure entre ces deux types est la manière de représenter cette information.

L'ordinateur classique représente l'information sous forme de **bits** (pour *binary digit*) qui peuvent avoir pour valeurs **0** ou **1**.

L'ordinateur quantique représente l'information à l'aide de **qubits** (pour *quantum binary digit*) qui a un état qui est une superposition de deux états, que l'on peut noter **0** et **1** :

```bash
a.|0> + b.|1>
```

Cela est possible du fait du principe de superposition quantique.

---
### Superposition quantique

Une particule, qui est infiniment petite et donc régie par les lois de la physique quantique, peut se trouver dans un **état indéterminé** tant qu'on n'a pas mesuré son état.

Donc si une particule peut avoir deux états : soit *spin up* (représenté par *|u>*) soit *spin down* (représenté par *|d>*) alors, on peut représenter son état par :

```bash
a.|u> + b.|d>
```

Où *a* et *b* déterminent la **probabilité** d'observer la particule dans l'état *|u>* ou *|d>*. Par exemple, si la particule est nécessairement dans l'état *|u>*, alors on aura :

```bash
a = 1
b = 0
```

---
### Le coin du mathématicien

Les vecteurs d'état de la physique quantique n'ont rien à voir avec les vecteurs de la géométrie. En effet, les bases de l'espace vectoriel sont des états mutuellement exclusifs : une particule ne peut être simultanément dans l'état *|u>* et *|d>*.

De plus, lorsqu'on écrit un état quantique sous la forme :

```bash
a.|u> + b.|d>
```

- Cet état n'indique pas que la particule a un peu de *|u>* et un peu de *|d>*.
- Les coefficients *a* et *b* sont des nombres **complexes**.

On peut représenter cet état sous forme de vecteurs colonnes :

```bash
| a |     | 1 |     | 0 |               | 1 |          | 0 |
|   | = a |   | + b |   |  avec : |u> = |   | et |d> = |   |
| b |     | 0 |     | 1 |               | 0 |          | 1 |
```

Dans cet état, la probabilité de l'état *up* est *|a|^2* et la probabilité de l'état *down* est *|b|^2* et *a* et *b* vérifient *|a|^2 + |b|^2 = 1*.

La mathématique de la physique quantique est **l'algèbre linéaire**.

---
### Etrangeté quantique

On peut se dire que c'est pareil pour un système classique à deux états (comme une pièce de monnaie qui peut être *pile* ou *face*), mais il n'en est rien. En effet, même si on ne regarde pas la pièce de monnaie, on sait qu'elle est soit *pile* soit *face*.

Dans le cas de la particule quantique, c'est différent : avant la mesure, son état est une superposition des deux états.

On peut faire le parallèle avec un billet de loterie : **tant que le tirage n'a pas eu lieu, le billet est à la fois perdant ET gagnant**. Et ce n'est pas parce qu'on ne voit pas le billet.

Ceci illustre le fait que l'on ne peut se représenter mentalement le monde quantique. Alors que nous pouvons prévoir le comportement de systèmes classiques simples (comme une pomme qu'on lâche), **seules les mathématiques permettent de prévoir le comportement d'un système quantique**.

---
### Intrication quantique

Deux objets quantiques peuvent être **liés** de sorte que si l'on connait l'état de l'un on peut en déduire l'état de l'autre. Ce phénomène s'appelle l'intrication quantique.

Ainsi, à l'issu de la désintégration d'une particule en deux autres, il peut arriver que les spins de ces deux particules soient intriqués. **Si on connait le spin de l'une on peut en déduire celui de l'autre**, et ce quelle que soit la distance qui les sépare.

![](img/intrication-quantique.png)

On peut expliquer ce phénomène par le fait que ces particules intriquées, qui peuvent être en nombre quelconque, forment **un seul système**.


