# Référence des méthodes

Table des matières : 1. MCO · 2. Panel · 3. Séries temporelles (stationnarité, ARIMA, VAR) · 4. Causalité (DiD, VI) · 5. Régression à seuil · 6. Variables qualitatives et de comptage · 7. Tests d'hypothèses

## 1. Moindres carrés ordinaires (MCO)

**Usage :** relation linéaire entre une variable expliquée et des explicatives, en coupe transversale ou en série simple.

**Hypothèses clés :** linéarité en paramètres, absence de corrélation entre explicatives et erreur (exogénéité), variance des erreurs constante ou corrigée, absence de multicolinéarité parfaite.

**Vérifications :** VIF (au-delà de 10, problème sérieux), test de Breusch-Pagan ou White pour l'hétéroscédasticité, erreurs robustes par défaut, test RESET pour la forme fonctionnelle.

**Pièges :** lire un coefficient sans tenir compte de l'échelle des variables ; confondre effet marginal et élasticité (passer au log si l'effet proportionnel a du sens) ; oublier les variables omises.

## 2. Données de panel

**Usage :** observations répétées sur les mêmes unités (ménages, entreprises, pays, régions) dans le temps.

**Modèles :** effets fixes (contrôle des caractéristiques inobservables constantes dans le temps, identification à partir des variations internes) ; effets aléatoires (plus efficace si l'hypothèse de non-corrélation est valide). Le test de Hausman arbitre entre les deux.

**Vérifications :** erreurs groupées (cluster) au niveau de l'unité ; dépendance transversale si les unités sont corrélées (pays voisins, chocs communs) ; variables invariantes dans le temps non identifiables en effets fixes.

**Pièges :** effets fixes avec très peu de périodes ; ignorer la dynamique (si la variable dépendante retardée figure dans le modèle, les estimateurs classiques sont biaisés : utiliser Arellano-Bond ou System GMM, avec test de suridentification).

## 3. Séries temporelles

### Stationnarité

Tester la racine unitaire (Dickey-Fuller augmenté, Phillips-Perron ou KPSS, idéalement les deux) avant toute régression. Une régression entre deux séries non stationnaires peut produire une fausse relation (régression fallacieuse).

### Cointégration

Si deux séries ou plus sont intégrées de même ordre et une combinaison linéaire est stationnaire, utiliser le modèle à correction d'erreur (test de Johansen pour plusieurs séries, Engle-Granger pour deux).

### ARIMA et prévision

Identifier l'ordre par les fonctions d'autocorrélation et d'autocorrélation partielle, estimer, vérifier que les résidus sont un bruit blanc (test de Ljung-Box). Évaluer la prévision sur un échantillon hors-période (erreur quadratique moyenne, erreur absolue moyenne). Ne jamais présenter une prévision sans intervalle.

### VAR

Choisir le nombre de retards par critère d'information (AIC, BIC). Analyser les fonctions de réponse impulsionnelle et la décomposition de la variance. Le sens de l'identification (ordre des variables ou restrictions) doit être justifié économiquement.

**Pièges :** ruptures structurelles (tester avec Chow ou Bai-Perron) ; saisonnalité non traitée ; trop de retards pour un petit échantillon.

## 4. Inférence causale

### Différence-de-différences (DiD)

**Usage :** évaluer l'effet d'une intervention en comparant un groupe traité à un groupe témoin avant et après.

**Hypothèse centrale :** tendance parallèle, c'est-à-dire qu'en l'absence de traitement les deux groupes auraient évolué de façon identique. Vérifier graphiquement et par test sur les périodes pré-traitement (tendances d'événements).

**Pièges :** traitement adopté à des dates différentes (utiliser les estimateurs robustes aux effets de traitement hétérogènes) ; erreurs non groupées ; échantillon de groupe témoin trop différent.

### Variables instrumentales (VI)

**Usage :** lorsqu'une explicative est endogène (corrélée à l'erreur).

**Conditions :** pertinence (l'instrument est corrélé à la variable endogène, à vérifier par la première étape : F supérieur à 10 au minimum, idéalement davantage) et exogénéité (l'instrument n'affecte la variable dépendante que par la variable endogène, non testable directement sauf en cas de sur-identification, via le test de Sargan-Hansen).

**Pièges :** instruments faibles (biais important) ; justifier l'exogénéité par un argument économique, pas seulement statistique.

## 5. Régression à seuil

**Usage :** l'effet d'une variable change selon qu'une autre dépasse un seuil inconnu.

**Méthode :** estimer le seuil par minimisation de la somme des carrés résiduels ; tester l'existence d'un seuil (test de type Hansen, avec distribution corrigée car le seuil n'est pas identifié sous l'hypothèse nulle) ; construire l'intervalle de confiance du seuil.

**Pièges :** ne pas tester l'existence du seuil avant de l'estimer ; seuil estimé à la limite de l'échantillon.

## 6. Variables qualitatives et de comptage

- **Logit ou probit** pour une variable binaire : rapporter les effets marginaux moyens, pas seulement les coefficients, qui n'ont pas d'interprétation directe.
- **Modèle multinomial ou ordonné** pour plusieurs catégories (ordonnées ou non).
- **Poisson ou binomiale négative** pour des comptes : si la variance dépasse fortement la moyenne, préférer la binomiale négative.
- **Modèle Tobit** lorsque la variable est censurée (par exemple, zéros massifs).

## 7. Tests d'hypothèses

- Choisir le test selon la nature des données et l'hypothèse nulle. Énoncer l'hypothèse nulle et l'hypothèse alternative avant le calcul.
- Rapporter la statistique, la p-valeur et la taille de l'effet ou l'intervalle de confiance.
- Corriger les comparaisons multiples si plusieurs tests sont menés (Bonferroni, Holm, ou taux de fausses découvertes).
- Une p-valeur de 0,06 n'est pas l'absence d'effet ; une p-valeur de 0,001 sur un effet minuscule n'est pas un résultat important.
