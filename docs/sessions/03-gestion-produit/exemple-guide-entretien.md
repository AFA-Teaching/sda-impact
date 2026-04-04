---
title: "Exemple : Guide d'entretien"
description: "Guide d'entretien utilisateur complet pour tester un prototype de recommandation personnalisée."
---

# Projet Reco Homepage : Guide d'entretien utilisateur

**Contexte**  
Vous allez interviewer un utilisateur réel (ou un collègue jouant le rôle).  
Durée : 30 minutes.

**Objectifs**

1. Comprendre comment il cherche des objets aujourd'hui (discovery).  
2. Tester si notre nouvelle homepage personnalisée l'intéresse vraiment (test prototype).

**👋 Phase 0 : Introduction (3 min)**  
Mettre l'utilisateur à l'aise. Il n'y a pas de mauvaises réponses.

- "Bonjour et merci de ton temps. Je travaille sur l'amélioration de l'application Leboncoin."  
- "Je ne suis pas là pour vendre quoi que ce soit, je veux juste comprendre comment tu utilises l'appli."  
- "Sois honnête, même si c'est critique. C'est ce qui nous aide le plus."  
- "Est-ce que je peux enregistrer la conversation pour ne pas perdre de détails ?"

**🕵️ Phase 1 : Discovery et usages actuels (10 min)**  
Objectif : Comprendre le "Job to be Done" et les douleurs actuelles sans parler de notre solution.

L'échauffement

- "Pour commencer, à quelle fréquence ouvres-tu Leboncoin en ce moment ?"  
- "Sur quel appareil ? (Mobile vs Desktop)"

Le récit de la dernière session  
Ne demandez pas "Qu'est-ce que tu aimes ?", demandez des faits passés.

- "Raconte-moi la dernière fois que tu as ouvert l'application. C'était quand ?"  
- "Qu'est-ce que tu cherchais précisément ?"  
  - Relance : "As-tu utilisé la barre de recherche ou as-tu juste scrollé ?"  
- "Est-ce que tu as trouvé ? Si non, pourquoi as-tu quitté l'appli ?"

La douleur de la Homepage

- "Quand tu ouvres l'application, avant même de taper une recherche, que penses-tu des annonces qui s'affichent ?"  
- "T'arrive-t-il de cliquer dessus ? Si non, pourquoi ?"  
  - Indice Data Scientist : On cherche à savoir si c'est un problème de pertinence (ce n'est pas pour moi) ou de confiance (ça a l'air d'une arnaque).

**📱 Phase 2 : Test du prototype (15 min)**  
Objectif : Valider l'algorithme Wizard of Oz.

**Mise en scène :** "J'aimerais maintenant te montrer une version expérimentale de la page d'accueil. Imagine que nous sommes la semaine prochaine. Tu as cherché des articles de Décoration Vintage et des Vélos ces derniers jours."

(Montrez le Prototype Figma ou Papier où vous avez manuellement sélectionné des annonces pertinentes).

Observation silencieuse (The 5-second test)  
Laissez l'utilisateur regarder l'écran sans rien dire.

- "Dis-moi ce qui te traverse l'esprit en voyant cet écran. Qu'est-ce qui change par rapport d'habitude ?"

Tâches guidées

- Scénario A (la pertinence) : "Fais défiler les annonces. Est-ce que l'une d'elles te donne envie de cliquer ? Laquelle et pourquoi ?"  
  - Question clé : "Si cette annonce apparaissait, est-ce que tu aurais l'impression que l'appli t'espionne ou qu'elle t'aide ?" (Check Privacy).  
- Scénario B (L'exclusion - Test du "nettoyeur") : (Le prototype ne montre PAS de voitures, alors que l'utilisateur en a acheté une hier).  
  - "Remarques-tu quelque chose qui manque par rapport à ton historique d'achat récent ?"  
  - "Est-ce que c'est une bonne ou une mauvaise chose pour toi ?"

Évaluation de la valeur

- "Sur une échelle de 1 à 10, à quel point cette page d'accueil t'aiderait à trouver ton bonheur plus vite ?"  
- "Qu'est-ce qui te ferait mettre +1 point ?"

**🏁 Phase 3 : Conclusion (2 min)**

- La question "Baguette Magique" :  
  - "Si tu avais une baguette magique pour changer un seul truc sur la façon dont Leboncoin te propose des objets, tu ferais quoi ?"  
- "Merci beaucoup, c'est très précieux pour nous."

**Interprétations**  
Voici comment interpréter les réponses pour votre futur modèle :

| Ce que l'utilisateur dit | Traduction pour votre algorithme (feature engineering) |
| :---- | :---- |
| "C'est flippant, j'ai juste parlé de vélo à ma femme et ça s'affiche !" | ⚠️ Risque privacy. Peut-être réduire la précision ou ajouter un label "Vu que vous avez cherché X...". |
| "C'est sympa mais ce sont des vélos à Paris, moi je suis à Lyon." | 🚨 Feature critique : La géolocalisation doit être un filtre strict (Hard Filter), pas juste un boost. |
| "Je ne clique jamais sur les annonces sans prix." | 📉 Data Cleaning : Exclure du dataset d'entraînement les items avec price = Null ou price = 0. |
| "J'aimerais voir plus de trucs bizarres, pas juste ce que je cherche." | 🎲 Exploration : Augmenter le paramètre de "Serendipity" (Injecter 10% d'aléatoire). |
