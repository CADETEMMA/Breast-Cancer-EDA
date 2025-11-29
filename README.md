# Breast-Cancer-EDA

Présentation du projet : 
Ce projet se concentre sur l'analyse exploratoire des données (EDA) du dataset SEER Breast Cancer. L'objectif est d'analyser les données démographiques des patients, les types de cancer, les taux de survie, et les résultats des traitements. Le projet utilise des méthodes statistiques et des visualisations des données à partir du dataset, dans le but de fournir des conclusions utiles aux professionnels de santé et aux chercheurs en cancérologie

Objectifs principaux :
- Analyse exploratoire des données (EDA) pour comprendre la répartition et les caractéristiques des patients atteints de cancer du sein.
- Analyse statistique pour identifier les corrélations entre les données démographiques (âge, sexe) et les résultats de survie.
- Analyse de survie et visualisation des résultats des patients en fonction de diverses variables (par exemple, l'âge, le stade du cancer).
- Identifier les facteurs déterminants qui influencent la survie des patients atteints de cancer du sein.

Dataset : 
Source : SEER (Surveillance, Epidemiology, and End Results) du National Cancer Institute (NCI)
Description du dataset : Ce dataset contient des informations sur les cas de cancer du sein avec plusieurs attributs, tels que :
Données démographiques des patients (âge, sexe, origine ethnique, statut marital)
Informations sur le cancer (stade du cancer, type de cancer, année du diagnostic)
Données de survie (taux de survie, durée jusqu'au décès)

Méthodes utilisées : 

Nettoyage des données :
Traitement des données manquantes (imputation avec la médiane ou le mode)
Suppression des colonnes inutiles
Suppression des doublons

Analyse exploratoire des données (EDA) :
Statistiques descriptives (moyenne, médiane, écart-type)
Visualisations des données (histogrammes, boxplots, diagrammes de dispersion)

Analyse statistique :
Corrélation entre les variables numériques
Test de Chi² pour les variables catégorielles
Test t pour comparer l'âge en fonction du sexe

Analyse de survie :
Courbes de survie de Kaplan-Meier
Modèle de Cox pour l'analyse des risques proportionnels

Mode d'emploi pour exécuter le projet : 
1) cloner le repostitory
git clone https://github.com/ton-username/SEER-Breast-Cancer-EDA.git

2) installer les dépendances
cd SEER-Breast-Cancer-EDA
pip install -r requirements.txt

3) executer le code
jupyter notebook notebooks/SEER_Breast_Cancer_EDA.ipynb


Le projet nécessite les librairies Python suivantes :
pandas - Pour la manipulation et l'analyse des données
numpy - Pour les opérations numériques
matplotlib - Pour les graphiques et visualisations
seaborn - Pour la visualisation statistique des données
scipy - Pour les tests statistiques (Chi², t-tests)
lifelines - Pour l'analyse de survie (Kaplan-Meier, modèle de Cox)
ydata_profiling - Pour générer des rapports interactifs 

Principaux résultats et conclusions :
L'âge moyen des patients est d'environ 54 ans.
La taille moyenne des tumeurs est de 30.5 mm (3 cm), avec une variation assez large (écart-type de 21.12).
En moyenne, 14 ganglions lymphatiques ont été examinés par patient, avec un écart-type de 8.1
En moyenne, 4.16 ganglions lymphatiques sont positifs pour les cellules cancéreuses, avec un écart-type de 5.11.
La durée de survie moyenne des patients est de 71.3 mois (environ 5 ans et 11 mois). L’écart-type de 22.92 mois montre qu'il existe une variation importante dans les durées de survie des patients.

