---
title: "Exemple : Design Thinking"
description: "Atelier design thinking appliqué : de l'empathie utilisateur au prototype magicien d'Oz pour un projet de recommandation."
---

# 💎 Atelier design thinking : Projet smart home

**Contexte**  
Problème : Notre Homepage est un fourre-tout. Les utilisateurs scrollent beaucoup mais cliquent peu (CTR faible). L'expérience est jugée trop générique.

Objectif : Réinventer l'expérience de découverte pour augmenter l'engagement.

Participants : Product Manager, UX Designer, Data Scientist (Vous), User Researcher.

## Étape 1 : Empathie (comprendre l'utilisateur)  
Sortir des logs serveurs pour comprendre l'humain derrière le clic.

**Ce que nous avons fait :** Au lieu de regarder seulement vos tableaux de données (events\_view), nous avons écouté 5 utilisateurs qui commentaient leur navigation en direct.

**Verbatims clés (la réalité du terrain) :**  
"C'est bizarre, j'ai acheté une poussette hier, et l'appli continue de me proposer des poussettes sur la page d'accueil. C'est inutile." - Julie, 34 ans.  
"Je ne sais pas quoi chercher. J'aime bien chiner, mais là, on me montre des pneus neige alors que je regarde de la déco." - Thomas, 28 ans.

**Votre constat data scientist :** En croisant ces dires avec la data, vous réalisez que notre algo actuel ("trending") favorise les articles très cliqués (comme les pneus en hiver), écrasant les goûts de niche des utilisateurs.

## Étape 2 : Définition (le vrai problème)  
Transformer les plaintes en une opportunité claire.  
Nous avons utilisé la méthode "How Might We" (Comment pourrions-nous...) pour cadrer le défi Data.

**Le problème initial (vague) :** "Il faut augmenter le taux de clic sur la home."

**Le problème recadré (actionnable pour la data) :** "Comment pourrions-nous utiliser l'historique récent de l'utilisateur pour lui proposer une sélection qui anticipe son besoin immédiat, tout en excluant ce qu'il a déjà acheté ?"

## Étape 3 : Idéation (brainstorming)  
Aucune idée n'est mauvaise. Tout le monde propose, y compris la Tech.

Voici les 3 idées finalistes sorties du brainstorming :

| Idée | Concept | Complexité Data | Impact Utilisateur |
| :---- | :---- | :---- | :---- |
| A. Le nettoyeur | Exclure automatiquement les catégories des objets achetés récemment. | 🟢 Faible (Règles SQL) | ⭐️ Moyen (Moins de frustration) |
| B. Le chineur Visuel | "Tu as liké cette lampe vintage ? Voici un tapis qui va avec." (Computer Vision / Embeddings). | 🔴 Élevée (Deep Learning) | ⭐️⭐️⭐️ Fort (Effet "Whaou") |
| C. Le météorologue | S'il pleut chez l'utilisateur, pousser des imperméables et jeux de société. | 🟡 Moyenne (API Météo) | ⭐️ Faible (Contextuel seulement) |

**Choix de l'équipe :** On part sur une combinaison A + B simplifiée. On veut de la pertinence visuelle (Idée B) mais en filtrant les achats (Idée A).

## Étape 4 : Prototypage (sans code !)  
Tester l'idée sans passer 3 mois à entraîner un modèle.

**Le rôle du data scientist ici :** Vous n'allez pas coder le modèle. Vous allez faire du magicien d'Oz.

**Le prototype :** Le Designer crée une fausse page d'accueil pour 10 utilisateurs testeurs.  
Au lieu d'un algo, c'est VOUS, le data scientist, qui sélectionnez manuellement 5 annonces pour chaque utilisateur testeur en regardant leur historique manuellement.

- User Testeur 1 : A regardé des vélos vintage.  
- Votre sélection manuelle : 2 selles en cuir Brooks, 1 guidon rétro, 1 vélo complet similaire.

**Pourquoi faire ça ?** Si l'utilisateur ne clique pas sur une sélection parfaite faite par un humain, ce n'est pas la peine de coder une IA complexe. Le problème est ailleurs (UX, prix, confiance).

## Étape 5 : Test et apprentissage  
Résultats du test magicien d'Oz.

**Feedback utilisateurs :**

- "Ah super, enfin des trucs qui me ressemblent !" → Hypothèse de pertinence validée.  
- "Par contre, pourquoi le guidon est en premier ? Je cherche d'abord le vélo." → Insight pour le ranking.

**Conclusion pour votre futur algo :** Ce test vous donne votre feuille de route technique pour le sprint 1 :

1. Inutile de faire du deep learning complexe tout de suite.  
2. Un simple algo de similarité item-item (collaborative filtering) suffira pour imiter ce que vous avez fait à la main.  
3. Règle métier critique : Ajouter un filtre post-process pour exclure les catégories achetées (feedback de l'étape 1).

**Ce qu'il faut retenir**  
En tant que data scientist, si vous aviez sauté l'étape Design Thinking, vous auriez peut-être :

- Passé 3 semaines à coder l'idée "Météo" (techniquement fun mais inutile pour l'user).  
- Oublié d'exclure les objets déjà achetés (frustration user).

Le design thinking sert à coder la bonne chose, avant de chercher à bien la coder.
