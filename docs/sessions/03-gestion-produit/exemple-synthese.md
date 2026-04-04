---
title: "Exemple : Synthèse"
description: "Synthèse de recherche utilisateur : insights clés, matrice JTBD et traduction technique pour le backlog data."
---

# 📄 Projet Reco Homepage : Synthèse recherche utilisateur

**Résumé**

- Verdict : 🟢 GO pour le développement.  
- L'appétence pour une homepage personnalisée est très forte (Note moyenne : 8.5/10).  
- Alerte majeure : L'algorithme ne doit pas être bête. Si l'utilisateur a déjà acheté l'objet ou s'il est vendu, l'afficher crée une frustration immédiate.  
- Pivot stratégique : La priorité n°1 n'est pas la précision pure, mais la fraîcheur et la géolocalisation.

## Panel et méthodologie

- Dates : 12 au 14 Octobre.  
- Format : 6 entretiens visio (30 min) avec test Wizard of Oz.  
- Panel : 2 power users (les chineurs), 2 occasionnels (les pragmatiques), 2 sceptiques (les anti-data).

## Top 3 insights (ce qu'on a appris)

Insight #1 : Le syndrome du "C'est déjà vendu"  
C'est le point de friction n°1. Les utilisateurs détestent qu'on leur recommande des objets qui ne sont plus disponibles ou qu'ils viennent d'acheter.

*"Ça m'énerve ! Leboncoin me montre encore des poussettes alors que j'en ai acheté une via l'appli mardi dernier. Ils devraient le savoir !" - Sarah, 32 ans.*

**Implication data :** Il nous faut impérativement une règle d'exclusion (negative filtering) basée sur les transactions récentes.

Insight #2 : La géolocalisation est une contrainte dure  
Pour les objets volumineux (Meubles, Vélos), la pertinence sémantique ne suffit pas. Si c'est loin, c'est invisible.

*"Ce canapé est magnifique, exactement mon style. Mais il est à Brest et je suis à Lyon. Donc pour moi, cette recommandation est une erreur." - Marc, 45 ans.*

**Implication data :** La distance ne doit pas être juste une feature dans le modèle de ranking. Elle doit être un filtre bloquant (Hard Filter) pour les catégories "Encombrants".

Insight #3 : Le besoin de "Pourquoi ?" (Explainability)  
Les sceptiques ont trouvé le prototype pertinent mais inquiétant. Ils ont besoin de contexte pour ne pas se sentir espionnés.

*"C'est bizarre qu'il sache que je veux une guitare... Ah, c'est parce que j'ai regardé des amplis hier ? Dites-le moi, sinon je me sens fliqué." - Julien, 24 ans.*

**Implication UX/data :** L'API doit renvoyer une raison avec la recommandation (ex: reason: "Parce que vous avez vu X").

## Matrice JTBD vs Solution  
Voici comment les jobs identifiés lors de l'atelier précédent ont été validés ou invalidés.

| Job utilisateur | Validé ? | Ce qu'ils attendent de l'algo |
| :---- | :---- | :---- |
| Le chasseur (Cherche un truc précis) | ✅ OUI | Fraîcheur immédiate. Il veut voir les annonces postées il y a < 1h sur ses critères. |
| Le flâneur (Passe le temps) | ✅ OUI | Diversité visuelle. Il ne veut pas voir 10 fois la même table basse. Il veut de la "Serendipity" (Surprise). |
| Le gestionnaire (Déménagement) | ⚠️ MITIGÉ | Il veut de la cohérence géographique ("Tout trouver dans un rayon de 5km"). |

## Traduction technique : du verbatim au backlog  
En tant que data scientist, voici comment cette recherche modifie notre roadmap technique pour le Sprint 1.

| Ce que l'utilisateur a dit (Verbatim) | Traduction data (feature engineering) | Priorité |
| :---- | :---- | :---- |
| "Je ne veux plus voir ce que j'ai acheté." | Création d'une Blacklist Category post-achat (durée : 30 jours). | 🔴 Prio 1 |
| "C'est trop loin, ça ne m'intéresse pas." | Implémenter un Radius Filter dynamique selon la catégorie (Vélo = 20km, Jeu vidéo = France entière). | 🔴 Prio 1 |
| "Montrez-moi des trucs nouveaux." | Booster le score des items dont created\_at < 24h (Decay function). | 🟠 Prio 2 |
| "Pourquoi vous me montrez ça ?" | Ajouter le champ source\_item\_id dans la réponse API pour afficher "Similaire à votre dernière visite". | 🟢 Prio 3 |

## Recommandation finale  
L'équipe Homepage recommande de lancer le développement du MVP avec les ajustements suivants :

1. **Scope :** On se limite aux catégories "Loisirs & Maison" (plus facile à recommander que l'Auto/Immo).  
2. **Technique :** On abandonne l'idée du Deep Learning complexe pour l'instant. Un simple Collaborative Filtering filtré par Géolocalisation suffira pour atteindre les objectifs de satisfaction.  
3. **KPI de succès :** On surveillera le CTR, mais aussi le Taux de "Hide" (Utilisateurs qui masquent la recommandation), signe de mauvaise pertinence.

**Prochaine étape :** Grooming du backlog avec les dévs pour intégrer les règles d'exclusion.
