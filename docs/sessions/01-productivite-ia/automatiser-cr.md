---
title: "Automatiser les CR"
description: "Transformer les transcriptions de réunions en comptes-rendus structurés avec plan d'action grâce à Gemini."
---

# 📋 Automatiser les comptes-rendus

**Objectif :** Ne plus jamais perdre 30 minutes à rédiger un mail récapitulatif après une réunion. Transformer un flux de parole désordonné en un plan d'action structuré, sans rien oublier (même ce que vous n'avez pas écouté).

**Le scénario**  
Vous sortez d'une réunion de sprint planning ou d'un point client d'une heure. Beaucoup de choses ont été dites, des décisions techniques ont été prises à la volée, et des tâches ont été assignées. Vous devez envoyer le CR. Au lieu de vous fier à votre mémoire (faillible) ou à vos notes griffonnées, nous allons utiliser la transcription brute.

**La méthode**

1\. La capture (la donnée brute)  
La matière première, c'est le texte.

- L'action : Sur Google Meet (ou Teams/Zoom), activez l'enregistrement de la transcription (Transcript).

- Le résultat : À la fin de la réunion, vous recevez un fichier texte ou un Google Doc. C'est illisible pour un humain (c'est plein de "euh...", de répétitions, de timestamps), mais c'est de l'or pour Gemini.

2\. L'extraction intelligente

- L'action : Copiez tout le texte brut (oui, tout). Collez-le dans Gemini.

- Le prompt : "Voici la transcription brute d'une réunion technique. Rédige un compte-rendu professionnel. Je veux : les décisions validées, les points de blocage évoqués, et surtout la liste des actions à faire (qui fait quoi pour quand)."

- L'effet super-ouïe : Vous serez surpris. Gemini va relever des détails que vous aviez zappés (ex: "Marc a mentionné au début qu'il fallait mettre à jour la librairie boto3"). Si vous avez un doute, demandez-lui : "À quel moment Marc a parlé de ça ?" et il vous donnera la preuve.

3\. Industrialiser avec un Gem  
Comme pour le reste, la structure compte. Créez un Gem pour avoir toujours le même format de mail.

- Nom du Gem : "Meeting Minutes Master"

- Instructions : Demandez à Gemini de vous les rédiger.

4\. La validation (trust but verify)  
C'est l'étape critique mentionnée dans notre méthodologie.

- Le risque : L'hallucination (rare sur du résumé, mais possible sur l'attribution des tâches).

- L'action : Relisez toujours le tableau des actions. Vérifiez que Gemini n'a pas attribué une tâche à la mauvaise personne parce que deux personnes parlaient en même temps. Votre valeur ajoutée n'est plus la rédaction, mais la validation.

**Ce qu'il faut retenir**

- Transcript > Notes manuelles : La transcription capture 100% du signal. Vos notes n'en capturent que 30%. Laissez Gemini faire le tri.

- Standardisation : Utilisez un Gem pour que vos collègues reçoivent toujours le même format de CR, clair et lisible.

- Vérification humaine : L'IA est votre scribe, vous êtes le responsable. Ne cliquez jamais sur "Envoyer" sans avoir relu les actions attribuées.

**Pour aller plus loin**  
[How to Use Gemini to take notes | Beginner to Advanced](https://youtu.be/ZRgTrvwAoJs?si=0nTKWMjnEEyTDRT0)
