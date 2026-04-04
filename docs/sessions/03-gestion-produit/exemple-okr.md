---
title: "Exemple : OKR"
description: "Document fictif illustrant une roadmap OKR trimestrielle et la sélection d'initiatives pour une squad data."
---

# 📋 Roadmap & OKR Q3 - Squad Homepage & Reco

*⚠️ DOCUMENT FICTIF : Ce document simule une page de définition d'objectifs trimestriels (OKR) chez leboncoin. Il sert à illustrer comment la stratégie d'entreprise redescend jusqu'au choix des algorithmes.*

**Statut :** Validé ✅  
**Propriétaires :** Head of Product (Demand), Lead Data Scientist, PM Homepage.

## Niveau 1 : Objectifs entreprise

Ce que notre CEO a annoncé lors du dernier All-Hands meeting. La stratégie repose sur 3 piliers majeurs pour cette année.

🦁O1 : Devenir le réflexe quotidien des Français (Engagement)  
Nous ne voulons pas que les gens viennent juste quand ils déménagent. Nous voulons qu'ils ouvrent l'app tous les jours, comme un réseau social.

- KR 1.1 (Key Result) : Atteindre 15 Millions de DAU (Daily Active Users).  
- KR 1.2 : Augmenter le temps passé moyen par jour de +15% (de 8min à 9m12s). 👈 C'est celui-ci qui concerne notre Squad !

🛡️O2 : Faire de la transaction une expérience invisible et sûre (Revenue & Trust)  
Sécuriser l'achat pour concurrencer le e-commerce neuf et rassurer les vendeurs.

- KR 2.1 : Augmenter la part des transactions passant par le Paiement Sécurisé de 30% à 45%.  
- KR 2.2 : Réduire le nombre de signalements frauduleux de -20%. (Ceci concerne les équipes Trust & Safety)

🌍O3 : Accélérer la transition écologique (Impact)  
Prouver que la seconde main est le premier choix citoyen.

- KR 3.1 : Atteindre 5 Millions de tonnes de CO2 évitées grâce aux ventes d'occasion.  
- KR 3.2 : Maintenir un Employee Net Promoter Score (eNPS) > 40 (Bien-être interne).

## Niveau 2 : Objectifs de la squad  
Comment la Squad Homepage contribue-t-elle à ces +15% de temps passé (O1 > KR 1.2) ?

Hypothèse : Si on montre des annonces pertinentes dès l'ouverture, l'utilisateur cliquera et restera plus longtemps.

🏠 O-Squad : Une Homepage qui lit dans les pensées  
L'utilisateur ne doit pas avoir à chercher. L'application doit anticiper son besoin (Mode, Auto, Immo) dès la première seconde.

- KR-Squad 1 (Principal) : Augmenter le CTR (Taux de Clic) du bloc "Recommandé pour vous" de 5% à 8%.  
- KR-Squad 2 (Secondaire) : Réduire le taux de "Bounce" (gens qui ferment l'app < 5 sec) de 10%.

## Niveau 3 : La sélection des initiatives  
C'est ici que se joue la priorisation. Nous avons 3 idées de modèles dans les cartons. Lequel on lance ?

| ID | Idée de modèle (Initiative) | Description | Impact estimé sur le CTR (KR) | Effort Data/Eng | Décision |
| :---- | :---- | :---- | :---- | :---- | :---- |
| A | Reco par Géolocalisation | "Tu habites à Bordeaux → Je te montre des vélos à Bordeaux". | Moyen (+0.5 pt) | Faible (3 jours) | ⏸️ Backlog (Trop basique, on l'a déjà un peu). |
| B | Collaborative Filtering (Historique) | "Tu as regardé des PS4 hier → Je te montre des jeux vidéo aujourd'hui". | Élevé (+2.5 pts) | Moyen (2 sprints) | ✅ PRIORITAIRE (Meilleur ratio Impact/Effort). |
| C | Computer Vision sur les images | "Tu aimes les canapés rouges -> J'analyse les pixels pour trouver du rouge". | Incertain (+? pts) | Très Élevé (2 mois + Coût GPU) | ❌ Rejeté (Trop risqué pour ce trimestre). |

## Conclusion pour l'équipe data science  
Pour ce trimestre (Q3), notre focus unique est de livrer l'Initiative B (Collaborative Filtering).  
Pourquoi ?  
Non pas parce que c'est le modèle le plus "sexy" (le C était plus cool techniquement), mais parce que c'est le levier le plus sûr pour atteindre les 8% de CTR, qui eux-mêmes permettront d'atteindre les +15% de temps passé demandés par l'entreprise.

**Votre mission Data :** Ne codez pas le modèle parfait. Codez le modèle qui maximise le CTR le plus vite possible pour valider l'hypothèse.
