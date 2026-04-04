---
title: "Maîtriser un concept"
description: "Transformer Gemini en tuteur personnel pour apprendre mieux et en profondeur grâce au prompting structuré et aux Gems."
---

# 💭 Maîtriser un concept

**Objectif :** Transformer Gemini en un tuteur personnel disponible 24/7. L'idée n'est pas d'apprendre vite, mais d'apprendre mieux et en profondeur, en sollicitant l'IA pour qu'elle s'adapte à votre besoin (théorie, visuel, code).

**Le scénario**  
En cours, on vous parle de l'algorithme KNN (K-Nearest Neighbors). Vous ne connaissez pas, ou c'est flou. Le réflexe classique est de taper "Explique-moi le KNN" sur Gemini. Nous allons voir comment aller beaucoup plus loin avec Gemini. 

**Les méthodes**

Étape A : La première approche (découverte de l'interface)  
On commence simple : tapez "Explique-moi ce qu'est le KNN" dans la barre de saisie de Gemini. C'est le moment de regarder votre tableau de bord. Avant même de valider, plusieurs choix s'offrent à vous :

- Le choix du modèle (le cerveau) : Vous avez souvent le choix.  
  - Flash : Rapide, pour des tâches simples (mails, résumés courts).  
  - Pro / Thinking : C'est le mode raisonnement. Il prend le temps de réfléchir.  
  - Mon conseil : Restez par défaut sur le modèle Pro. Généralement, on ne veut pas de la vitesse, on veut de la pertinence et de la nuance. Acceptez d'attendre quelques secondes de plus pour une réponse de meilleure qualité.

- Les pièces jointes (Le contexte) : Le bouton + permet d'ajouter vos propres données. Pour un data scientist, c'est crucial : vous pouvez uploader un PDF, un Google Doc, une vidéo .mp4, ou même lier un repo GitHub.

- Les outils :  
  - Certains sont visibles : Deep Research, vidéos, images, Canvas.  
  - D'autres sont cachés : s'activent seuls (comme la recherche Google pour vérifier des faits récents), ou doivent être explicitement demandés (comme l'exécution de code Python, on y reviendra).

Étape B : Visualiser pour comprendre (introduction à canvas)  
Pour des algorithmes comme KNN (basé sur des distances géométriques), le texte ne suffit pas. C'est ici qu'intervient Canvas. C'est une interface dédiée, séparée du chat, qui permet de générer du contenu (code ou texte) et de travailler dessus sans polluer la conversation.

- L'action :  
  - Demandez "Crée une petite application web interactive pour visualiser comment fonctionne le KNN avec des points de couleur".  
  - Activez l'outil Canvas avant de soumettre votre prompt.

- Le résultat : Gemini va ouvrir une fenêtre à droite (Canvas) et coder en direct.

- L'usage : Vous obtenez une visualisation graphique. Vous pouvez modifier le code directement ou demander des ajustements. C'est indispensable pour se créer une image mentale du concept.

Étape C : Structurer sa connaissance (l'art du prompting)  
Une définition simple ne suffit pas à un expert. Pour maîtriser un sujet, vous avez besoin de structure : Théorie, Analogie, Limites, Code. Au lieu de poser 4 questions, on va faire un prompt d'expert.

- La méthode PTCF : Un bon prompt contient 4 éléments :  
  - Persona (Qui est l'IA ?) : Tu es un tuteur pédagogue en data science.  
  - Tâche (Que doit-elle faire ?) : Explique-moi le KNN.  
  - Contexte (Qui êtes-vous ?) : Je suis étudiant débutant.  
  - Format (La structure de sortie) : Je veux une analogie, la théorie mathématique, les limites du modèle, et un exemple de code Python.

- L'astuce meta-prompting : Vous ne voulez pas écrire tout ça ? Demandez à Gemini de le faire !  
  - Prompt : "Rédige-moi les instructions pour qu'un assistant AI joue le rôle de tuteur et m'explique un concept de data science de façon complète (analogie, code, limites)."

- Le tips productivité : Utilisez le mode vocal (le micro). C'est souvent plus fluide de dicter ses pensées complexes à l'oral ("Je veux que tu m'expliques ça comme si j'avais 10 ans mais avec du code Python...") plutôt que de tout taper. L'IA comprend parfaitement le langage naturel parlé (même avec des erreurs).

Étape D : Capitaliser (création d'un Gem)  
Vous allez devoir apprendre des dizaines d'algorithmes (SVM, Random Forest, Neural Nets...). Vous n'allez pas réécrire le super prompt de l'étape C à chaque fois. Utilisez les Gems. Ce sont des versions personnalisées de Gemini avec une mémoire et des instructions pré-enregistrées.

- Pourquoi ? Pour créer un outil presse-bouton qui vous donne toujours le même format de réponse qualitatif.

- L'action : Allez dans le gestionnaire de Gems → "Créer un Gem".

- Configuration :  
  - Nom : "Tuteur Data Science"  
  - Instructions : Collez le prompt structuré (PTCF) créé à l'étape C. Dites-lui : "À chaque fois que je te donne un nom d'algorithme, applique cette structure."

- Résultat : Désormais, vous ouvrez ce Gem, vous tapez juste "XGBoost", et vous obtenez immédiatement votre cours structuré avec analogie et code.

**Ce qu'il faut retenir**

- Canvas est votre meilleur allié pour transformer du code ou des maths en visualisation graphique.

- Ne restez pas bloqué sur l'écriture du prompt : utilisez le vocal ou demandez à Gemini d'écrire le prompt pour vous.

- Ne répétez pas les tâches répétitives : dès qu'un prompt fonctionne bien, sauvegardez-le dans un Gem pour vous créer votre propre boîte à outils d'apprentissage.

**Pour aller plus loin**  
[Every Google Gemini Feature Explained in One Video](https://youtu.be/7HuXSoDXfTY?si=Sey_lKx_LKCio-HP)  
[How to Write Prompts for Google Gemini Fast](https://youtu.be/QUoxvf4tZHQ?si=_zjPAdL6CfTSqWx2)  
[How To Use Gems in Gemini to Save Time with AI](https://youtu.be/yO01B8OoXfo?si=BFMOFGcOPhnYphsG)  
[How to Teach Yourself APIs (and anything else) Using Google's New Gemini Canvas: Step-by-Step Guide](https://youtu.be/OeYhQB5wT-I?si=UFz9doVr39O59_mf)
