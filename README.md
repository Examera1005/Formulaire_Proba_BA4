# EPFL — Formulaire de Probabilités et Statistique

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![LaTeX](https://img.shields.io/badge/LaTeX-Compiled-blue.svg)](https://www.latex-project.org/)
[![EPFL](https://img.shields.io/badge/EPFL-Mechanical%20Engineering-red.svg)](https://www.epfl.ch)

Ce dépôt contient un formulaire de synthèse rigoureux et ultra-dense pour les cours de **Probabilités et Statistique** dispensés à l'EPFL. Conçu spécifiquement pour une utilisation stratégique lors des examens à livre ouvert (notamment pour le Bachelor en Génie Mécanique), ce document condense l'intégralité des concepts clés, des théorèmes limites aux tests d'hypothèses, sans fioritures superflues.

---

## �� Aperçu du Contenu

Le document est structuré de manière à maximiser l'efficacité de la recherche d'informations sous pression temporelle :

### 1. Statistique Exploratoire
* [cite_start]**Tendance centrale** : Formulations de la moyenne empirique, de la médiane (selon la parité de $n$) et des quantiles/quartiles[cite: 5, 7, 8, 9, 10, 11].
* [cite_start]**Dispersion & Forme** : Variance et écart-type empiriques (correction de biais via $n-1$), identité de König-Huygens, construction géométrique précise du Boxplot (critère d'exclusion des valeurs aberrantes à $1.5 \times IQR$)[cite: 13, 14, 15, 16, 17, 18].

### 2. Théorie des Probabilités & Théorèmes Limites
* [cite_start]**Fondations** : Théorème de Bayes (forme simple et généralisée par partition), propriétés avancées de l'espérance conditionnelle et de la covariance (bilinéarité, changements d'échelle)[cite: 20, 21, 24, 25, 26, 27, 51].
* [cite_start]**Comportements Limites** : Distinctions fondamentales entre la Loi Faible (convergence en probabilité) et la Loi Forte des Grands Nombres (convergence quasi-sûre)[cite: 46, 47, 48, 49].
* [cite_start]**Inférence Asymptotique** : Théorème Central Limite (TCL) pour les variables standardisées et application de la **Méthode Delta** pour les fonctions continûment dérivables $g(\cdot)$[cite: 56, 57, 58].

### 3. Estimation Ponctuelle & Asymptotique
* [cite_start]**Méthodes d'estimation** : Méthode des Moments (MOM) et Maximum de Vraisemblance (ML) via la résolution de l'équation de score et la vérification de la condition de concavité locale[cite: 61, 62, 66, 67, 68].
* [cite_start]**Optimisation d'EQM** : Décomposition du compromis Biais-Variance[cite: 69, 70, 71]. [cite_start]Étude de cas sur la minimisation de l'EQM de la variance sous loi normale[cite: 72, 73, 74, 75, 76, 79].
* [cite_start]**Information de Fisher** : Calculs théoriques et observés ($I_n(\theta)$ vs $J_n(\hat{\theta})$), variances asymptotiques, et analyse des limites du modèle sur les structures non régulières (ex : Loi Uniforme $U(0, \theta)$)[cite: 81, 82, 83, 84, 85, 86, 87].
* [cite_start]**Queues Lourdes** : Comportement de la loi de Pareto et effondrement des théorèmes standards (TCL) lorsque la condition sur les moments ($\alpha > 1$ ou $\alpha > 2$) n'est plus satisfaite[cite: 88, 89].

### 4. Intervalles de Confiance (IC)
* [cite_start]**Théorie des Pivots** : Identification de pivots exacts normaux (Loi de Student $t_{n-1}$ vs $\mathcal{N}(0,1)$) et non normaux (Loi Uniforme via le maximum d'échantillon $M_n$)[cite: 91, 97, 100, 103, 105, 106].
* [cite_start]**Approches Asymptotiques** : IC construits à partir de l'Information de Fisher observée et du TCL appliqué[cite: 110, 111, 112, 118].

### 5. Régression Linéaire Simple
* [cite_start]**Moindres Carrés Ordinaires (MCO)** : Preuve d'unicité du minimum global via le déterminant strictement positif de la matrice Hessienne[cite: 92, 93, 94, 95].
* [cite_start]**Analyse de la Variance (ANOVA)** : Décomposition de la somme des carrés ($SC_{Total} = SC_R + SC_E$), calcul du coefficient de détermination $R^2$ et de sa version ajustée $R^2_{adj}$[cite: 125, 126, 127, 128, 129, 130].
* [cite_start]**Inférence sur la Pente** : Distribution exacte de l'estimateur $\hat{\beta}_n$, erreur-type, intervalles de confiance associés et statistiques de tests d'hypothèses de non-linéarité[cite: 132, 137, 138, 140, 141].

### 6. Distributions Usuelles & Tests du Chi-deux ($\chi^2$)
* [cite_start]**Formulaire de lois** : Synthèse compacte (Support, Densité/Masse, Espérance, Variance, Fisher) pour les lois Uniforme, Exponentielle, Poisson, Binomiale et Normale[cite: 144, 146, 147, 148, 150, 151].
* [cite_start]**Tests d'Adéquation & d'Indépendance** : Formulation des statistiques de test, calcul des degrés de liberté $\nu$ (ajustés selon les paramètres estimés $c$), et critères géométriques de rejet basés sur les quantiles théoriques[cite: 157, 158, 159, 160, 161, 162].

---

## ��️ Structure du Répertoire

```text
.
├── Formulaire_Proba.tex      # Fichier source LaTeX principal
├── Formulaire_Proba.pdf      # Version compilée prête à l'impression
├── figures/                  # TikZ ou graphiques vectoriels éventuels
└── README.md                 # Description du dépôt

⚡ Compilation LocaleLe document utilise des packages standards de l'écosystème de l'AMS ainsi que des environnements multicolonnes optimisés pour les aide-mémoires d'examen. Pour générer le PDF à partir des sources :Bash# Utilisation de latexmk pour gérer automatiquement les dépendances de compilation
latexmk -pdf Formulaire_Proba.tex

# Ou via une compilation classique pdflatex
pdflatex Formulaire_Proba.tex
Note technique : Assure-toi de disposer d'une distribution TeX Live (ou MiKTeX) complète incluant amsmath, amsfonts, amssymb et multicol pour éviter toute rupture de compilation des structures de matrices ou de symboles probabilistes (comme les opérateurs d'espérance $\mathbb{E}$ ou de convergence $\xrightarrow{\mathcal{L}}$).�� LicenceCe projet est distribué sous licence MIT. Libre à toi de le cloner, de le modifier et de l'adapter pour tes propres révisions à l'EPFL ou ailleurs. Les pull requests visant à corriger des coquilles ou à enrichir certaines sections (notamment la méthode Delta ou l'ANOVA) sont les bienvenues.