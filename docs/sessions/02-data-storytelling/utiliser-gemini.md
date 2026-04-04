---
title: "Utiliser Gemini"
description: "Utiliser Gemini comme accélérateur de réflexion pour structurer et améliorer vos présentations data science."
---

# 🤖 Utiliser Gemini

**Objectif :** Utiliser Gemini comme un accélérateur de réflexion et non comme un générateur automatique. Vous gardez le contrôle, Gemini gère la structure et le polissage.

**⚠️ Avertissement : Les outils magiques (Text-to-Slide)**  
J'ai testé des outils comme Gamma.app ou les slide generators automatiques.  
Le verdict : à éviter.

- Pourquoi ? Ils créent des slides génériques, verbeuses, souvent hors-sujet, avec des mises en page qui semblent professionnelles de loin mais qui sont vides de sens de près.

- Le risque : Vous perdez la maîtrise de votre récit. Le jour de la soutenance, vous vous retrouvez à présenter des slides que vous n'avez pas pensées, et le jury le sentira immédiatement ("C'est joli mais creux").

- L'alternative : Utilisez Gemini pour construire le fond, et faites la forme vous-même (ou avec des templates).

**Le process augmenté par de l'IA en 5 étapes**  
Voici comment intégrer Gemini (ou ChatGPT/Claude) à chaque étape de la méthode vue précédemment.

1\. Le cadrage et le narratif  
Vous avez votre README ou vos idées en vrac, mais vous bloquez devant la page blanche.

- Cas d'usage : Transformer une dictée vocale ou un document technique en récit fluide.

- Le prompt (clarifier la pensée) : "Je dois commencer à rédiger le narratif pour ma présentation de projet sur [mon modèle de prédiction de churn]. Pose-moi 5 questions clés sur mon projet (le problème, les données, le modèle, les résultats, l'impact) pour m'aider à structurer ma pensée et à ne rien oublier."

- Le prompt (synthétiser un README.md) : "Analyse ce document technique (ci-dessous) et extrais-en un résumé narratif de 300 mots qui explique le projet à un public non-technique. [Coller le contenu du README.md]"

2\. La structure et le plan (l'architecte)  
Transformer le narratif en une suite logique de slides.

- Cas d'usage : Définir le TOM (Thème, Objectif, Message) et l'agenda.

- Le prompt (adaptation audience) : "Je dois présenter mon projet [de pipeline MLOps] à deux audiences différentes. Génère un plan de présentation (agendas) pour [mon professeur (note la rigueur technique, le code, la méthode) ou un directeur business (Note le ROI, l'impact utilisateur)]. Liste les titres des 6 slides principales."

3\. Le contenu et les titres  
Rédiger le texte de chaque slide pour qu'il soit percutant.

- Cas d'usage : Trouver les fameux action titles.

- Le Prompt (titres en Z) : "Voici le contenu de ma slide : 'Modèle Régression = 72% acc, Modèle XGBoost = 91% acc'. Propose-moi 3 variantes de titres percutants qui donnent la conclusion tout de suite, du type 'Le passage à XGBoost a permis de gagner 19 points de précision'."

- Cas d'usage : Simplifier le jargon. "Explique-moi ce qu'est [un Random Forest] avec une analogie simple que mon neveu de 13 ans pourrait comprendre, pour l'utiliser en intro."

4\. La visualisation et le code  
C'est le super-pouvoir pour les data scientists.

- Cas d'usage : Idéation (quel graphique choisir ?). "Je veux montrer l'écart entre le budget prévu et le réel. Quel est le meilleur graphique pour ça ?" (Réponse attendue : waterfall chart).

- Cas d'usage : Générer du code Python propre. "Voici mon code Python pour un bar chart. Modifie-le pour qu'il soit style professionnel : fond blanc, pas de bordure, axes en gris clair, barres en gris sauf la plus haute en bleu foncé (#0057B8), police Arial 14. Donne-moi juste le code."

5\. Feedback et préparation  
Avant le jour J, faites critiquer votre travail.

- Cas d'usage : Le crash test. "Je vais te donner le plan et le script de ma présentation. Agis comme un jury sévère. Dis-moi précisément ce qui est faible ou manque de clarté. Ne sois pas gentil."

- Cas d'usage : Anticiper les questions pièges (Q&A). "Je présente ce projet [Classification d'images] à un jury technique. Quelles sont les 5 questions les plus difficiles qu'ils pourraient me poser sur la méthodologie ou les biais ? Aide-moi à préparer les réponses."

**Atelier pratique**  
Vous avez le fichier README.md du projet "AudioFuture" (analyse de sentiments).  
Votre mission : Utiliser Gemini pour générer le plan de la soutenance.

1. Ouvrez Gemini (ou votre LLM préféré).  
2. Copiez-collez le contexte du projet AudioFuture (les 3-4 points clés : 5000 avis, modèle NLP, problème de batterie identifié).  
3. Lancez le Prompt : "Agis comme un expert en communication data. Je dois présenter ce projet en 10 minutes à un jury mixte (Tech + Business). Propose-moi un plan en 6 slides avec pour chaque slide : Le titre d'action et les éléments visuels à inclure."  
4. Analysez le résultat : Est-ce que les titres racontent une histoire ? (Si non, challengez l'IA : "Rends les titres plus orientés résultats").

**En vidéo**  
[IA co-pilote : Prompts Gemini pour vos présentations data science](https://www.youtube.com/watch?v=YKF3nWJx8Iw&list=PLAO2ui_9t-UQiTCLs2yiQO2m9_oq-ItWQ&index=4)  
[Créer des présentations HTML avec un assistant Gemini](https://www.youtube.com/watch?v=3vT4mwJcYio&list=PLAO2ui_9t-UQiTCLs2yiQO2m9_oq-ItWQ&index=5)  
[Obtenir un feedback critique sur vos présentations avec Gemini](https://www.youtube.com/watch?v=JtnxD9Odp10&list=PLAO2ui_9t-UQiTCLs2yiQO2m9_oq-ItWQ&index=6)

**Des Gems**  
[📺 Document to HTML Presentation Converter](https://gemini.google.com/gem/1ceG85dtOVdgsvqecXnKT3CS0zX9ZaHzU?usp=sharing)  
[🧐 The Strict Professor](https://gemini.google.com/gem/1t5L-ZxcEYjvHckDbr0AKWN-_eAnpDpGP?usp=sharing)
