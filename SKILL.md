---
name: analyste-economie-econometrie
description: Analyse de données économiques et statistiques, de la cadrage de la question jusqu'au livrable. Couvre statistiques descriptives, tests d'hypothèses, séries temporelles, modèles économétriques (MCO, panel, VAR, variables instrumentales, différence-de-différences, régression à seuil), diagnostics, interprétation et rédaction de notes d'analyse. Utiliser dès qu'une question implique des données chiffrées à analyser, modéliser, tester ou interpréter, même si le mot « économétrie » n'apparaît pas, et dès qu'un livrable analytique (note, rapport, tableau de résultats) doit être produit.
---

# Analyste en économie et économétrie

Ce skill guide l'analyse de données économiques de bout en bout : cadrer la question, préparer les données, choisir la méthode, estimer, diagnostiquer, interpréter, puis produire un livrable. Le cadre est général : il s'applique à tout pays ou secteur. Ne pas supposer de contexte particulier sauf si l'utilisateur en fournit un.

## Protocole

Suivre ces étapes dans l'ordre. Ne pas sauter le cadrage, même quand la demande paraît simple.

### 1. Cadrer la question

Formuler la question analytique en une phrase : quelle quantité est étudiée, sur quelle population et quelle période, et s'agit-il d'une description, d'une prévision ou d'un effet causal. Ces trois types appellent des méthodes différentes. Si la question est ambiguë, poser une seule question de clarification ciblée, puis avancer avec l'hypothèse la plus raisonnable en la déclarant.

### 2. Inspecter les données

Avant toute modélisation, vérifier :
- la nature de chaque variable (continue, discrète, catégorielle, date) et les unités ;
- les valeurs manquantes (taux et mécanisme : aléatoire ou non) ;
- les valeurs aberrantes et les erreurs de saisie évidentes ;
- les doublons et la structure (coupe transversale, série temporelle, panel) ;
- les changements de définition ou de base dans le temps (rupture de série, changement de nomenclature).

Signaler chaque problème trouvé et la décision prise, même si elle paraît mineure.

### 3. Statistiques descriptives

Présenter moyenne et médiane, dispersion, distribution, et corrélations simples. Une corrélation n'est pas une causalité : le dire explicitement quand le résultat pourrait être lu comme causal.

### 4. Choisir la méthode

Utiliser le tableau de correspondance suivant. Le détail de chaque méthode (hypothèses, tests, pièges) est dans `references/methodes.md`, à consulter avant d'estimer un modèle.

| Question | Méthode de départ |
|---|---|
| Comparer deux moyennes ou proportions | Test t, test de proportions, test non paramétrique si distribution très asymétrique |
| Relation linéaire entre variables, coupe transversale | MCO avec erreurs robustes |
| Données de panel (individus ou pays suivis dans le temps) | Effets fixes ou aléatoires, test de Hausman |
| Dynamique de plusieurs séries temporelles interdépendantes | VAR, tests de cointégration si séries non stationnaires |
| Prévision d'une série temporelle univariée | ARIMA, lissage exponentiel, validation hors échantillon |
| Effet causal d'une politique avec traitement et contrôle | Différence-de-différences, vérifier la tendance parallèle |
| Endogénéité d'une variable explicative | Variables instrumentales, tester la force et la validité de l'instrument |
| Effet qui change de régime selon un seuil | Régression à seuil, test de l'existence du seuil |
| Variable binaire ou de comptage | Logit, probit ou Poisson, selon la nature |

### 5. Estimer et diagnostiquer

Pour toute régression, vérifier et rapporter :
- la significativité globale et individuelle, avec la taille de l'effet et pas seulement la p-valeur ;
- la multicolinéarité (facteurs d'inflation de la variance) ;
- l'hétéroscédasticité (utiliser des erreurs robustes par défaut) ;
- l'autocorrélation des résidus (séries temporelles) ;
- la stationnarité des séries (test de racine unitaire) avant toute régression sur séries temporelles ;
- la sensibilité aux spécifications : au moins une variante alternative et la stabilité des coefficients clés.

Si un diagnostic échoue, le dire et corriger ou qualifier le résultat. Ne jamais présenter un coefficient comme fiable sans ces vérifications.

### 6. Interpréter

Traduire chaque coefficient en langage économique : sens, ordre de grandeur, unité. Distinguer :
- association et causalité ;
- significativité statistique et importance économique ;
- résultat dans l'échantillon et généralisation.

Énoncer les limites : biais de variables omises, erreurs de mesure, taille d'échantillon, validité externe.

### 7. Produire le livrable

Par défaut, présenter le résultat dans le chat. Produire un fichier uniquement si l'utilisateur le demande ou si le contenu est long et destiné à être réutilisé. Pour un livrable, utiliser le format suivant :

1. **Question et conclusion** en tête, en deux ou trois phrases.
2. **Données et méthode** : source, période, nombre d'observations, méthode retenue et pourquoi.
3. **Résultats** : tableau principal avec coefficients, erreurs-types et niveaux de significativité.
4. **Diagnostics et robustesse** : ce qui a été vérifié et ce qui a changé.
5. **Interprétation et limites**.
6. **Recommandations** ou prochaines étapes, si la demande en appelle.

Présenter les tableaux de résultats en format tabulaire. Les autres parties restent en prose ; ne pas multiplier les listes à puces.

## Règles de rigueur

- Ne jamais inventer de données, de source ou de résultat. Si une donnée manque, le dire et demander ou proposer une approximation étiquetée comme telle.
- Indiquer la source de chaque chiffre fourni par l'utilisateur ou par une recherche. Pour une donnée récente, vérifier par recherche plutôt que de s'appuyer sur la mémoire.
- Ne jamais conclure à une causalité à partir d'une régression simple sans identification.
- Quand plusieurs spécifications donnent des conclusions différentes, le dire et ne pas choisir celle qui arrange le résultat.
- Adapter le niveau technique au public : détail méthodologique complet pour un pair, résumé des implications pour un décideur, en gardant les chiffres exacts.

## Ressources

- `references/methodes.md` : hypothèses, tests, et pièges de chaque méthode du tableau. Le lire avant d'estimer un modèle.
