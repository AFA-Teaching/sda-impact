---
title: "Exemple : Lean Startup"
description: "Application du cycle Build-Measure-Learn à un projet de recommandation : du MVP au pivot data-driven."
---

# Projet lean startup : Le cycle build, measure, learn

**Contexte**  
Vous sortez de la phase design thinking. L'idée "Afficher des recommandations basées sur l'historique" semble plaire sur papier.

Le piège à éviter : S'enfermer 3 mois dans un tunnel pour coder l'architecture parfaite, scalable et temps réel, pour découvrir à la fin que personne ne clique.

L'approche lean : Construire le Minimum Viable Product (MVP) pour valider l'hypothèse business le plus vite possible.

**🏁 Phase 1 : L'hypothèse (ce qu'on veut vérifier)**  
Avant d'écrire une ligne de code, nous devons formuler notre pari.

**L'hypothèse risquée (The riskiest assumption) :** "Nous pensons que personnaliser la Home Page avec un algorithme de filtrage collaboratif augmentera le nombre de clics (CTR) par rapport à l'affichage générique actuel."

**Le critère de succès (KPI) :** Pour valider l'hypothèse, le CTR (Click-Through Rate) du bloc MVP doit être supérieur de 10% au bloc actuel ("trending").

**🏗️ Phase 2 : Construire le MVP**  
Objectif : Mettre l'idée en prod avec le minimum d'effort technique.

🔴 La version parfaite (ce qu'on ne fait PAS tout de suite) :

- Architecture micro-services Kafka en temps réel.  
- Ré-entraînement du modèle toutes les 10 minutes.  
- Gestion complexe des nouveaux utilisateurs.  
- Temps estimé : 3 mois.

🟢 La version MVP (ce qu'on fait maintenant) :

- Modèle : Un script Python basique qui tourne sur votre ordi portable.  
- Fréquence : Batch manuel. On calcule les recommandations une fois par nuit (J-1).  
- Delivery : On génère un gros fichier CSV (user\_id, \[item\_id\_1, item\_id\_2...\]) qu'on pousse "sauvagement" dans la base de données de production.  
- Temps estimé : 4 jours.

**Leçon data :** Votre code est sale, pas optimisé, pas scalable. C'est normal. Si le produit ne marche pas, on n'aura perdu que 4 jours, pas 3 mois.  
**📏 Phase 3 : Mesurer l'impact**  
On lance le MVP sur 10% du trafic (A/B Test) pendant 1 semaine.

Le tableau de bord de l'expérience :

| Métrique | Groupe A (Contrôle - Trending) | Groupe B (MVP - Reco Perso) | Delta |
| :---- | :---- | :---- | :---- |
| Vues (Impressions) | 100 000 | 10 000 | - |
| Clics | 5 000 | 650 | - |
| CTR (Taux de Clic) | 5.0 % | 6.5 % | +30% 🚀 |
| Temps de chargement | 120ms | 140ms | OK (<200ms) |

**Observation surprise (insight) :** En creusant les data, vous voyez que le modèle performe très bien sur les catégories Loisirs (Jeux vidéo, Livres) mais sous-performe sur la catégorie Véhicules.

Pourquoi ? Parce que les gens achètent rarement deux voitures de suite. L'historique court terme ne prédit pas bien l'achat futur dans ce cas.

**🧠 Phase 4 : Apprendre et pivoter**  
Le cycle est bouclé. Qu'avons-nous appris et quelle est la décision ?

**Verdict :** ✅ Persévérer mais avec ajustement.

L'hypothèse globale est validée (+30% CTR). Cependant, l'insight sur les voitures nous force à adapter la stratégie avant l'industrialisation.

**Le prochain cycle (Itération 2) :** Au lieu de passer en production industrielle tout de suite, on relance une boucle Lean rapide.

- Nouvelle hypothèse : Pour la catégorie Auto, un algo basé sur la localisation marchera mieux que l'historique.  
* Nouveau build : Modifier le script pour dire "Si user a regardé Auto → Montrer Auto dans sa région (pas forcément similaire)".

**📝 Synthèse**  
Voici comment le Lean Startup change votre métier de data scientist :

- Code jetable : Vous devez accepter d'écrire du code qui sera jeté dans 2 semaines. Ce n'est pas du mauvais travail, c'est de l'intelligence économique.  
- Vanity vs actionable metrics :  
  - Vanity (Vanité) : "Mon modèle a une précision de 95%". (on s'en fiche si personne ne clique).  
  - Actionable (Actionnable) : "Le CTR a pris +1.5pt". (c'est ça qui valide le projet).  
- Le pivot : C'est le moment où la data contredit l'intuition. Votre rôle est d'être honnête avec les chiffres : si l'expérience échoue, il faut tuer le projet ou le changer, même si vous adorez votre algorithme.
