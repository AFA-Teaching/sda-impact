---
title: "Exercice : Notes brouillon"
description: "Exemple de notes de cours brutes à transformer avec un Gem de structuration de notes."
---

# 📄 Test : Notes brouillon

cours du mardi 14/11 - Intro ML & Python  
prof : M. Dupont (parle super vite auj)  
rappel semaine derniere : on a vu l'environement Anaconda et Jupyter Notebook.  
faut tjrs lancer jupyter notebook dans le terminal ou via anaconda navigator  
installation des packages : pip install pandas numpy scikit-learn (ou conda install)  
aujou'dhui : LE PROCESSUS DATA SCIENCE  
cest quoi ?

1. definiri le pb (business understanding) -> super important sinon on code pour rien  
2. Data collection (SQL, CSV, API, Web Scraping...)  
3. Data Cleaning / Preprocessing (c'est 80% du taf c relou mais obligatoire)  
4. EDA (Exploratory Data Analysis) -> comprendre les donnés  
5. Modeling (le ML)  
6. Evaluation  
7. Deploiement

DETAIL :  
numpy = pour les calculs mathematiques, vecteurs, matrices. bcp plus rapide que les listes python classiques.  
import numpy as np (convention)  
Pandas = le excel de python.  
import pandas as pd  
la structure de base cest le DataFrame (df).  
df = pd.read\_csv('data.csv')  
df.head() -> affiche les 5 premieres lignes  
df.info() -> types des colonnes (int, float, object...)  
df.describe() -> stats de base (moyenne, ecart type etc)  
ATTENTION AUX MISSING VALUES (NaN) !!!  
si y'en a faut gerer.  
soit on supprime la ligne : df.dropna() -> radical  
soit on remplace (imputation) : par la moyenne ou la mediane.  
df.fillna(df.mean())  
attention si c des categories on peut pas mettre la moyenne lol. mettre le mode (valeur la + frequente)  
types de variables :

* quantitatives (chiffres) : continues (prix, taille) ou discretes (nb enfants)  
* qualitatives (textes/catégories) : ordinales (classement genre petit moyen grand) ou nominales (couleur, ville).  
  Faut transformer les qualitatifs en chiffres pour que le modele comprenne !!  
  -> One Hot Encoding (pd.get\_dummies) ou Label Encoding.

PAUSE 10 min  
penser a demander a sarah les notes du cours de stats jai rien écouté  
REPRISE  
Machine Learning  
2 grands types a retenir par coeur pr l'exam :

1. Apprentissage SUPERVISÉ (Supervised Learning)  
   -> On a les etiquettes (labels). On connait la réponse pour les données d'entrainement.  
   ex : predire le prix d'une maison (target = prix -> variable continue -> REGRESSION)  
   ex : predire si un mail est spam ou pas (target = oui/non -> variable categorielle -> CLASSIFICATION)  
2. Apprentissage NON SUPERVISÉ (Unsupervised)  
   -> Pas d'etiquettes. On lache l'algo dans la nature et il cherche des structures.  
   ex : Clustering (regouper des clients qui se ressemblent). K-Means.

Notion de Train / Test SPLIT  
MEGA IMPORTANT  
Faut jamais tester son modele sur les données qu'il a deja vu sinon c de la triche.  
On coupe le dataset en 2 :

* Training set (genre 80%) pour entrainer le modele  
* Test set (20%) pour verifier si il marche vrmt  
  from sklearn.model\_selection import train\_test\_split  
  X\_train, X\_test, y\_train, y\_test = train\_test\_split(X, y, test\_size=0.2)

L'overfitting (surapprentissage)  
c quand le modele apprend "par coeur" le bruit des données d'entrainement.  
il est excellent sur le train set (score 99%) mais nul sur le test set (score 50%).  
c comme un etudiant qui apprend les exos par coeur mais comprend pas la logique.  
inverse = underfitting (modele trop simple, genre une ligne droite pour un truc courbe).  
Premier algo simple : REGRESSION LINEAIRE  
y = ax + b  
on cherche la droite qui passe le plus pres de tout les points.  
Methode des moindres carrés (OLS).  
On veut minimiser l'erreur (les résidus).  
MSE = Mean Squared Error (moyenne des carrés des erreurs).  
Pour evaluer une regression :  
R2 score (R squared) -> plus c proche de 1 mieux c'est.  
RMSE -> erreur moyenne dans l'unité de la target.  
prochain cours : Logistic Regression (c pour la classification malgre le nom !!) et KNN.  
projet a rendre pour le 20 decembre par groupe de 3.  
sujet libre mais faut utiliser un dataset clean.  
voir Kaggle pour trouver des datasets.
