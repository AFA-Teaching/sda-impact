---
title: "Scénario de produit"
description: "Mise en situation : intégrer l'équipe Data de Leboncoin et comprendre ce qu'est un produit data."
---

# Scénario de produit

Imaginez que vous venez de signer votre contrat. Vous rejoignez l'équipe Data de [Leboncoin](https://www.leboncoin.fr/).

Pourquoi cet exemple ? Parce que tout le monde connaît l'interface, mais peu de gens voient la machinerie derrière.

**Une réalité invisible : Le produit vivant**  
Même si le site peut sembler "figé" (on a toujours la barre de recherche, les photos, le prix), c'est une illusion.

- Le produit évolue constamment.  
- Des dizaines d'équipes travaillent en parallèle.  
- Des déploiements ont lieu quasi-quotidiennement pour des correctifs, et mensuellement pour des fonctionnalités majeures.  
- Votre application mobile se met à jour silencieusement pour intégrer ces changements.

**Définitions clés**  
Avant de coder, mettons-nous d'accord sur les termes.

Qu'est-ce qu'un produit ?  
Ce n'est pas juste du code ou un logiciel. Un produit est un véhicule qui délivre de la valeur à un utilisateur pour résoudre un problème, de manière viable pour l'entreprise.

Exemple : La fonctionnalité "Déposer une annonce" résout le problème de vouloir vendre un objet.

Qu'est-ce qu'un produit data ?  
C'est un produit dont la valeur principale repose sur l'utilisation de données pour faciliter un objectif final. Contrairement au développement logiciel classique (qui est déterministe : "si je clique ici, ça ouvre ça"), le produit data est souvent probabiliste.

Il peut prendre 3 formes :

- Aide à la décision : Un dashboard pour le marketing.  
- Décision automatisée : Un algorithme de détection de fraude qui bloque une transaction.  
- Fonctionnalité intelligente : Un système de recommandation (ce qui nous intéresse aujourd'hui).

**Note importante :** En data science, on gère de l'incertitude. On ne code pas une règle stricte, on entraîne un système à deviner. C'est ce qui change tout dans la gestion de projet.

**Votre mission**  
Vous intégrez l'équipe recommandation.  
Votre champ d'action : La page d'accueil de l'application et du site web.

Le constat :  
Actuellement, les utilisateurs passent du temps à scroller mais ne cliquent pas assez souvent sur les annonces suggérées. L'expérience est jugée générique.

Le défi :  
Le product manager et le business souhaitent augmenter l'engagement (temps passé et nombre de contacts générés) sur la page d'accueil via une personnalisation plus fine.

Votre rôle de data scientist :  
Vous ne devez pas seulement coder un meilleur algorithme.

Vous devez :

1. Comprendre quel problème utilisateur on résout (discovery).  
2. Définir comment mesurer le succès (business vs proxy metrics).  
3. Concevoir une stratégie incrémentale (baseline > algo simple > deep Learning).  
4. Mettre en production une solution fiable.

*⚠️ Disclaimer : Ce cas d'usage est purement fictif. Les données, contextes et problématiques cités sont inventés pour les besoins pédagogiques de cette formation et ne reflètent pas nécessairement la réalité interne ou la stratégie actuelle de l'entreprise Leboncoin.*
