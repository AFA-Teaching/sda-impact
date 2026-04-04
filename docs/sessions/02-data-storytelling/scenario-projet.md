---
title: "Scénario de projet"
description: "Présentation du projet fil rouge AudioFuture : analyse de sentiments NLP sur des avis clients."
---

# 💼 Scénario de projet

**Objectif :** Avoir un projet de référence réaliste pour la formation. Il servira d'exemple pour construire nos slides.

**Le sujet du projet**

- Titre du projet : "Analyse de sentiments sur les avis clients (NLP)".

- Le point de départ : Un dataset public (type Kaggle ou Amazon Reviews) contenant 10 000 lignes de commentaires bruts sur des produits électroniques.

- La problématique : Comment automatiser le traitement d'une grande quantité de texte non structuré pour en extraire l'opinion des utilisateurs ?

- L'objectif académique : Mettre en œuvre un pipeline de Natural Language Processing (NLP) complet, du nettoyage à la modélisation.

**Le travail technique réalisé**

- Exploration (EDA) : Analyse de la distribution des notes (étoiles) et de la longueur des commentaires.

- Preprocessing : Nettoyage du texte (suppression de la ponctuation, minuscules, lemmatisation, retrait des stop-words).

- Modélisation : Entraînement d'un algorithme de classification (ex: régression logistique ou naive bayes) pour prédire si un avis est "positif" ou "négatif".

- Évaluation : Mesure de la performance via la matrice de confusion et l'accuracy.

**Les données à présenter (matière pour les slides)**  
Pour l'exercice, nous utiliserons ces résultats fictifs :

- Performance technique : Le modèle atteint 88% d'Accuracy (précision globale).

- Insight découvert : Le modèle a permis d'identifier que le mot "batterie" est le plus corrélé aux avis négatifs.

- Visualisations prévues :  
  - Histogramme de la distribution des notes (déséquilibre des classes).  
  - Matrice de confusion (vrai positifs / faux négatifs).  
  - Nuage de mots (wordcloud) des avis négatifs.

**L'enjeu de la présentation**  
Vous devez réussir un double exercice face au jury :

- Prouver la rigueur technique : Montrer que le dataset a été bien nettoyé et que le modèle est valide (pas d'overfitting).

- Montrer la valeur applicative : Démontrer que ce modèle "théorique" pourrait servir concrètement (ex: "Grâce à ce modèle, on peut alerter le SAV automatiquement si un avis parle de batterie").
