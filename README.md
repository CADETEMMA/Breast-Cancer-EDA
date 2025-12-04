# Breast-Cancer-EDA

Présentation du projet : 
Ce projet porte sur l’analyse exploratoire du dataset SEER Breast Cancer.
L’objectif est de comprendre les caractéristiques démographiques et cliniques des patientes, d’étudier leurs survies, et d’identifier les facteurs influençant le pronostic.

L’étude comprend :
une EDA complète,
des tests statistiques univariés,
une analyse de survie (Kaplan-Meier),
un modèle de Cox multivarié.

Ce projet s’inscrit dans une démarche d’aide à la compréhension des facteurs pronostiques utilisés en cancérologie.

Objectifs principaux : 
Décrire les patientes atteintes de cancer du sein (âge, race, statut marital…).
Analyser les caractéristiques tumorales (stades T/N, grade, récepteurs hormonaux).
Étudier les facteurs influençant la survie globale.
Identifier les facteurs pronostiques indépendants via un modèle de Cox.

Dataset : 
Source : SEER (Surveillance, Epidemiology, and End Results) du National Cancer Institute (NCI)
Ce dataset contient des informations sur :
Données démographiques des patients (âge, sexe, origine ethnique, statut marital)
Informations sur le cancer (stade du cancer, type de cancer, année du diagnostic)
Données de survie (taux de survie, durée jusqu'au décès)

Méthodes utilisées : 
Nettoyage des données:
Gestion des valeurs manquantes (imputation médiane ou mode)
Suppression des doublons
Standardisation / nettoyage des colonnes catégorielles

Analyse exploratoire:
Statistiques descriptives
Visualisations : histogrammes, boxplots, heatmaps, nuages de points

Analyse statistique:
Corrélations entre variables numériques
Tests du Chi² pour variables catégorielles
Tests t pour comparer les moyennes
ANOVA pour comparer la survie selon plusieurs groupes

Analyse de survie:
Courbes Kaplan-Meier
Tests log-rank
Modèle Cox proportional hazards

Librairies utilisées :
pandas – Manipulation de données
numpy – Calcul numérique
matplotlib – Visualisation
seaborn – Graphiques statistiques
scipy – Tests statistiques
lifelines – Analyse de survie (Kaplan-Meier, Cox) 

Principaux résultats et conclusions :
1. Statistiques descriptives
Âge moyen : 54 ans
Taille tumorale moyenne : 30.5 mm
Ganglions examinés : 14 en moyenne
Ganglions positifs : 4.16 en moyenne
Survie moyenne : 71.3 mois (~6 ans)

Ces valeurs confirment la grande variabilité des situations cliniques.

2. Tests du Chi² : relations entre variables catégorielles
De nombreuses associations significatives (p < 0.05) ont été observées :

Associations majeures :
Race VS Grade, ER status, PR status, Survie
Statut marital VS Stades N / 6th stage / survie
Stades T, N, Grade, A stage VS survie

Statuts hormonaux fortement associés entre eux et au statut de survie

=> Ces interdépendances justifient l'utilisation d'un modèle multivarié comme le modèle de Cox.

3. Tests t
ER+ → survie significativement meilleure (p < 0.0001)
PR+ → survie significativement meilleure (p < 0.0001)

4. ANOVA : survie selon les stades
Toutes les ANOVA sont significatives :
N Stage -> p-value = 	0.0000	survie diminue fortement avec N2/N3
T Stage	p-value = 0.0000	T3/T4 = survie nettement réduite
Grade	p-value = 0.0001	Grade élevé = mauvais pronostic

5. Courbes Kaplan-Meier
Statut hormonal
ER+ / PR+ = meilleure survie

Stades tumoraux
T1 > T2 > T3 > T4
N0 > N1 > N2 > N3
Grade I > Grade II > Grade III > Grade IV

6. Modèle de Cox : facteurs indépendants de survie

Le modèle ajusté met en évidence des facteurs pronostiques indépendants, même après correction pour les autres variables.

Facteurs augmentant le risque (HR > 1) : 
N3 : HR = 3.22 (effet très fort)
N2 : HR = 1.82
T4 : HR = 2.22
Grade III : HR = 1.42
Grade IV : HR = 3.17
Âge : HR = 1.02 par année

Facteurs protecteurs (HR < 1) : 
Estrogen+ : HR = 0.52
Progesterone+ : HR = 0.61
Grade I : HR = 0.65

Performance du modèle : 
Concordance = 0.73 → bonne capacité prédictive
Log-likelihood ratio p < 0.0001

=> Le modèle est robuste et confirme les résultats univariés et Kaplan-Meier.

Conclusion générale
Cette analyse permet de mettre en évidence les facteurs les plus importants pour le pronostic des patientes atteintes d’un cancer du sein.
Les variables liées au stade tumoral (T, N, Grade) et les statuts hormonaux (ER/PR) jouent un rôle majeur dans la survie.

Le modèle de Cox a identifié des facteurs pronostiques indépendants, notamment :
âge
stades T4, N2, N3
grade tumoral
statut ER et PR positif (protecteurs)

Ces résultats sont cohérents avec la littérature clinique et montrent la pertinence des données SEER dans l’étude du cancer du sein.
Le modèle Cox montre une bonne capacité prédictive (concordance = 0.73) et confirme les résultats obtenus par Kaplan-Meier et les tests univariés.

