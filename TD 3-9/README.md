# Optimisation de la consommation énergétique des bâtiments
La consommation énergétique des bâtiments n'a cessé d'augmenter au cours des dernières décennies à travers le monde, les systèmes de chauffage, de ventilation et de climatisation (CVC) représentant la majeure partie de la consommation d'énergie dans les bâtiments. En optimisant les paramètres de conception dans le but de minimiser les charges de chauffage et de refroidissement, il est possible de minimiser la consommation énergétique totale d'un bâtiment.

Ce processus d'optimisation peut être réalisé en utilisant des outils de simulation capables de prédire les charges de chauffage et de refroidissement en fonction d'un ensemble de paramètres de conception, ainsi qu'en utilisant des algorithmes d'optimisation qui peuvent rechercher l'ensemble optimal de paramètres minimisant les charges de chauffage et de refroidissement. Cependant, l'exécution de simulations en lot à ces fins est longue et coûteuse en calcul.

Dans ce projet, des modèles d'apprentissage automatique ont été entraînés sur un jeu de données disponible de paramètres de conception et de consommation d'énergie correspondante. Une fois les modèles entraînés, ils peuvent être utilisés comme modèles de substitution dans le processus d'optimisation. L'algorithme d'optimisation mettra à jour les modèles et les utilisera pour prédire la consommation d'énergie pour différents ensembles de paramètres de conception, et sélectionnera le prochain ensemble de paramètres à évaluer en fonction des performances estimées des modèles.

Il est important de noter que j'ai utilisé deux approches différentes pour évaluer la consommation d'énergie : des calculs distincts de consommation d'énergie pour les systèmes de chauffage et de climatisation, et la consommation d'énergie totale qui additionne les charges de chauffage et de refroidissement sur une période donnée, comme un jour, une semaine ou une année. Cette dernière approche fournit une vue d'ensemble de la consommation d'énergie et peut permettre d'identifier des possibilités de réduction de la consommation, par exemple grâce à une meilleure isolation, un éclairage efficace ou l'utilisation de sources d'énergie renouvelable pour l'ensemble de l'installation.

Le jeu de données contient huit attributs (ou caractéristiques, notés X1...X8) et deux réponses (ou résultats, notés y1 et y2). Vous trouverez ci-dessous les hypothèses sous-jacentes utilisées dans les simulations pour générer le jeu de données :

12 formes de bâtiment ont été générées à l'aide d'Ecotect
Tous les bâtiments ont le même volume de 771,75 m3
Tous les éléments ont utilisé le même matériau qui n'était pas isolé
Caractéristiques du bâtiment (les valeurs U associées apparaissent entre parenthèses) : murs (1,780), sols (0,860), toits (0,500), fenêtres (2,260).
Les emplacements des bâtiments sont à Athènes, en Grèce, à usage résidentiel avec sept personnes et une activité sédentaire (70 W).
Les conditions de conception intérieure ont été définies comme suit : vêtements : 0,6 clo, humidité : 60%, vitesse de l'air : 0,30 m/s, niveau d'éclairage : 300 Lux.
Les gains internes ont été fixés à 5 W/m2 pour le sensible et 2 W/m2 pour le latent, tandis que le taux d'infiltration a été fixé à 0,5 pour le taux de renouvellement d'air avec une sensibilité au vent de 0,25 renouvellement d'air par heure.
Système de thermopompe mixte à 95% d'efficacité, plage du thermostat de 19 à 24 °C, avec 15 à 20 heures de fonctionnement les jours de semaine et 10 à 20 heures les week-ends.
Trois types de surfaces vitrées, exprimées en pourcentages de la surface au sol : 10%, 25% et 40%.
Cinq scénarios de distribution différents ont été simulés pour chaque surface vitrée : (1) uniforme : avec 25% de vitrage sur chaque côté, (2) nord : 55% sur le côté nord et 15% sur chacun des autres côtés, (3) est : 55% sur le côté est et 15% sur chacun des autres côtés, (4) sud : 55% sur le côté sud et 15% sur chacun des autres côtés, (5) ouest : 55% sur le côté ouest et 15% sur chacun des autres côtés.

**<ins>Notebook 1 & 1B</ins>**

1. Préparation du problème

a) Importer les bibliothèques nécessaires
b) Charger le jeu de données

2. Analyse exploratoire des données

a) Statistiques descriptives
b) Visualisations des données

3. Préparation des données

a) Nettoyage des données
b) Séparation des données en ensembles d'entraînement et de validation
c) Transformations des données ou ingénierie des caractéristiques (analyse de sensibilité Sobol)

4. Évaluation des algorithmes

a) Sélection ponctuelle d'algorithmes (technique de validation croisée)
   
   - Notebook 1: machine learning (Linear Regression, Random Forest, and XGBoost) and neural network (Keras Sequential) models
   
   - Notebook 1B: machine learning (Linear Regression, Random Forest, KNN, and Support Vector Machine) and neural network (Keras Sequential) models

b) Comparaison des algorithmes :

5. Finalisation du modèle

a) Prédictions sur l'ensemble de validation

b) Sauvegarde du modèle pour une utilisation ultérieure

6. Conclusions


