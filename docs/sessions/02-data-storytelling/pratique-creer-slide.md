---
title: "Pratique : Créer une slide"
description: "Exercice pratique avec les données brutes du projet AudioFuture pour créer des slides percutantes."
---

# 📄 Pratique : Créer une slide

1\. Performance du modèle (régression logistique v2)

- On a testé plusieurs modèles (SVM, naive bayes), c'est la régression logistique qui performe le mieux.  
- Global accuracy : 88% (le modèle prédit correctement le sentiment 88 fois sur 100).  
- Precision : 0.85 / Recall : 0.91 sur la classe "négatif".  
- Note technique : On a eu du mal avec l'ironie, mais le nettoyage des stop-words a bien marché.

2\. Analyse des coefficients (mots clés importants)  
Les mots qui pèsent le plus lourd dans la décision du modèle :

- TOP POSITIF (Ce qui va bien) :  
  - "Son" (Coeff: 2.4)  
  - "Bass" (Coeff: 1.8)  
  - "Design" (Coeff: 1.5)  
  - Observation : Les clients sont très contents de la qualité audio, c'est le point fort.  
- TOP NÉGATIF (Ce qui ne va pas) :  
  - "Batterie" (Coeff: -3.2) → C'est le mot le plus discriminant !  
  - "Charge" (Coeff: -2.8)  
  - "Éteint" (Coeff: -2.1)  
  - "Boîtier" (Coeff: -1.5)

3\. Verbatims (exemples de commentaires clients)

- Client A (5 étoiles) : "Le son est incroyable pour le prix, les basses sont profondes."  
- Client B (1 étoile) : "Inutilisable. La batterie se vide en 20 minutes après 1 mois d'utilisation. Je demande un remboursement."  
- Client C (2 étoiles) : "Bon son, mais le boîtier ne charge plus les écouteurs. C'est dommage."

4\. Conclusion rapide  
Le modèle est fiable (88%). On voit clairement que le produit est bon sur l'audio (son/bass), mais il y a un problème critique matériel sur l'alimentation (batterie/charge). Il faut voir avec l'équipe ingénieur.
