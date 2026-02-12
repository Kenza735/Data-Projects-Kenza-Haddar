# Analyse de l'évolution des cambriolages en France (2016-2025)

## Objectif du projet :
Ce projet personnel est né de mon expérience en tant que conseillère en déclaration de sinistres dans le secteur de l’assurance. Il vise à confronter cette expérience de terrain aux données statistiques nationales afin d’analyser l’évolution réelle des cambriolages et tentatives de cambriolages en France.
L’objectif principal est d’identifier la tendance sur la période 2016–2025 et d’évaluer l’existence d’une rupture structurelle liée à la crise sanitaire de 2020.

## Source des données utilisées :
Les données proviennent de la plateforme officielle [data.gouv.fr](././https://www.data.gouv.fr/datasets/service-statistique-ministeriel-de-la-securite-interieure-base-des-series-chronologiques)
Elles couvrent la période de janvier 2016 à décembre 2025, avec une fréquence mensuelle (114 observations).

## Variables utilisées :
Variable dépendante : Nombre mensuel de cambriolages et tentatives de cambriolages.
Variable principale : Temps (index mensuel).
Variable de rupture : Crise sanitaire/Confinement (variable binaire avant et après mars 2020).

## Analyse de l'évolution des cambriolages et tentatives de cambriolages sur R Studio : 

Nettoyage et préparation des données :
Filtrage et préparation des variables en lien avec le cambriolage sur **Excel**.
J'ai séléctionné les données en lien avec les cambriolages.

[Base de données](./cambriolage_données.ods)


**Méthodes statistiques :**

Script : [Code_projet_cambriolages.Rmd](./code_projet_cambriolages.Rmd)

- **Analyse descriptive**
    - Les statistiques descriptives permettent d'avoir des informations sur l'ensemble des cambriolages ou tentatives de cambriolages de 2016 à 2025.
    - Sortie de code : [Tableau des statistiques descriptives](./sortie_code_stats_descriptives.png)
      
- **Modélisation de la tendance par Régression Linéaire (MCO)**.
    - Sortie de code : [tableau MCO](./sortie_code_MCO.png)
      La régression simple montre une tendance décroissante significative du nombre de cambriolages (β = -35,1, p < 0,001), indiquant une diminution globale au fil du temps.

- **Modélisation par variable binaire** pour tester l'existence d'une rupture structurelle liée à la crise sanitaire de 2020 (Covid-19) :
    - Sortie de code : [Tableau MCO multiple](./sortie_code_MCO_covid.png)
      L'introduction de la variable binaire améliore nettement la précision du modèle ($R^2$ ajusté à 52,7 %) et confirme un "effet Covid"
      La régression multiple montre une tendance croissante du nombre de cambriolages ( β = 33.95, p < 0,001).
      
    - Boîte à moustage : [Boxplot](./Boite_a_moustache_avant_après_covid.pdf)
    - Graphique de l'évolution temporelle du sinistre avec un marquage pour mars 2020 : [Graphique de l'évolution temporelle](./Graph_evolution_cambriolages.png)
      Le graphique d’évolution temporelle met en évidence une tendance globale décroissante ainsi qu’une rupture visuelle autour de mars 2020, ce qui correspond au début du        confinement en France.
 
  
---
*Pour une analyse détaillée de la méthodologie et des conclusions, consultez la page dédiée sur mon [Portfolio Notion](https://www.notion.so/Kenza-Haddar-2d8c042088c3801a89e8f8f1a9b43b64).*
