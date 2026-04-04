---
title: "Exemple : Plan de recherche"
description: "Plan de recherche utilisateur fictif pour valider une hypothèse de personnalisation via la méthode Wizard of Oz."
---

# 🗺️ Projet Reco Homepage : Plan de recherche utilisateur

**Contexte**

- Projet : Refonte de l'expérience de recommandation (Homepage).  
- Date : Semaine 1 du projet.  
- Responsables : Product manager et Data scientist.

## Le contexte et le problème

Les données quantitatives (analytics) montrent un problème clair :

- Les utilisateurs passent du temps sur la Home Page (Scroll infini).  
- Mais le CTR (Taux de Clic) sur les suggestions est faible (< 5%).  
- L'algorithme actuel "Trending" (Top des ventes) semble manquer de pertinence pour les utilisateurs réguliers.

**Notre hypothèse :** Les utilisateurs ignorent ces suggestions car elles sont trop génériques et ne reflètent pas leurs intérêts immédiats.

## Objectifs de la recherche (ce qu'on veut apprendre)  
Nous ne cherchons pas (encore) à valider une solution technique. Nous voulons comprendre la psychologie de la "Découverte".

1. Comprendre les modes de chine : Comment un utilisateur décide-t-il de se balader sans but précis ? Qu'est-ce qui déclenche ce comportement ?  
2. Identifier les irritants actuels : Pourquoi certains utilisateurs disent-ils "L'algo est nul" ? (Est-ce un problème de prix ? De localisation ? De catégorie ?).  
3. Tester l'appétence à la personnalisation : Est-ce que les utilisateurs veulent qu'on utilise leur historique, ou trouvent-ils cela intrusif (Privacy) ?

## La méthodologie  
Nous allons combiner deux approches qualitatives lors de la même session :

- Partie A, Entretien exploratoire (15 min) : Discussion ouverte sur les habitudes de navigation passées.  
- Partie B, Test Concept Wizard of Oz (15 min) : Mise en situation face à une interface simulée où les résultats sont manipulés manuellement pour être parfaits.

**Pourquoi cette méthode ?**  
Le Wizard of Oz nous permet de valider la valeur d'un algorithme parfait avant d'investir du temps de développement Data Science.

## Recrutement (Qui interroger ?)  
Nous visons 6 participants pour couvrir les spectres comportementaux principaux.

**Critères d'inclusion :**

- Avoir ouvert l'application Leboncoin au moins 2 fois la semaine dernière.  
- Avoir effectué au moins un achat ou un contact dans les 6 derniers mois.

**Segments cibles :**

| Segment | Profil recherché | Pourquoi ? |
| :---- | :---- | :---- |
| Le power user (2 pers) | Connecté tous les jours. Chineur expert. | Il est très exigeant sur la pertinence. C'est notre critique le plus dur. |
| L'occasionnel (2 pers) | Vient pour un besoin précis (Déménagement, Naissance). | Il a besoin d'efficacité. On veut voir si la reco l'aide ou le gêne. |
| Le sceptique (2 pers) | Refuse souvent les cookies. Méfiant envers la data. | On veut tester la limite de l'intrusion (Privacy). |

## Planning et logistique

- Lundi - Mardi : Recrutement (envoi d'emails sur la base opt-in).  
- Mercredi - Jeudi : Passation des 6 entretiens (30 min chacun) en visio.  
- Vendredi : Synthèse et mise à jour des JTBD.

**Matériel nécessaire :**

- Prototype Figma "Homepage V2" (Statique).  
- Script d'entretien (voir document suivant).  
- Grille de prise de notes.

## Livrables attendus (output)  
À la fin de cette semaine de recherche, nous devons produire :

1. La carte des intérêts : Liste des critères qui comptent vraiment pour un utilisateur (ex: "La distance est plus importante que le prix pour les meubles"). → Input vital pour le feature engineering.  
2. La matrice de confiance : Qu'est-ce qui fait qu'une recommandation est perçue comme "utile" vs "effrayante".  
3. Go / No-Go : Confirmation (ou non) que la personnalisation est le bon levier pour augmenter le CTR.

**Note :**  
En data science, on a tendance à dire "Donnez-moi les données, je trouverai les patterns".  
Ce plan de recherche prouve l'inverse : on va d'abord chercher les patterns humains (quali) pour savoir quelles données extraire ensuite (quanti).
