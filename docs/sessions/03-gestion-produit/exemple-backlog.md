---
title: "Exemple : Backlog"
description: "Exploration guidée d'un backlog Trello : structure du board, anatomie d'un ticket et glossaire pour data scientists."
---

# 📝 Backlog Squad Homepage

OBJECTIF : Ce document vous accompagne dans l'exploration du tableau [Trello de l'équipe Homepage](https://trello.com/invite/b/69555f5b6de2878638d926fc/ATTIdf5520730c9a690fc9f12a6ba1e43a62BED0C9A6/backlog-squad-homepage).

Comme expliqué dans [la fiche Artefacts](artefacts.md), la roadmap donne la direction (Q2 : personnalisation), ce backlog est la liste plate pour l'exécuter.

## Comprendre la structure du board (les colonnes)

En parcourant le tableau de gauche à droite, vous remontez le temps du projet : du futur lointain (idées) au passé validé (prod).

Product backlog

- C'est quoi ? La liste unique de tout ce qui pourrait être fait.  
- Observation à faire : Remarquez le cône d'incertitude.  
  - Haut de pile : Tickets prêts (ex: "audit data").  
  - Bas de pile : Idées vagues (ex: "Ajouter la météo").  
  - Note data : Regardez le ticket "Migration Airflow", c'est de la dette technique, pas une feature.

Sprint backlog

- C'est quoi ? Le sous-ensemble sélectionné pour le sprint en cours. Une fois lancé, c'est une zone protégée.  
- Observation à faire : Ici, tout est précis. Le ticket "Algo Collaborative Filtering" est passé du stade d'idée à une tâche chiffrée.

QA / Staging

- C'est quoi ? L'étape tampon avant la mise en ligne. Un ticket n'arrive ici que s'il respecte les specs.

## Anatomie d'un ticket

Ouvrez le ticket "Implémentation Algo" et observez ces 4 éléments clés :

Le format user story  
En tant que \[User\], je veux \[Action\], afin de \[Bénéfice\].

- Pourquoi ? Pour éviter d'écrire des tâches techniques.  
- Le piège à éviter :  
  * 🔴 Mauvais : "Créer un modèle XGBoost sur les logs." (L'utilisateur se fiche de votre modèle).  
  * 🟢 Bon : "En tant qu'acheteur, je veux voir des annonces similaires..." (On parle de bénéfice).

Les critères d'acceptation  
Regardez la section critères d'acceptation (Souvent en format Given / When / Then).

- Définition : C'est la liste précise des conditions pour dire "ça marche".  
- Exemples observés :  
  * "Latence < 200ms" : Performance technique non-négociable.  
  * "Cold start" : Gestion du cas "nouvel utilisateur" (souvent oublié).

## La Definition of Done (DoD)  
C'est la checklist finale en bas du ticket.

- Définition : Ce sont les standards non-négociables de l'équipe.

## Les points d'effort (story points)  
Regardez le petit badge chiffré sur les cartes (1, 2, 3, 5, 8...).

- Définition : Une estimation de la complexité relative (Suite de Fibonacci), pas une durée en jours.

## Les indices de collaboration  
En regardant l'ensemble du board, essayez de repérer les dépendances entre les métiers.

1. Data et front :  
   Regardez le ticket intégration carousel. Le développeur Front ne peut pas avancer tant que l'API du data scientist n'est pas prête.  
2. Data et business :  
   Le ticket dashboard de suivi montre que le travail ne s'arrête pas au model.predict(). Il faut prouver la valeur (KPI).

## Glossaire de survie pour le data scientist

| Terme | Signification Simple |
| :---- | :---- |
| US (User Story) | Description d'une fonctionnalité orientée valeur utilisateur (pas tâche technique). |
| AC (Acceptance Criteria) | Les conditions fonctionnelles spécifiques (le contrat). |
| DoD (Definition of Done) | Les critères de qualité transverses (Tests, Doc, RGPD...). |
| Technical Debt | Travail de fond (ex: migration infra) nécessaire pour maintenir la vélocité future. |
