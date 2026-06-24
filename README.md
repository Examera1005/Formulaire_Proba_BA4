# EPFL — Formulaire de Probabilités et Statistique

Ce dépôt contient un formulaire de synthèse rigoureux et ultra-dense pour les cours de Probabilités et Statistique dispensés à l'EPFL. Conçu spécifiquement pour une utilisation stratégique lors des examens à livre ouvert (notamment pour le Bachelor en Génie Mécanique), ce document condense l'intégralité des concepts clés, des théorèmes limites aux tests d'hypothèses, sans fioritures superflues.

Il fait référence au fichier principal Formulaire_Proba.pdf qui contient la version compilée finale.

---

## Aperçu du Contenu

Le document est structuré de manière à maximiser l'efficacité de la recherche d'informations sous pression temporelle :

### 1. Statistique Exploratoire
* **Tendance centrale** : Formulations de la moyenne empirique, de la médiane (selon la parité de n) et des quantiles/quartiles.
* **Dispersion & Forme** : Variance et écart-type empiriques (correction de biais via n-1), identité de König-Huygens, construction géométrique précise du Boxplot (critère d'exclusion des valeurs aberrantes à 1.5 * IQR).

### 2. Théorie des Probabilités & Théorèmes Limites
* **Fondations** : Théorème de Bayes (forme simple et généralisée par partition), propriétés avancées de l'espérance conditionnelle et de la covariance (bilinéarité, changements d'échelle).
* **Comportements Limites** : Distinctions fondamentales entre la Loi Faible (convergence en probabilité) et la Loi Forte des Grands Nombres (convergence quasi-sûre).
* **Inférence Asymptotique** : Théorème Central Limite (TCL) pour les variables standardisées et application de la Méthode Delta pour les fonctions continûment dérivables g(.).

### 3. Estimation Ponctuelle & Asymptotique
* **Méthodes d'estimation** : Méthode des Moments (MOM) et Maximum de Vraisemblance (ML) via la résolution de l'équation de score et la vérification de la condition de concavité locale.
* **Optimisation d'EQM** : Décomposition du compromis Biais-Variance. Étude de cas sur la minimisation de l'EQM de la variance sous loi normale.
* **Information de Fisher** : Calculs théoriques et observés (In(theta) vs Jn(theta)), variances asymptotiques, et analyse des limites du modèle sur les structures non régulières (ex : Loi Uniforme U(0, theta)).
* **Queues Lourdes** : Comportement de la loi de Pareto et effondrement des théorèmes standards (TCL) lorsque la condition sur les moments (alpha > 1 ou alpha > 2) n'est plus satisfaite.

### 4. Intervalles de Confiance (IC)
* **Théorie des Pivots** : Identification de pivots exacts normaux (Loi de Student t_n-1 vs N(0,1)) et non normaux (Loi Uniforme via le maximum d'échantillon Mn).
* **Approches Asymptotiques** : IC construits à partir de l'Information de Fisher observée et du TCL appliqué.

### 5. Régression Linéaire Simple
* **Moindres Carrés Ordinaires (MCO)** : Preuve d'unicité du minimum global via le déterminant strictement positif de la matrice Hessienne.
* **Analyse de la Variance (ANOVA)** : Décomposition de la somme des carrés (SCTotal = SCR + SCE), calcul du coefficient de détermination R^2 et de sa version ajustée R^2_adj.
* **Inférence sur la Pente** : Distribution exacte de l'estimateur beta_n, erreur-type, intervalles de confiance associés et statistiques de tests d'hypothèses de non-linéarité.

### 6. Distributions Usuelles & Tests du Chi-deux (X^2)
* **Formulaire de lois** : Synthèse compacte (Support, Densité/Masse, Espérance, Variance, Fisher) pour les lois Uniforme, Exponentielle, Poisson, Binomiale et Normale.
* **Tests d'Adéquation & d'Indépendance** : Formulation des statistiques de test, calcul des degrés de liberté nu (ajustés selon les paramètres estimés c), et critères géométriques de rejet basés sur les quantiles théoriques.

---

## Structure du Répertoire

```text
.
├── Formulaire_Proba.tex      # Fichier source LaTeX principal
├── Formulaire_Proba.pdf      # Version compilée prête à l'impression (référence principale)
├── figures/                  # TikZ ou graphiques vectoriels éventuels
└── README.md                 # Description du dépôt
```
## Compilation Locale

Le document utilise des packages standards de l'écosystème de l'AMS ainsi que des environnements multicolonnes optimisés pour les aide-mémoires d'examen. Pour générer le PDF à partir des sources :

```bash
# Utilisation de latexmk pour gérer automatiquement les dépendances de compilation
latexmk -pdf Formulaire_Proba.tex

# Ou via une compilation classique pdflatex
pdflatex Formulaire_Proba.tex
```

> Note technique : Assure-toi de disposer d'une distribution TeX Live (ou MiKTeX) complète incluant amsmath, amsfonts, amssymb et multicol pour éviter toute rupture de compilation des structures de matrices ou de symboles probabilistes (comme les opérateurs d'espérance ou de convergence).

---

## Licence

Ce projet est distribué sous licence MIT. Libre à toi de le cloner, de le modifier et de l'adapter pour tes propres révisions à l'EPFL ou ailleurs. Les pull requests visant à corriger des coquilles ou à enrichir certaines sections (notamment la méthode Delta ou l'ANOVA) sont les bienvenues.
