---
title: "Pratique : Suivre un process"
description: "Application complète des 4 premières étapes du processus de création de slides au projet AudioPod X."
---

# 📄 Pratique : Suivre un process

Passons maintenant de la théorie à la pratique : appliquons méthodiquement les 4 premières étapes du processus de création de slides au projet "AudioPod X".

**Étape 1 : Le cadrage**

T (Thème)  
Mise en œuvre d'une pipeline de traitement du langage naturel (NLP) appliquée à un dataset de classification binaire (avis clients).

O (Objectif)

- Valider le module : Prouver qu'on a bien assimilé les 3 piliers du cours (nettoyage, vectorisation, modélisation).

- Démontrer la rigueur : Montrer qu'on n'a pas juste lancé un script, mais qu'on a comparé plusieurs approches (LogReg vs Random Forest) et qu'on sait justifier nos choix.

- Montrer la maîtrise des métriques : Prouver qu'on sait dépasser la simple accuracy pour analyser les faux positifs et négatifs (matrice de confusion).

M (Message)  
"Nous avons structuré des données brutes via un prétraitement NLP rigoureux pour entraîner un modèle de régression logistique qui atteint 88% de fiabilité, validant ainsi notre capacité à transformer du texte libre en outil de classification prédictif."

**Étape 2 : La narration**

Transcription brute  
"Ok... test micro... un deux. C'est bon.  
Alors, je dois raconter tout le projet pour préparer la soutenance. Allez, on se lance.  
Bon, le point de départ, c'est ce fameux dataset reviews.csv. Franchement, au début, quand on a chargé le truc avec Pandas, on s'est dit que ça allait être tranquille. 2000 lignes, c'est pas du Big Data, ça va vite à calculer. Mais la réalité... euh... la Situation, c'est que c'était inexploitable. C'était le chaos total. Y'avait des commentaires en majuscules, des fautes de frappe partout, des gens qui mettaient cinquante émojis 'pouce en bas'...  
Et là, la Complication majeure, c'est que... bah, un ordi, ça lit pas du texte. Si je balance ça direct dans un algo, il comprend rien. En plus, on avait un vrai problème de bruit : comment tu veux que le modèle fasse la différence entre un avis positif et négatif si les mots les plus fréquents c'est 'le', 'la', 'et', 'de' ? Ça polluait tout. Sans parler des mots comme 'aimer' et 'aimé', l'ordi croyait que c'était deux trucs différents. On était bloqués, impossible de sortir une prédiction fiable, on avait une accuracy ridicule de 55% au début, autant jouer à pile ou face quoi.  
Du coup, Résolution... on a sorti l'artillerie lourde sur le pré-processing. C'est là qu'on a passé 80% du temps en fait.  
J'ai commencé par coder une fonction de nettoyage. J'ai utilisé des Regex – d'ailleurs j'ai bien galéré avec les Regex – pour virer la ponctuation et les caractères spéciaux. Ensuite, on a utilisé la librairie NLTK.  
Euh... attends, il faut que je précise l'ordre... Ouais :

1. Tokenization : couper les phrases en mots.  
2. Stop-words : on a viré les mots vides.  
3. Lemmatisation : ça c'était cool. On a transformé tous les 'écouteurs', 'écoutes', 'écouter' en une seule racine. Ça a vachement réduit la taille du vocabulaire, c'était plus propre.

Ensuite, fallait vectoriser. Transformer les mots en chiffres. On a hésité entre le Bag of Words classique et le TF-IDF. On a testé les deux, et franchement le TF-IDF donnait de meilleurs résultats parce qu'il pénalisait les mots trop communs qui n'apportaient pas d'info.  
Après, pour la modélisation... là aussi y'a eu débat dans le groupe. Au début, on voulait faire les malins, on a lancé un Random Forest avec 100 arbres. Le truc a mis deux minutes à tourner, et boum : 99% d'accuracy sur le train set ! On était trop contents... sauf que sur le test set, on tombait à 70%. Gros overfitting. Le modèle apprenait par cœur.  
Du coup, on est revenus aux bases. On a pris une Régression Logistique. Plus simple, plus interprétable. Et là, c'était stable : 88% d'accuracy sur le test set. C'est solide.  
Mais le plus intéressant pour la conclusion – et ça faudra que j'insiste dessus devant le jury pour montrer qu'on a compris le business – c'est l'analyse des coefficients.  
En regardant les poids que le modèle donne aux mots, on a vu une séparation super nette.  
D'un côté, t'as 'Son', 'Bass', 'Audio' qui ont des coefficients hyper positifs. Donc le modèle nous dit : quand ces mots sont là, c'est un bon avis.  
De l'autre, t'as 'Batterie', 'Charge', 'Coupure'. Eux, ils plongent la note.  
C'est ça la vraie valeur du projet. On a pas juste classé des textes, on a identifié que le produit est bon techniquement sur l'audio, mais que le hardware d'alimentation est défaillant.  
Donc voilà... en résumé : on a pris des données sales, on les a nettoyées avec une pipeline NLP rigoureuse, on a évité le piège du sur-apprentissage, et on livre un modèle à 88% de fiabilité qui pointe exactement le problème de batterie.  
Je pense que ça tient la route comme histoire. Faudra juste que je mette les graphiques de la matrice de confusion pour prouver les chiffres."

Structure Situation - Complication - Résolution

- Situation (ce qu'on a au départ) : "Nous disposons d'un jeu de données de 2 000 commentaires clients sur les écouteurs AudioPod X. C'est un dataset standard que nous avons chargé avec la librairie Pandas pour tenter de comprendre les retours utilisateurs."

- Complication (le problème qui bloque tout) : "Côté business, la note moyenne chute drastiquement sans qu'on sache pourquoi. Côté technique, les données sont 'sales' (fautes, émojis, bruit) et inexploitables telles quelles par un algorithme (55% de précision initiale). De plus, nos tentatives avec des modèles complexes (Random Forest) ont échoué à cause du sur-apprentissage."

- Résolution (la solution apportée) : "J'ai mis en place une pipeline de traitement NLP rigoureuse (Nettoyage Regex, Lemmatisation NLTK, vectorisation TF-IDF) pour nettoyer le signal. J'ai ensuite stabilisé un modèle de Régression Logistique qui atteint 88% de fiabilité. L'analyse des coefficients a permis d'identifier mathématiquement la cause du problème : le produit est excellent sur le 'Son', mais défaillant sur la 'Batterie'."

**Étape 3 : Le squelette**

Slide 1 : La page de couverture

- Titre : Analyse de Sentiments AudioPod X  
- Sous-titre : Comment le NLP permet de transformer 2000 avis bruts en levier de performance produit.

Slide 2 : Le one-pager

- En bref : Notre modèle identifie avec 88% de fiabilité que la "Batterie" est la cause unique de la chute des notes.

Slide 3 : Contexte & Agenda (Le Contrat)

- Objectif : Comprendre la baisse de satisfaction (4.5 → 3.2) et valider la faisabilité d'une analyse automatisée.

Slide 4 : Traduction technique

- Méthodologie : Une pipeline de nettoyage (NLTK) transforme le texte bruité en vecteurs mathématiques exploitables.

Slide 5 : Le corps - Insight 1 (exploration)

- L'analyse exploratoire révèle un paradoxe : les avis longs sont les plus négatifs.

Slide 6 : Le corps - Insight 2 (choix modèle)

- Face au sur-apprentissage du Random Forest, la Régression Logistique offre la meilleure stabilité.

Slide 7 : Le corps - Insight 3 (performance)

- Le modèle final atteint une Accuracy de 88% et un F1-Score équilibré sur la classe critique.

Slide 8 : Le corps - Insight 4 (résultat Business)

- L'interprétabilité des coefficients isole le problème : le "Son" est plébiscité, l'alimentation ("Batterie") est sanctionnée.

Slide 9 : Conclusion (bilan)

- Bilan : Nous avons validé techniquement la chaîne de traitement et identifié la cause racine du problème.

Slide 10 : Next Steps (Ouverture)

- Prochaines étapes : Audit du fournisseur batterie et test d'un modèle BERT pour gérer l'ironie.

Annexe 1 : Data quality

- Le dataset est modérément déséquilibré (60% Positif / 40% Négatif), ne nécessitant pas de resampling. (Anticipe la question : "Avez-vous géré le déséquilibre des classes ?")

Annexe 2 : Benchmark modèles

- Comparatif détaillé : Le Random Forest souffre d'un écart de 29 points entre Train et Test (Overfitting). (Anticipe la question : "Pourquoi avoir jeté le Random Forest qui avait de meilleures stats ?")

Annexe 3 : Choix des hyperparamètres

- GridSearch : La régularisation C=1.0 offre le meilleur compromis Biais/Variance pour la Régression Logistique. (Anticipe la question : "Comment avez-vous tuné votre modèle ?")

Annexe 4 : Analyse des erreurs

- Zoom sur les Faux Positifs : Le modèle échoue principalement à détecter l'ironie. (Anticipe la question : "Quels sont les cas où votre modèle se trompe ?")

**Étape 4 : Le remplissage moche**

Slide 1 : La page de couverture

- Titre : Analyse de Sentiments AudioPod X  
- Sous-titre : Comment le NLP permet de transformer 2000 avis bruts en levier de performance produit.  
- Infos : Date : 05/01/2026. Groupe 4 : Thomas, Sarah, Mehdi.  
- Image : (Logo de l'école et une image générique d'écouteurs trouvée sur Unsplash).

Slide 2 : Le one-pager

- Titre : En bref : Notre modèle identifie avec 88% de fiabilité que la "Batterie" est la cause unique de la chute des notes.  
- Contenu :  
  - Problème : Note moyenne passée de 4.5 à 3.2.  
  - Solution : Algo de Régression Logistique sur les commentaires.  
  - Résultat : Le son est top, mais la batterie est nulle.  
  - Recommandation : Changer de fournisseur batterie.

Slide 3 : Contexte et agenda

- Titre : Objectif : Comprendre la baisse de satisfaction et valider la faisabilité d'une analyse automatisée.  
- Contenu :  
  - Le dataset : reviews.csv, 2000 lignes.  
  - Contexte : Chute brutale des étoiles sur les 3 derniers mois.  
  - Plan de la prez :  
    1. Méthodo NLP.  
    2. Résultats techniques.  
    3. Analyse business.

Slide 4 : Traduction technique

- Titre : Méthodologie : Une pipeline de nettoyage (NLTK) transforme le texte bruité en vecteurs mathématiques.  
- Contenu (Capture d'écran Code + Schéma moche) :  
  - (Capture d'écran du notebook Jupyter montrant la fonction clean\_text avec les regex).  
  - Liste des étapes :  
    - Lowercase.  
    - Remove punctuation.  
    - Stopwords (le, la, un...).  
    - Lemmatization (NLTK WordNet).  
    - Vectorisation : TF-IDF (min\_df=5).

Slide 5 : Le corps - Insight 1 (exploration)

- Titre : L'analyse exploratoire révèle un paradoxe : les avis longs sont les plus négatifs.  
- Contenu (Graphique brut Matplotlib/Seaborn) :  
  - (Copier-coller d'un histogramme bleu par défaut montrant la longueur des avis par note).  
  - Note : On voit que les avis à 1 étoile font en moyenne 150 mots, ceux à 5 étoiles font 20 mots.  
  - "Les gens contents disent juste 'Super', les gens pas contents écrivent un roman."

Slide 6 : Le corps - Insight 2 (choix modèle)

- Titre : Face au sur-apprentissage du Random Forest, la Régression Logistique offre la meilleure stabilité.  
- Contenu (Tableau Excel collé) :  
  - Tableau comparatif :  
    - Random Forest : Train 99% / Test 70% (Overfitting !).  
    - Logistic Regression : Train 90% / Test 88% (Bon).  
    - SVM : Trop lent à entraîner.

Slide 7 : Le corps - Insight 3 (performance)

- Titre : Le modèle final atteint une Accuracy de 88% et un F1-Score équilibré.  
- Contenu (Image) :  
  - (Capture d'écran de la output de classification\_report de Scikit-Learn avec les chiffres bruts).  
  - (Image de la Matrice de confusion générée par seaborn heatmap, avec les couleurs par défaut un peu moches).  
  - Commentaire : On a très peu de faux positifs.

Slide 8 : Le corps - Insight 4 (résultat business)

- Titre : L'interprétabilité des coefficients isole le problème : le "Son" est plébiscité, l'alimentation est sanctionnée.  
- Contenu (graphique barplot horizontal) :  
  - (Graphique montrant les Top 10 Features Importance).  
  - Barres vertes (Positif) : "Son", "Qualité", "Bass", "Design".  
  - Barres rouges (Négatif) : "Batterie", "Charge", "Coupure", "Service".  
  - Citation client : "Le son est ouf mais ça charge pas" (Ligne 452).

Slide 9 : Conclusion

- Titre : Bilan : Nous avons validé techniquement la chaîne de traitement et identifié la cause racine.  
- Contenu :  
  - Technique : Pipeline NLP robuste + Modèle LogReg validé.  
  - Business : Confirmation que le hardware (Batterie) est le seul point noir.  
  - L'analyse automatisée fonctionne et fait gagner du temps.

Slide 10 : Next steps

- Titre : Prochaines étapes : Audit du fournisseur batterie et test d'un modèle BERT.  
- Contenu :  
  - Court terme : Envoyer rapport aux ingénieurs produit.  
  - Long terme :  
    - Récupérer plus de données.  
    - Tester BERT (Deep Learning) pour mieux capter l'ironie (ex: "Super la batterie qui dure 10 min...").  
    - Mettre le modèle en API avec Flask.

Annexe 1 : Data quality

- Contenu :  
  - Screenshot d'un df\['sentiment'\].value\_counts().plot(kind='bar').  
  - Tableau brut :  
    - Positif (1) : 1200 lignes.  
    - Négatif (0) : 800 lignes.  
  - Note : "Pas besoin de SMOTE ou d'undersampling car le ratio est acceptable."

Annexe 2 : Benchmark modèles

- Contenu :  
  - Screenshot des courbes d'apprentissage (learning curves) générées par sklearn.  
  - On voit la courbe bleue (Train) à 100% et la courbe orange (Validation) qui stagne à 70% pour le Random Forest.  
  - Juste à côté, les courbes de la Régression Logistique qui sont proches l'une de l'autre (bon signe).

Annexe 3 : Choix des hyperparamètres

- Contenu :  
  - Copier-coller du code de la GridSearchCV.  
  - Snippet : param\_grid = {'C': [0.01, 0.1, 1, 10, 100]}.  
  - Output de la console : Best params: {'C': 1}.

Annexe 4 : Analyse des erreurs

- Contenu :  
  - Liste de 3 verbatims mal classés (copiés du CSV).  
  - Exemple 1 : "Génial, la batterie tient 5 minutes..." (Classé POSITIF à cause du mot "Génial", mais c'est NÉGATIF).  
  - Exemple 2 : "Pas mal, mais je m'attendais à mieux." (Classé NÉGATIF à cause de "pas", mais c'est neutre/positif).  
  - Note en gros : "Limite actuelle du Bag-of-words = Contexte non pris en compte."

**Étape 5 : Le design**  
[Sur Google Slides…]
