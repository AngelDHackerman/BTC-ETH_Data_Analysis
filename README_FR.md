#### ⚠️ Avertissement ! Ce n'est PAS un conseil financier ! Plus de détails [ici](./disclaimers/DISCLAIMER.md). 👀

Quieres leerlo en español? [click aqui](./README_ES.md).

What to read it in English? [click here](/README.md).

# Comprendre Bitcoin et le S&P 500 : Une analyse comparative basée sur les données

<a id='main-questions'></a>

## Quelles questions cherchons-nous à répondre avec ce projet ?

En utilisant des données publiques, ce projet tentera de répondre à ces questions très intéressantes, tout en analysant le comportement du Bitcoin et du S&P 500 au fil du temps :

0. [Analyse temporelle de Bitcoin (BTC) et S&P 500 au cours des 10 dernières années. **(Hebdomadaire, Mensuel, Annuel)**](#temporal-analysis)
1. [La corrélation entre Bitcoin et le S&P 500 est-elle plus forte en période de crise économique, est-ce vrai ?](#correlation-analysis)
2. [Bitcoin montre une forte volatilité par rapport au S&P 500, mais à quel point BTC est-il volatil par rapport au S&P 500 ?](#volatility-analysis)
3. [Qu'offre de meilleurs rendements : la volatilité de Bitcoin ou la cohérence du S&P 500 ?](#Returns-Time)
4. [**Bonus !** Points clés pour les parties prenantes](#takeaways)

En utilisant différentes techniques telles que :

  * Statistiques 
  * Analytique
  * Finances 
  * Récit
  * Pensée critique

Avec des outils comme : 

  * __Python__
  * __Numpy__
  * __Pandas__
  * __Matplotlib__
  * __Seaborn__

Je répondrai à ces questions très intéressantes, profitez-en !

## **Ensembles de Données**
### Aperçu

Les ensembles de données incluent les prix quotidiens de Bitcoin et du S&P 500 de **septembre 2014 à mai 2024**.

### Principales Étapes de Prétraitement :

1. **Gestion des Valeurs Manquantes** :
   - Les valeurs manquantes ont été supprimées pour garantir l'intégrité des données, car elles représentaient moins de 1 % de l'ensemble de données.
2. **Suppression des Données du Week-end** :
   - Les données de Bitcoin ont été alignées avec celles du S&P 500, qui ne se négocie que les jours ouvrables.
3. **Nettoyage des Données** :
   - Les doublons ont été supprimés et l'alignement temporel entre les ensembles de données a été assuré.

## **Flux de Travail du Projet**

### Étape 1 et 2 : Enquête Initiale
- Une analyse exploratoire a été réalisée en utilisant `.head()`, `.info()` et `.describe()` pour comprendre les ensembles de données.
- Les fichiers pertinents ont été combinés pour créer des ensembles de données unifiés pour Bitcoin et l'indice S&P 500.
- Une haute qualité des données a été assurée en supprimant les lignes nulles et en double.
- Le type de données dans des colonnes comme 'Date' a été modifié en `datetime64` pour un meilleur traitement avec les ensembles de données.
- En utilisant la méthode de l'Écart Interquartile (IQR), certains points aberrants ont été identifiés dans les deux ensembles de données ; ils ont été conservés pour observer les comportements du marché lors d'événements extrêmes.
- Les données ont été exportées dans un fichier pour BTC et S&P500.

Consultez les détails supplémentaires dans les notebooks pour ces étapes :
* [Exploration Initiale S&P 500](./1_Inital_Exploration_SP_500.ipynb)
* [Exploration Initiale BTC](./1_Initial_Exploraion_BTC.ipynb)
* [Comparaison BTC et S&P 500](./2_BTC_SP500_Comparation.ipynb)

### Étape 3 : Évaluation de la Qualité

- L'intégrité des données a été vérifiée en contrôlant les **valeurs manquantes**, **doublons** et **plages de valeurs logiques**.
- Les ensembles de données sont alignés temporellement, garantissant qu'ils ont des plages de dates identiques.
- Les données sont propres, cohérentes et fiables dans les deux ensembles de données.

Consultez les **observations** et **conclusions** supplémentaires dans le notebook :
* [Évaluation de la Qualité pour BTC et S&P 500](./3_Quality_Evaluation_BTC_SP500.ipynb)

<a id='temporal-analysis'></a>

# Analyse temporelle de Bitcoin (BTC) et S&P 500 au cours des 10 dernières années. **(Hebdomadaire, Mensuel, Annuel)** [⬆️ Retour aux Questions Principales 🤓](#main-questions)

- **Objectif** : Identifier les tendances des prix sur des intervalles hebdomadaires, mensuels, trimestriels et annuels.

- **Résultats** :
  - **Tendances des Prix** :
    - Bitcoin montre une grande variabilité à court terme, tandis que le S&P 500 présente une croissance stable et cohérente. **(Voir [Figure 1](#figure-1))**
    - Les tendances à long terme mettent en évidence la croissance exponentielle et la volatilité de Bitcoin. **(Voir [Figure 2](#figure-2))**
  - **Tendances des Volumes** :
    - Le volume des transactions de Bitcoin est corrélé aux périodes de forte volatilité des prix, augmentant souvent lors de hausses ou de chutes du marché.
    - Le volume des transactions du S&P 500 reste relativement stable, s'alignant sur sa croissance constante.
    - Les augmentations significatives de volume pour Bitcoin précèdent souvent les inversions de prix, suggérant une forte relation entre le sentiment du marché et l'activité commerciale. **(Voir [Figure 3](#figure-3) et [Figure 4](#figure-4))**
  - **Perspectives Comparatives** :
    - Le volume de Bitcoin réagit fortement aux nouvelles du marché et aux événements macroéconomiques, amplifiant sa volatilité.
    - Le volume des transactions du S&P 500 montre une résilience et une moindre sensibilité aux nouvelles à court terme, indiquant une structure de marché mature et stable.
    - Dans les deux cas, en janvier 2018, le prix et le volume de Bitcoin ont dépassé ceux du S&P 500 et ont maintenu cette tendance depuis lors, pour l'instant... **(Voir Figures 1 et 3)** 

---

## **En Mots Simples**:
  - Bitcoin 🪙 affiche une forte volatilité et une croissance exponentielle à long terme 📈, avec des volumes de transactions augmentant considérablement lors d'événements de marché 📊, tandis que le S&P 500 reste stable et moins sensible aux changements à court terme 🛠️📉. **Depuis 2018, Bitcoin a constamment surpassé le S&P 500 en termes de prix 💸 et de volume 🔥**.

Consultez les **observations** et **conclusions** supplémentaires dans le notebook :
* [Analyse Temporelle pour Bitcoin et l'Indice S&P 500](/4_Temporal_Analysis.ipynb)

<a id="figure-1"></a>
**Figure 1.** Prix Moyens Hebdomadaires de BTC et S&P 500 (USD). [⬆️ Retour](#temporal-analysis)

![Prix Moyens Hebdomadaires de BTC et S&P 500 (USD)](./images/Fig1_weekly_prices_BTC_SP500.png)

<a id="figure-3"></a>
**Figure 3.** Volume Hebdomadaire des Transactions de BTC et S&P 500 (par 1 million d'unités). [⬆️ Retour](#temporal-analysis)

![Volume Hebdomadaire des Transactions de BTC et S&P 500](/images/Fig3_weekly_volume_BTC_SP500.png)

**Moyennes Mensuelles.** Prix Moyens Mensuels de BTC et S&P 500 (USD). [⬆️ Retour](#temporal-analysis)

![Prix Moyens Mensuels de BTC et S&P 500 (USD)](/images/monthly_average_price.png)

**Volume Mensuel.** Volume Mensuel de BTC et S&P 500 (USD). [⬆️ Retour](#temporal-analysis)

![Volume Mensuel de BTC et S&P 500 (USD)](/images/monthly_total_volume.png)

<a id="figure-2"></a>
**Figure 2.** Prix Moyens Annuels de BTC et S&P 500 (USD). [⬆️ Retour](#temporal-analysis)

![Prix Moyens Annuels de BTC et S&P 500 (USD)](/images/Fig2_annual_prices_BTC_SP500.png)

<a id="figure-4"></a>
**Figure 4.** Volume Annuel des Transactions de BTC et S&P 500 (par 1 million d'unités). [⬆️ Retour](#temporal-analysis)

![Volume Annuel des Transactions de BTC et S&P 500](/images/Fig4_annual_volume_BTC_SP500.png)

<a id="correlation-analysis"></a>

# La corrélation entre Bitcoin et le S&P 500 est-elle plus élevée en périodes de crise économique ? [⬆️ Retour aux Questions Principales 🤓](#main-questions)

### Analyse des Perspectives (Étape 5.1) :

- **Objectif** : L'objectif de cette analyse était d'explorer la corrélation entre Bitcoin (BTC) et l'Indice S&P 500 durant la crise du COVID-19 (mars 2020 à décembre 2021), la crise énergétique et des approvisionnements (2021-2022) et la crise financière (2023-2024).

- **Plus précisément, l'analyse se concentre sur** :
  - Comprendre le comportement de BTC et du S&P 500 durant des périodes économiques clés.
  - Comparer les tendances des prix et des volumes, ainsi que leurs corrélations, pour identifier des schémas ou anomalies potentiels.
  - Mettre en évidence des perspectives pouvant guider des stratégies d'investissement ou de gestion des risques.

#### Comprendre les Corrélations

  1. **Corrélation Positive** :
    - Si la corrélation est plus proche de **1**, cela indique une **corrélation positive directe**, signifiant que lorsque l'une des variables augmente, l'autre augmente également.

  2. **Corrélation Négative** :
    - Si la corrélation est plus proche de **-1**, cela indique une **corrélation inverse directe**, signifiant que lorsque l'une des variables augmente, l'autre diminue.

  3. **Aucune Corrélation** :
    - Plus la corrélation est proche de **0**, plus la relation est faible, indiquant **peu ou pas de corrélation** entre les deux variables.

### Observations et Conclusions


1. **Tendances Générales**:
   - BTC et le S&P 500 montrent des comportements distincts, avec BTC affichant une plus grande volatilité par rapport au mouvement stable du S&P 500.
   - Les deux actifs montrent des mouvements de prix significatifs pendant des périodes économiques majeures, comme la crise du COVID-19.

<a id='covid-19_correlation'></a>

2. **Analyse de la Période COVID-19 (2020–2021)**:
   - Pendant la pandémie, BTC a connu une forte augmentation des prix **à partir de la fin de 2020, coïncidant avec les mesures de relance budgétaire.** **(Voir [Figure 5, section supérieure](#figure-5))**
   - Le S&P 500 s'est également redressé pendant cette période, reflétant des tendances de reprise similaires sur les marchés traditionnels et de cryptomonnaies.
   - **Perspective de Corrélation**: BTC et le S&P 500 ont montré une **corrélation modérée à forte (0,87)** positive pendant cette période, indiquant un alignement plus étroit des mouvements du marché. **(Voir [Figure 5, section inférieure](#figure-5))**

<a id='supply_energy_correlation'></a>

3. **Crise de l'Énergie et de l'Approvisionnement 2021–2022 (COVID persistant et Guerre Ukraine-Russie)**:
   - Le prix et le volume de BTC ont montré une forte volatilité, avec des baisses significatives pendant les pénuries mondiales d'énergie et les perturbations de la chaîne d'approvisionnement, ainsi qu'avec l'interdiction de Bitcoin en Chine (septembre 2021). **(Voir [Figure 6, section supérieure](#figure-6))**
   - Le S&P 500 a montré des tendances relativement stables, mettant en évidence une résilience par rapport à la sensibilité accrue de BTC aux conditions du marché mondial.
   - **Perspective de Corrélation**: La corrélation entre BTC et le S&P 500 **s'est légèrement affaiblie (0,60)** pendant cette période, mais est restée positive, suggérant un alignement partiel des marchés face à des chocs externes. **(Voir [Figure 6, section inférieure](#figure-6))**

<a id='Economic-crisis'></a>

4. **Crise Économique (2023–2024)**:
   - BTC a montré une croissance significative et maintenu une trajectoire de prix plus élevée, reflétant un intérêt accru des investisseurs spéculatifs recherchant des actifs alternatifs. **(Voir [Figure 7, section supérieure](#figure-7))**
   - Le S&P 500 a présenté des tendances stables avec une reprise progressive, **renforçant son rôle comme indicateur de stabilité économique.**
   - **Perspective de Corrélation**: La corrélation **s'est renforcée (0,90)** pendant cette période, indiquant une **interdépendance accrue entre BTC et les marchés traditionnels** à mesure que BTC s'intègre davantage dans les finances mondiales. **(Voir [Figure 7, section inférieure](#figure-7))**

<a id='volumen-analysis'></a>

5. **Analyse des Volumes**:
   - Le volume des transactions BTC a fortement augmenté pendant les périodes de forte volatilité des prix, montrant une sensibilité aux événements du marché.
   - Les volumes du S&P 500, bien que moins volatils, ont également augmenté pendant l'incertitude du marché.
   - Globalement, il semble que la corrélation "volume-prix" entre Bitcoin et le S&P 500 est **peu forte** et qu'ils sont à peine corrélés. **(Voir [Figure 8](#figure-8))**

### L'Ombre Rouge dans les Graphiques de Corrélation

L'**ombre rouge** dans les graphiques de corrélation représente l'**intervalle de confiance** pour la ligne de régression linéaire. Cet intervalle indique la plage dans laquelle la véritable ligne de régression est susceptible de se situer avec un certain niveau de confiance (généralement 95 %). **Une ombre rouge plus étroite** suggère **une plus grande confiance** et moins de variabilité dans les données, tandis qu'une **ombre plus large** indique **une plus grande incertitude et variabilité** dans la relation entre les prix de BTC et du S&P 500.

Ces observations et perspectives graphiques mettent en évidence collectivement comment BTC et le S&P 500 réagissent dans diverses conditions économiques, démontrant des comportements distincts et des corrélations évolutives au fil du temps.

---

## **En Mots Simples**:
- **📊 Alors, la corrélation entre Bitcoin et le S&P 500 est-elle plus élevée pendant les périodes de crise économique ?**
  - ✅ Oui ! Il semble que la corrélation entre Bitcoin 🪙 et le S&P 500 💰 soit élevée 📈, en particulier pendant les périodes de crises économiques 🔥🌎📉.

Consultez les **observations** et **conclusions** supplémentaires dans le notebook :
* [Analyse des Différentes Crises et Corrélations](/5.1_Insights_Analysis_Crisis_And_Correlations.ipynb)

<a id="figure-5"></a>
**Figure 5.** Prix de Bitcoin et du S&P Pendant la Crise COVID-19 (Prix USD). [⬆️ Retour](#covid-19_correlation)

![Prix de Bitcoin et du S&P Pendant la Crise COVID-19](/images/Fig5_BTC_SP500_price_correlations_Covid-19.png)

<a id="figure-6"></a>
**Figure 6.** Prix de Bitcoin et du S&P Pendant la Crise de l'Énergie et de l'Approvisionnement (Prix USD). [⬆️ Retour](#supply_energy_correlation)

![Prix de Bitcoin et du S&P Pendant la Crise de l'Énergie et de l'Approvisionnement](/images/Fig6_BTC_SP500_Price_Correlations_Supply_Crisis.png)

<a id="figure-7"></a>
**Figure 7.** Crise Économique 2023-2024 (Prix USD). [⬆️ Retour](#Economic-crisis)

![Crise Économique 2023-2024](/images/Fig7_BTC_SP500_Price_Correlation_Economic_crisis.png)

<a id="figure-8"></a>
**Figure 8.** Corrélation Volume-Prix BTC vs S&P 500. [⬆️ Retour](#volumen-analysis)

![Corrélation Volume-Prix BTC vs S&P 500](/images/Fig8_BTC_SP500_Volume_Price_correlation.png)

---

<a id="volatility-analysis"></a>

# Bitcoin montre une forte volatilité par rapport au S&P 500, mais à quel point BTC est-il plus volatil que le S&P 500 ? [⬆️ Retour aux Questions Principales 🤓](#main-questions)
## Analyse de la Volatilité sur des Échelles Mensuelles et Annuelles

### Analyse des Perspectives (Étape 5.2)

- **Objectifs :**
  - Évaluer et comparer la **volatilité** de Bitcoin (BTC) et de l'Indice S&P 500 sur différentes échelles de temps : **mensuelles** et **annuelles**.
  - Analyser et mettre en évidence :
    - **Volatilité Moyenne** : Identifier les fluctuations typiques du marché.
    - **Pic de Volatilité** : Évaluer les mouvements extrêmes du marché.
    - **Différences significatives** et **modèles** de volatilité entre BTC et le S&P 500 au fil du temps.
  - Identifier les événements clés influençant la volatilité des deux actifs.
  - Fournir une compréhension complète du comportement du marché et des risques associés.

### Observations et Conclusions :

<a id="volatility-monthly"></a>

#### Observations Clés :
1. **Volatilité Plus Élevée de Bitcoin** :
  - La volatilité mensuelle moyenne de Bitcoin est environ **4,26 fois plus élevée** **(Voir [Figure 9](#figure-9))** que celle du S&P 500.
  - **À son maximum**, Bitcoin était **1,74 fois** plus volatil que le pic de volatilité mensuelle du S&P 500, ce qui indique que même dans des conditions extrêmes du marché, Bitcoin présente un risque plus élevé.
  - Bitcoin est **4,23 fois** plus volatil que le S&P 500 en moyenne **(annuellement)**. **(Voir [Figure 10](#figure-10))**
  - **À son maximum**, Bitcoin était **2,68 fois** plus volatil que le S&P 500 **(annuellement)**.

2. **Modèles Consistants de Volatilité** :
   - Bitcoin montre constamment une volatilité significativement plus élevée dans les analyses mensuelles et annuelles.
   - **(Voir [Figure 11](#figure-11) et [Figure 12](#figure-12))**

3. **Événements Clés Influant sur la Volatilité** : **(Voir [Figure 11](#figure-11))**
   - **Crash du COVID-19 (2020)** : Augmentations abruptes de la volatilité de Bitcoin.
   - **Adoption Institutionnelle (fin 2020)** : Volatilité maximale observée.
   - **Changements Réglementaires (2023)** : Nouvelles fluctuations, bien que réduites par rapport aux années précédentes.

#### Conclusions :

1. **Bitcoin en tant qu'Actif à Haut Risque** :
   - La volatilité de Bitcoin dépasse significativement celle du S&P 500, réaffirmant son statut d'actif à haut risque.

2. **Sensibilité du Marché aux Événements Externes** :
   - Bitcoin et le S&P 500 montrent une sensibilité aux événements macroéconomiques et réglementaires, mais les réponses de Bitcoin sont plus prononcées.

3. **Potentiel de Diversification** :
   - Malgré sa volatilité, Bitcoin pourrait offrir des avantages de diversification dans des portefeuilles, en particulier pour des stratégies à haut risque et haute récompense.

4. **Implications Futures** :
   - À mesure que l'adoption institutionnelle et la réglementation évoluent, la volatilité de Bitcoin pourrait se stabiliser avec le temps, bien qu'elle reste probablement plus élevée que celle des indices traditionnels comme le S&P 500.

---

## **En Mots Simples**
- **À quel point Bitcoin est-il volatil par rapport au S&P 500 ?**
  - 🪙 Bitcoin affiche une volatilité significativement plus élevée 📈 que le S&P 500 dans presque toutes les métriques évaluées. Cela est particulièrement vrai lors d'événements extrêmes, confirmant sa nature spéculative et son profil à haut risque.
  - Avec une moyenne **mensuelle** environ **4 fois plus élevée** que le S&P 500 et pratiquement **la même volatilité annuelle**.

Consultez les **observations** et **conclusions** supplémentaires dans le notebook :
* [Analyse de la Volatilité](/5.2_Insights_Volatility_Monthly_Yearly.ipynb)

<a id="figure-9"></a>
**Figure 9.** Volatilité Mensuelle Moyenne BTC vs S&P 500. [⬆️ Retour](#volatility-monthly)

![Volatilité Mensuelle Moyenne BTC vs S&P 500](/images/Fig9_BTC_SP500_Volatility.png)

<a id="figure-10"></a>
**Figure 10.** Volatilité Annuelle Moyenne BTC vs S&P 500. [⬆️ Retour](#volatility-monthly)

![Volatilité Annuelle Moyenne BTC vs S&P 500](/images/Fig_10_BTC_SP500_Volatility.png)

<a id="figure-11"></a>
**Figure 11.** Comparaison Mensuelle de la Volatilité BTC vs S&P 500. [⬆️ Retour](#volatility-monthly)

![Comparaison Mensuelle de la Volatilité BTC vs S&P 500](/images/Fig_11_BTC_SP500_Patern_Month.png)

<a id="figure-12"></a>
**Figure 12.** Comparaison Annuelle de la Volatilité BTC vs S&P 500. [⬆️ Retour](#volatility-monthly)

![Comparaison Annuelle de la Volatilité BTC vs S&P 500](/images/Fig_12_BTC_SP500_Patern_Yearly.png)

---

<a id="Returns-Time"></a>

# Qu'est-ce qui offre de meilleurs rendements : la volatilité de Bitcoin ou la constance du S&P 500 ? [⬆️ Retour aux Questions Principales 🤓](#main-questions)

### Observations Clés
1. **Rendements sur Différentes Périodes**:
   - Bitcoin a montré des rendements annuels, trimestriels, mensuels et hebdomadaires significativement plus élevés que le S&P 500, bien qu'avec une plus grande volatilité. **(Voir [Figure 13](#figure-13), [Figure 14](#figure-14), [Figure 15](#figure-15), [Figure 16](#figure-16))**
   - Par exemple :
     - En 2017, le rendement annuel de Bitcoin était d'environ 1300 %, soulignant sa croissance explosive lors des marchés haussiers.

2. **Profits Moyens**:
   - Voici une autre découverte intéressante, les rendements moyens pour **BTC** et **S&P 500** :
   - **Moyenne Hebdomadaire** : Bitcoin 0,62 % vs. S&P 500 0,23 %
   - **Moyenne Mensuelle** : Bitcoin 6,42 % vs. S&P 500 0,83 %
   - **Moyenne Trimestrielle** : Bitcoin 28,45 % vs. S&P 500 3,03 %
   - **Moyenne Annuelle** : Bitcoin 224,01 % vs. S&P 500 11,85 %

   > **Remarque** : L'année 2017 est une anomalie notable qui affecte significativement les profits annuels moyens de Bitcoin.

3. **Compromis Risque-Rendement**:
   - Malgré sa volatilité, Bitcoin a constamment surperformé le S&P 500 dans la plupart des métriques, en faisant une **option attrayante pour les investisseurs tolérants au risque**.

### Observations et Conclusions
1. **Analyse de la Performance**:
   - Les rendements de Bitcoin sont extraordinaires lors des marchés haussiers, tandis que le S&P 500 fournit des rendements réguliers dans le temps.
   - Le risque associé à la volatilité de Bitcoin est compensé par son potentiel élevé de gains substantiels.

2. **Opportunités de Diversification**:
   - Incorporer les deux actifs dans un portefeuille permet d'équilibrer les rendements élevés de Bitcoin avec la stabilité du S&P 500.

3. **Perspectives pour les Parties Prenantes**:
   - Les investisseurs recherchant une stabilité à long terme peuvent préférer le S&P 500.
   - Les investisseurs à haut risque cherchant des rendements exponentiels pourraient bénéficier de Bitcoin.

---

## En Mots Simples
- Bitcoin 📈 offre un potentiel énorme de gains, mais il est volatil 💥 et risqué.
- Le S&P 500 📊 est un choix fiable pour ceux qui préfèrent une croissance stable et constante 💼.
- Combiner les deux pourrait offrir une stratégie d'investissement équilibrée : rendements élevés avec stabilité 🌎.

<a id="figure-13"></a>
**Figure 13.** Rendements Annuels au Fil du Temps. [⬆️ Retour](#Returns-Time)

![Rendements Annuels au Fil du Temps](/images/Annual_Returns.png)

#### Par exemple : Si vous aviez investi X montant en janvier 2017 et retiré votre argent fin décembre 2017, vous auriez réalisé un profit de 1300 %.

<a id="figure-14"></a>
**Figure 14.** Rendements Trimestriels au Fil du Temps. [⬆️ Retour](#Returns-Time)

![Rendements Trimestriels au Fil du Temps](/images/Quarterly_Returns.png)

#### Par exemple : Si vous aviez investi X montant en janvier 2017 et retiré votre argent en mars 2017, vous auriez réalisé un profit d'environ 120 %.

<a id="figure-15"></a>
**Figure 15.** Rendements Mensuels au Fil du Temps. [⬆️ Retour](#Returns-Time)

![Rendements Mensuels au Fil du Temps](/images/Monthly_Returns.png)

#### Par exemple : Si vous aviez investi X montant le 3 janvier 2017 et retiré votre argent le 31 janvier 2017, vous auriez réalisé un profit d'environ 20 %.

<a id="figure-16"></a>
**Figure 16.** Rendements Hebdomadaires au Fil du Temps. [⬆️ Retour](#Returns-Time)

![Rendements Hebdomadaires au Fil du Temps](/images/Weekly_Returns.png)

#### Ici, cela montre essentiellement que vous auriez perdu de l'argent la première semaine de 2017 (environ une perte de 10 %).

Consultez les **observations** et **conclusions** supplémentaires dans le notebook :
* [Analyse des Rendements](/5.3_Inshights_Cumulative_Returns.ipynb)

--- 

<a id="takeaways"></a>

# Points Clés pour les Parties Prenantes [⬆️ Retour aux Questions Principales 🤓](#main-questions)

1. **Corrélations pendant les Périodes de Crise**  
   - Bitcoin et le S&P 500 montrent des corrélations plus fortes lors des périodes de crise économique, comme la pandémie de COVID-19 et la crise financière de 2023, avec une corrélation maximale de **0,90**. Cela suggère une alignement croissant de Bitcoin avec les marchés traditionnels sous le stress économique mondial.

2. **Volatilité et Risque**  
   - La volatilité moyenne de Bitcoin est **4,26 fois plus élevée** que celle du S&P 500 mensuellement et **4,23 fois plus élevée** annuellement, en faisant un actif à haut risque. Cependant, cette volatilité crée aussi des opportunités de rendements significatifs dans les marchés haussiers.

3. **Rendements Supérieurs**  
   - Bitcoin surperforme systématiquement le S&P 500 dans toutes les périodes de temps (hebdomadaire, mensuelle, trimestrielle et annuelle). Par exemple, le rendement annuel moyen de Bitcoin est de **224 %**, contre **11,85 %** pour le S&P 500.

4. **Sensibilité au Marché**  
   - Bitcoin est hautement réactif aux événements mondiaux et aux changements réglementaires, avec des volumes de transactions augmentant lors des chocs de marché. Cela contraste avec le comportement plus stable du S&P 500, mettant en évidence la nature spéculative de Bitcoin.

5. **Stratégies d'Investissement**  
   - Combiner le potentiel de croissance élevé de Bitcoin avec la stabilité du S&P 500 peut équilibrer le risque et la récompense dans les portefeuilles. Alors que Bitcoin convient aux investisseurs à haut risque, le S&P 500 reste idéal pour ceux recherchant une croissance stable et constante.

---

Fait avec amour 💚 par Angel Hackerman 🥷🏻💻 et plusieurs machines d'IA 🤖. Merci pour votre temps! 🤗