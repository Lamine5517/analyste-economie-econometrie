# Analyste en économie et économétrie

Skill Manus pour cadrer, préparer, analyser et interpréter des données économiques et statistiques, puis produire un livrable analytique rigoureux.

## Objectif

Ce skill accompagne une analyse de bout en bout :

1. formuler la question analytique ;
2. inspecter la structure et la qualité des données ;
3. produire les statistiques descriptives pertinentes ;
4. choisir une méthode adaptée à la question ;
5. estimer le modèle et effectuer les diagnostics ;
6. interpréter les résultats en langage économique ;
7. rédiger une note, un rapport ou un tableau de résultats.

Il est conçu pour éviter les erreurs fréquentes : confondre corrélation et causalité, interpréter une p-valeur sans mesurer la taille de l’effet, ignorer les données manquantes ou présenter un modèle sans vérifier ses hypothèses.

## Quand utiliser ce skill

Utiliser ce skill dès qu’une demande implique :

- l’analyse de données chiffrées économiques, sociales, financières ou sectorielles ;
- la comparaison de groupes, de moyennes ou de proportions ;
- l’analyse d’une relation entre variables ;
- une prévision ou l’étude de séries temporelles ;
- l’évaluation d’une politique publique ou d’une intervention ;
- l’analyse de données de panel ;
- un modèle économétrique ou un test statistique ;
- la production d’une note d’analyse, d’un rapport ou d’un tableau de résultats.

Le mot « économétrie » n’a pas besoin d’apparaître explicitement dans la demande pour que le skill soit pertinent.

## Méthodes couvertes

| Question analytique | Méthode de départ |
|---|---|
| Comparer deux moyennes ou proportions | Test t, test de proportions ou test non paramétrique |
| Étudier une relation linéaire en coupe transversale | MCO avec erreurs robustes |
| Suivre plusieurs unités dans le temps | Effets fixes ou aléatoires, avec test de Hausman |
| Prévoir une série temporelle | ARIMA ou lissage exponentiel, avec validation hors échantillon |
| Étudier plusieurs séries interdépendantes | VAR, tests de stationnarité et de cointégration |
| Évaluer une politique avec groupe traité et groupe témoin | Différence-de-différences |
| Traiter l’endogénéité | Variables instrumentales |
| Étudier un changement de régime | Régression à seuil |
| Modéliser une variable binaire | Logit ou probit |
| Modéliser une variable de comptage | Poisson ou binomiale négative |

La référence [`references/methodes.md`](references/methodes.md) précise les hypothèses, contrôles, tests et pièges associés à ces méthodes.

## Workflow appliqué

### 1. Cadrage

Le skill commence par préciser :

- la variable ou la quantité étudiée ;
- la population ou les unités concernées ;
- la période ;
- la nature de la question : description, prévision ou effet causal.

Si la demande est ambiguë, il pose une question de clarification ciblée ou avance avec une hypothèse explicitement déclarée.

### 2. Inspection des données

Avant toute modélisation, l’analyse vérifie notamment :

- les types, unités et définitions des variables ;
- les valeurs manquantes et leur taux ;
- les valeurs aberrantes et les erreurs de saisie ;
- les doublons ;
- la structure des données : coupe transversale, série temporelle ou panel ;
- les ruptures de série et changements de nomenclature.

Chaque problème constaté et chaque décision de traitement doivent être signalés.

### 3. Description statistique

L’analyse présente, selon le besoin :

- moyenne et médiane ;
- dispersion et quantiles ;
- distribution des variables ;
- comparaisons entre groupes ;
- corrélations simples, en rappelant qu’une corrélation ne constitue pas une preuve de causalité.

### 4. Estimation et diagnostics

Pour une régression, le skill demande de rapporter la taille des effets et pas seulement les p-valeurs. Il vérifie également, selon le modèle :

- la significativité globale et individuelle ;
- la multicolinéarité, notamment avec les VIF ;
- l’hétéroscédasticité et l’utilisation d’erreurs robustes ;
- l’autocorrélation des résidus ;
- la stationnarité des séries temporelles ;
- la robustesse à au moins une spécification alternative.

Un diagnostic défavorable doit être corrigé, discuté ou explicitement qualifié. Un coefficient ne doit pas être présenté comme fiable sans ces vérifications.

### 5. Interprétation

Les résultats sont traduits en langage économique : signe, unité, ordre de grandeur et importance économique. L’analyse distingue systématiquement :

- association et causalité ;
- significativité statistique et importance économique ;
- résultat dans l’échantillon et généralisation ;
- résultat estimé et hypothèses nécessaires à son interprétation.

Les limites possibles sont mentionnées : variables omises, erreurs de mesure, faible taille d’échantillon, endogénéité, biais de sélection et validité externe.

## Exemples d’utilisation

### Exemple 1 — Analyse descriptive d’un fichier CSV

> Analyse le fichier `revenus_menages.csv`. Décris la distribution du revenu mensuel par région, compare les moyennes entre zones urbaines et rurales, signale les valeurs manquantes et propose une courte conclusion sans interpréter les différences comme causales.

Le skill doit inspecter les colonnes, les unités, les valeurs manquantes et les valeurs extrêmes avant de produire les tableaux descriptifs.

### Exemple 2 — Régression MCO

> À partir de `productivite_entreprises.xlsx`, estime la relation entre la productivité et l’investissement, la taille de l’entreprise et l’ancienneté. Utilise des erreurs-types robustes, calcule les VIF, teste l’hétéroscédasticité et interprète les coefficients en unités économiques.

Le résultat attendu inclut la spécification, le nombre d’observations, le tableau des coefficients, les erreurs-types, les diagnostics et les limites d’une interprétation causale.

### Exemple 3 — Données de panel

> Estime l’effet des dépenses publiques d’éducation sur le taux de réussite dans un panel de régions observées entre 2010 et 2024. Compare effets fixes et effets aléatoires, applique le test de Hausman et groupe les erreurs au niveau de la région.

Le skill doit vérifier la clé d’identification région-période, la présence de variables invariantes dans le temps et la pertinence du niveau de regroupement des erreurs.

### Exemple 4 — Différence-de-différences

> Évalue l’effet d’un programme de formation introduit en 2021 dans cinq régions traitées, en utilisant les autres régions comme groupe témoin. Vérifie graphiquement l’hypothèse de tendances parallèles et présente une estimation en différence-de-différences avec étude des effets par période.

L’analyse doit discuter la comparabilité des groupes, les tendances pré-traitement, le regroupement des erreurs et les éventuelles dates d’adoption différentes.

### Exemple 5 — Prévision d’une série temporelle

> Prévois les ventes mensuelles des 12 prochains mois à partir de `ventes_mensuelles.csv`. Teste la stationnarité, compare quelques spécifications ARIMA, valide hors échantillon et présente les intervalles de prévision.

Une prévision ne doit pas être présentée sans méthode de validation et sans intervalle d’incertitude.

### Exemple 6 — Variables instrumentales

> Estime l’effet de l’accès au crédit sur l’investissement des petites entreprises en utilisant la distance à l’agence bancaire la plus proche comme instrument. Présente la première étape, la force de l’instrument, l’argument économique d’exogénéité et les limites de l’identification.

Le skill doit distinguer la pertinence statistique de l’instrument et la condition d’exclusion, qui repose principalement sur un argument économique.

### Exemple 7 — Test d’hypothèse

> Compare le taux moyen d’emploi de deux groupes avant et après une réforme. Énonce les hypothèses nulle et alternative, choisis un test approprié, rapporte la statistique, la p-valeur, l’intervalle de confiance et la taille de l’effet.

Si plusieurs comparaisons sont effectuées, le skill doit envisager une correction pour comparaisons multiples.

### Exemple 8 — Note de synthèse pour décideur

> Transforme les résultats de l’analyse en une note de deux pages destinée à un décideur non spécialiste. Commence par la conclusion, conserve les chiffres exacts, explique les implications économiques en langage simple et résume les limites méthodologiques sans jargon inutile.

Le niveau technique doit être adapté au public tout en conservant la précision des estimations.

## Format de livrable recommandé

Lorsqu’un fichier ou une note est demandé, le livrable suit généralement cette structure :

1. **Question et conclusion** : deux ou trois phrases en tête ;
2. **Données et méthode** : source, période, unités, nombre d’observations et justification de la méthode ;
3. **Résultats** : tableau principal avec coefficients, erreurs-types et niveaux de significativité ;
4. **Diagnostics et robustesse** : contrôles effectués et changements entre spécifications ;
5. **Interprétation et limites** ;
6. **Recommandations ou prochaines étapes**, si elles sont pertinentes.

Les tableaux de résultats sont présentés sous forme tabulaire. Les explications restent principalement en prose afin d’éviter la multiplication de listes.

## Règles de rigueur

Le skill impose notamment les règles suivantes :

- ne jamais inventer de données, de sources ou de résultats ;
- indiquer la source de chaque chiffre fourni ou recherché ;
- vérifier les données récentes au lieu de s’appuyer uniquement sur la mémoire ;
- ne jamais conclure à une causalité à partir d’une simple régression sans stratégie d’identification ;
- signaler les conclusions qui changent selon la spécification ;
- distinguer clairement une approximation d’un résultat observé ou estimé.

## Installation dans Manus

Le skill peut être installé depuis le fichier `.skill` fourni avec ce dépôt ou ajouté à l’environnement Manus à partir du fichier `SKILL.md`.

La structure minimale attendue est :

```text
analyste-economie-econometrie/
├── SKILL.md
└── references/
    └── methodes.md
```

## Fichiers du dépôt

- [`SKILL.md`](SKILL.md) : instructions opérationnelles du skill et protocole d’analyse ;
- [`references/methodes.md`](references/methodes.md) : hypothèses, diagnostics et pièges des principales méthodes économétriques ;
- [`README.md`](README.md) : présentation, périmètre et exemples d’utilisation.

## Limites

Ce skill structure et améliore une analyse ; il ne remplace pas la vérification de la qualité des données, le jugement économique ou la connaissance du contexte institutionnel. Les résultats dépendent des données disponibles, des hypothèses retenues et de la validité de la stratégie d’identification.
