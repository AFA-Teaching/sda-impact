---
title: "Pratique : Construire la présentation"
description: "Exercice pratique : organiser les éléments en vrac du projet AudioFuture en un plan de présentation structuré."
---

# 📄 Pratique : Construire la présentation

## Objectif

Appliquer les principes de la fiche [Construire la présentation](construire-presentation.md) en organisant les éléments en vrac ci-dessous en un plan de présentation structuré pour le projet AudioFuture.

**Les éléments en vrac**

Voici toutes les idées et éléments que nous avons notés sur le tableau blanc après avoir fini le projet "AudioFuture". C'est le chaos.

Liste des éléments en vrac :

- Graphique technique : La courbe ROC et la matrice de confusion (l'accuracy est bonne).

- Observation exploratoire (EDA) : En faisant un groupby par date, on a remarqué une chute bizarre de la moyenne des notes sur les 3 derniers mois (passage de 4.5 à 3.2).

- Détail du code : On a utilisé la librairie NLTK et on a passé beaucoup de temps à nettoyer les émojis qui faisaient planter le script.

- La bonne nouvelle : Les mots "Bass" et "Qualité Sonore" sont les plus fréquents dans le cluster des avis positifs.

- L'insight majeur : Le mot "Batterie" a un coefficient très négatif dans notre régression logistique. C'est le prédicteur n°1 d'une mauvaise note.

- Source des données : Le fichier reviews.csv fourni dans l'énoncé (2000 lignes).

- Piste d'amélioration : Pour aller plus loin, on pourrait essayer un modèle BERT (Deep Learning) si on avait un GPU.

- Comparaison : On a testé Random Forest et Régression Logistique. La régression était meilleure.

- Exemple concret : La ligne 452 du CSV : "J'adore le son mais la batterie a lâché en 1 semaine" (résume bien la situation).
