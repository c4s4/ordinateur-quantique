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
  - Big data, à quand le big processing ?
	- Chiffres de l'informatique Google ?
- Principes de fonctionnement
  - Représentation de l'information
  - Superposition quantique
  - Intrication quantique
  - Le Qbit
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
### Besoins de calcul croissants

Voici des estimations du nombre d'ordinateurs dans les datacenters des plus grandes entreprises du web :

- Google : plus de 1.000.000 (en janvier 2010).
- Microsoft : 1.000.000 (en janvier 2013).
- Amazon : 450.000 (en mars 2012).
- OVH : 140.000 (en mars 2013).

Les besoins en calculs des grandes entreprise est donc énorme et va croissant. La consommation des datacenters représente **2 % de la consommation modiale d'électricité**.

---
### Evolution des besoins en calcul

A titre d'exemple, voici l'évolution de la puissance des super-caculateurs de Météo France entre 1992 et 2016 (l'échelle est **logarithmique**):

![](img/evolution-meteo-france.png)

---
Principe de fonctionnement
--------------------------

L'ordinateur *quantique* traite, comme son homologue *classique*, de l'information. La différence majeure entre ces deux types est la manière de représenter cette information.

Alors que l'ordinateur classique manipule des *bits*, l'ordinateur quantique manipule des bits quantiques ou *Qbits*.



Dans un ordinateur classique, l'information 

