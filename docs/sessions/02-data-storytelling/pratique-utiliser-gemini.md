---
title: "Pratique : Utiliser Gemini"
description: "Exercice pratique : utiliser un README.md technique comme contexte pour demander à Gemini de construire une stratégie de soutenance."
---

# 📄 Pratique : Utiliser Gemini

Et maintenant, changeons de perspective : supposons que vous ayez déjà rédigé ce fichier README.md technique, et voyons comment l'utiliser comme contexte pour demander à Gemini de construire votre stratégie de soutenance.  
---

\# 🎧 AudioPod X \- Sentiment Analysis Project

\#\# 📋 Contexte du Projet

Ce projet a été réalisé dans le cadre du module "Introduction au NLP" de la formation Data Science.

\#\#\# Le scénario :

Les écouteurs AudioPod X subissent une chute critique de leur note moyenne (de 4.5/5 à 3.2/5) sur les 3 derniers mois. Avec plus de 2000 avis clients non lus, il est impossible de traiter l'information manuellement.

\#\#\# Notre mission :

1\. Nettoyer et structurer les données textuelles brutes.  
2\. Créer un modèle de Classification Binaire (Positif/Négatif) capable de prédire le sentiment.  
3\. Identifier les causes racines du mécontentement via l'interprétabilité du modèle.

\#\# 📂 Structure du Repository

\`\`\`  
├── data/  
│   ├── raw/  
│   │   └── reviews.csv          \# Dataset original (2000 lignes)  
│   └── processed/  
│       └── cleaned\_reviews.csv  \# Dataset après pré-traitement NLTK  
├── notebooks/  
│   ├── 01\_EDA\_Exploration.ipynb \# Analyse exploratoire & Visualisation  
│   └── 02\_Modeling\_NLP.ipynb    \# Pipeline de nettoyage & Modèles  
├── src/  
│   └── preprocessing.py         \# Fonctions de nettoyage (Regex, Lemmatization)  
├── slides/  
│   └── Presentation\_Groupe4.pdf \# Support de soutenance  
├── requirements.txt             \# Dépendances Python  
└── README.md  
\`\`\`

\#\# 🛠️ Installation & Usage

\#\#\# 1\. Cloner le projet :

\`\`\`bash  
git clone https://github.com/groupe4-datascience/audiopod-nlp.git  
cd audiopod-nlp  
\`\`\`

\#\#\# 2\. Installer les dépendances :

\`\`\`bash  
pip install \-r requirements.txt  
\`\`\`

\*\*Note :\*\* Nécessite le téléchargement des corpus NLTK : \`stopwords\`, \`wordnet\`

\#\#\# 3\. Lancer les notebooks :

\`\`\`bash  
jupyter notebook  
\`\`\`

\#\# ⚙️ Méthodologie (Pipeline NLP)

Nous avons comparé deux approches de vectorisation (Bag of Words vs TF-IDF) et deux modèles (Random Forest vs Régression Logistique).

\#\#\# 1\. Pré-traitement (Preprocessing)

Le texte brut étant très bruité (émojis, majuscules), nous avons appliqué la chaîne de traitement suivante (voir \`src/preprocessing.py\`) :

\* \*\*Cleaning\*\* : Suppression de la ponctuation et des caractères spéciaux (Regex).  
\* \*\*Tokenization\*\* : Segmentation des phrases en mots.  
\* \*\*Stop-words filtering\*\* : Suppression des mots vides (le, la, et...) via \`nltk.corpus\`.  
\* \*\*Lemmatization\*\* : Normalisation des mots (ex: "batteries" \-\> "batterie").

\#\#\# 2\. Modélisation

\* \*\*Tentative 1 : Random Forest\*\*  
   \* Résultat : 99% sur le Train set, mais 70% sur le Test set.  
   \* Diagnostic : Fort Overfitting (sur-apprentissage). Modèle rejeté.

\* \*\*Tentative 2 : Logistic Regression (Retenu)\*\*  
   \* Résultat : 88% Accuracy sur le Test set.  
   \* Avantage : Plus stable et offre une interprétabilité directe via les coefficients.

\#\# 📊 Résultats Clés & Insights Business

L'analyse des coefficients de la Régression Logistique nous a permis d'isoler les mots qui influencent le plus la note.

| Feature (Mot) | Coefficient | Interprétation |  
|---------------|-------------|----------------|  
| Son           | \`+2.4\`      | ✅ Point fort majeur du produit. |  
| Bass          | \`+1.8\`      | ✅ Qualité audio validée. |  
| Design        | \`+1.5\`      | ✅ Esthétique appréciée. |  
| Service       | \`-1.2\`      | ⚠️ Problème mineur de SAV. |  
| Batterie      | \`-3.2\`      | ❌ \*\*CAUSE RACINE DU PROBLÈME.\*\* |  
| Charge        | \`-2.8\`      | ❌ Problème lié à l'alimentation. |

\#\#\# Conclusion :

Le modèle confirme que la qualité sonore n'est pas en cause. L'insatisfaction client est corrélée à 90% à des problèmes matériels d'autonomie et de charge.

\#\# 🚀 Pistes d'amélioration (Next Steps)

\* Tester un modèle \*\*BERT\*\* (Transformers) pour mieux capter le contexte et l'ironie (ex: "Super la batterie qui dure 10 min").  
\* Mettre en place une \*\*API avec Flask\*\* pour classifier les nouveaux avis en temps réel.  
\* Affiner la liste des stop-words spécifiques au domaine audio.

\#\# 👥 Auteurs (Groupe 4\)

\* \*\*Thomas\*\* \- Data Cleaning & EDA  
\* \*\*Sarah\*\* \- Modélisation & Tuning  
\* \*\*Mehdi\*\* \- Interprétation & Slides

\---

📧 Pour toute question ou suggestion, n'hésitez pas à ouvrir une issue sur ce repository.
