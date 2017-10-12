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

![](img/amour-ordi.jpg)

---
### Loi de Moore

```bash
Le nombre de transistors dans les processeurs (donc leur puissance)
double tous les dix-huit mois.
```

Cette loi a été énoncée par XXX Moore en 19

Cette loi est **exponentielle** car à intervalle de temps (tous les *18* mois) on multiplie le nombre de transistors par une constante (*2* en l'occurrence).

Or nous savons tous que les lois exponentielles ne peuvent fonctionner qu'un temps. Jusqu'à ce qu'on atteigne la **limite du système**. Par exemple, en économie, ce qui limite la croissance est (entre autre) la finitude des ressources.

En ce qui concerne les processeurs, les limites sont physiques :

- La finesse de la gravure est limitées par la diffraction de la lumière.
- L'effet tunnel, qui permet à un électron de passer une barrière à priori infranchissable limite aussi la finesse de la gravure.
- La fréquence est limitée par l'émission de rayonnement aux hautes fréquences.

---
### Besoins de calcul croissants

---
Principe de fonctionnement
--------------------------

L'ordinateur *quantique* traite, comme son homologue *classique*, de l'information. La différence majeure entre ces deux types est la manière de représenter cette information.

Alors que l'ordinateur classique manipule des *bits*, l'ordinateur quantique manipule des bits quantiques ou *Qbits*.



Dans un ordinateur classique, l'information 

