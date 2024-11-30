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

