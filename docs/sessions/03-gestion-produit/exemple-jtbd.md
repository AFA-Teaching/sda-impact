---
title: "Exemple : JTBD"
description: "Jobs to be Done appliqué à la recommandation : identifier les intentions utilisateur plutôt que les profils démographiques."
---

# 🧩 Jobs to be Done (JTBD) : au-delà du profil utilisateur

**Le concept clé :**  
Vos utilisateurs n'achètent pas votre produit pour ce qu'ils sont (ex: "Homme, 35 ans, Paris"), mais pour la tâche qu'ils essaient d'accomplir (ex: "Me débarrasser d'un vieux canapé avant mon déménagement").

**La phrase magique :** "On embauche (hire) un produit pour faire un job."

## Le duel : Persona vs JTBD  
Imaginez deux utilisateurs sur Leboncoin.

- Profil A : Homme, 73 ans, riche, vit dans un château, aime les chiens.  
- Profil B : Homme, 73 ans, riche, vit dans un château, aime les chiens.

Un système se dit : "Ils sont pareils, je leur recommande la même chose !"

Sauf que...

- Le profil A (Prince Charles) cherche une voiture de collection pour son musée.  
- Le profil B (Ozzy Osbourne) cherche une voiture pour la détruire dans un clip.

**Leçon data :** La démographie ne prédit pas l'intention. Le contexte (le "job") le fait.

## Les 3 "jobs" principaux sur la Homepage Leboncoin  
En analysant les comportements (et pas les profils), nous avons identifié 3 "jobs" distincts. Votre algorithme de recommandation doit être capable de détecter quel job l'utilisateur est en train de faire pour adapter l'affichage.

Job 1 : Le chasseur précis

- Le besoin : "Je sais exactement ce que je veux. Je veux le trouver au meilleur prix et l'acheter avant quelqu'un d'autre."  
- Signaux data (features) :  
  - Utilise beaucoup la barre de recherche.  
  - Utilise les filtres de prix/localisation.  
  - Taux de retour élevé sur la même requête.  
- Réponse de l'algorithme :  
  * Ne PAS faire de "découverte".  
  * Afficher les nouvelles annonces correspondant aux critères précis.  
  * Alerter sur les baisses de prix.

Job 2 : Le flâneur

- Le besoin : "Je m'ennuie dans le métro. Montre-moi des trucs sympas ou bizarres pour passer le temps. Je n'ai pas d'intention d'achat immédiate."  
- Signaux data (features) :  
  - Scrolle beaucoup sans cliquer.  
  - Regarde des catégories très variées (Montres, puis Déco, puis Immobilier de luxe).  
  - Sessions longues, click-to-buy très faible.  
- Réponse de l'algorithme :  
  - Optimiser pour le clic et l'engagement, pas la conversion.  
  - Favoriser la diversité et les images de haute qualité.  
  - Injecter de la "serendipity" (découverte fortuite).

Job 3 : Le gestionnaire de projet

- Le besoin : "Je déménage / J'attends un bébé. J'ai besoin d'équiper toute une pièce avec un budget serré."  
- Signaux data (features) :  
  - Regarde plusieurs sous-catégories liées (Lit bébé + Poussette + Table à langer).  
  - Filtre géographique très restreint (veut tout chercher au même endroit).  
- Réponse de l'algorithme :  
  - Recommandation de complémentarité (cross-sell).  
  - "Tu as pris le lit ? Voici le matelas qui va avec."

## Atelier : Traduire le job en feature data  
En tant que data scientist, votre rôle est de traduire ces concepts psychologiques en règles techniques.

| Le job détecté | L'erreur classique (persona) | La solution JTBD (data) |
| :---- | :---- | :---- |
| "Je vide mon grenier" (vendeur) | Lui recommander d'acheter d'autres objets similaires (car il aime cette catégorie). | Lui recommander des cartons de déménagement ou une location de camionnette. |
| "Je cherche une voiture" | Lui montrer des voitures après qu'il en ait acheté une. | Détecter l'arrêt soudain de la recherche "Voiture" → Basculer sur "Assurance Auto" ou "Pièces détachées". |
| "Cadeau de dernière minute" | Lui recommander des objets à l'autre bout de la France (car moins chers). | Prioriser absolument la géolocalisation (< 5km) et la réponse rapide du vendeur. |

## Synthèse

1. L'intention bat l'identité : Ne perdez pas de temps à prédire l'âge ou le genre de l'utilisateur. Essayez de prédire son job actuel à partir de ses 5 derniers clics (session-based reco).  
2. Un utilisateur change de job : Le matin, je peux être un "chasseur" (je cherche une pièce auto urgemment), et le soir un "flâneur" (je regarde des villas de luxe). Votre modèle doit être temps-réel pour s'adapter.  
3. L'impact métrique :  
   * Job "chasseur" → On optimise le taux de conversion.  
   * Job "flâneur" → On optimise le temps passé.
