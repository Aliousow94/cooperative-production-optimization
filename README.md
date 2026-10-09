# Optimisation de la production – Recherche opérationnelle

## Présentation du projet

Ce projet de recherche opérationnelle consiste à modéliser et résoudre un problème de programmation linéaire appliqué à la planification de la production de la coopérative fictive **SAHEL Ameublement**, basée à Dakar.

L'objectif est de déterminer les quantités optimales de tables, de chaises et d'armoires à produire chaque semaine afin de maximiser la marge bénéficiaire, tout en respectant les contraintes de disponibilité des ressources et les engagements commerciaux.

## Objectifs

* Formaliser un problème de production sous forme de modèle mathématique.
* Résoudre un problème de programmation linéaire avec plusieurs outils.
* Comparer les résultats obtenus avec Excel et Python.
* Interpréter les résultats grâce à l'analyse de sensibilité et aux prix duaux.
* Étudier une extension en programmation linéaire en nombres entiers et un problème de transport.

## Technologies et outils

* **Python** : langage de programmation.
* **PuLP** : modélisation et résolution de problèmes d'optimisation linéaire.
* **SciPy** : résolution numérique avec `scipy.optimize.linprog`.
* **Excel Solver** : modélisation et résolution par la méthode du simplexe.
* **Jupyter Notebook** : développement et exécution des analyses.

## Modèle mathématique

### Variables de décision

* \(x_1\) : nombre de tables produites.
* \(x_2\) : nombre de chaises produites.
* \(x_3\) : nombre d'armoires produites.

### Fonction objectif

Maximiser la marge bénéficiaire hebdomadaire :

$$
\max Z=15000x_1+4000x_2+22000x_3
$$

Sous les contraintes suivantes :

* Bois : \(8x_1+2x_2+12x_3\leq900\)
* Main-d'œuvre : \(4x_1+1.5x_2+6x_3\leq400\)
* Temps machine : \(2x_1+x_2+3x_3\leq220\)
* Limite commerciale : \(x_2\leq60\)
* Contrat minimum : \(x_3\geq10\)
* Non-négativité : \(x_1,x_2,x_3\geq0\)

## Résultats obtenus

Les trois méthodes de résolution convergent vers la même solution optimale.

| Indicateur                       |       Résultat |
| -------------------------------- | -------------: |
| Tables à produire                |             85 |
| Chaises à produire               |              0 |
| Armoires à produire              |             10 |
| Marge maximale hebdomadaire      | 1 495 000 FCFA |
| Heures de main-d'œuvre utilisées |          400 h |
| Prix dual de la main-d'œuvre     |   3 750 FCFA/h |

### Principales observations

* La main-d'œuvre constitue la ressource limitante du problème.
* Le bois et le temps machine restent partiellement disponibles.
* La production de chaises n'est pas retenue dans la solution optimale.
* L'analyse de sensibilité permet d'évaluer l'effet des variations de ressources sur la rentabilité.

## Comparaison des méthodes

* **Excel Solver** : facilite la modélisation visuelle et l'interprétation des rapports.
* **PuLP** : permet de formuler le modèle de manière lisible à l'aide de variables et de contraintes nommées.
* **SciPy** : offre une approche matricielle adaptée à la résolution numérique.

Les résultats identiques obtenus avec ces trois approches permettent de vérifier la cohérence de la solution.

## Extensions étudiées

Le projet comprend également :

* La programmation linéaire en nombres entiers pour imposer des quantités entières de meubles.
* Un problème de transport vers Niamey, Zinder et Maradi, avec des coûts et des capacités hypothétiques à titre d'illustration.

## Structure du dépôt

```text
optimisation-recherche-operationnelle/
├── README.md
├── projet RO EXCEL.xlsx
├── optimisation_scipy_pulp.ipynb
└── Rapport_Projet_RO.pdf
```

Les noms des fichiers peuvent être adaptés à ceux réellement présents dans le dépôt.

## Installation et exécution

Installer les bibliothèques Python nécessaires :

```bash
python -m pip install "pulp<4" scipy jupyter
```

Lancer ensuite Jupyter Notebook :

```bash
jupyter notebook
```

Ouvrir `optimisation_scipy_pulp.ipynb` et exécuter les cellules pour reproduire les calculs.

Le classeur Excel permet également de consulter le modèle et de relancer la résolution avec le Solveur.

## Compétences mobilisées

* Modélisation mathématique et programmation linéaire.
* Optimisation sous contraintes.
* Programmation scientifique avec Python.
* Utilisation de PuLP et SciPy.
* Analyse de sensibilité et interprétation des prix duaux.
* Comparaison et validation de solutions numériques.

## Auteurs

* Papa Ousseynou Niang
* Bada Sall
* Mamadou Aliou Sow

**Projet réalisé dans le cadre du module de Recherche opérationnelle.**

Enseignant responsable : Dr Cheikh Gueye.

---

*Remarque : les données utilisées pour l'extension consacrée au transport sont des hypothèses fictives et ne représentent pas des coûts réels.*
