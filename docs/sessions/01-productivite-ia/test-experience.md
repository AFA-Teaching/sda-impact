---
title: "Exercice : Expérience brouillon"
description: "Exemple de narration brute d'un projet étudiant à transformer en bullet points CV et récit STAR."
---

# 📄 Test : Expérience brouillon

Alors voilà, c'était un projet de semestre. On devait prédire les ventes d'une chaine de magasins Rossmann. J'étais avec 2 autres étudiants, Thomas et Sarah. C'était dur car les données étaient sales. J'ai utilisé XGBoost. On a eu une bonne précision à la fin.  
En fait, pour détailler un peu, au début on s'est dit "facile, c'est de la série temporelle", mais pas du tout. Enfin si, mais pas que. On a récupéré les CSV, y'avait train.csv et store.csv. Le premier truc galère, c'était de merger les deux. Parce que t'as les infos des ventes jour par jour, et les infos du magasin genre "est-ce qu'il est loin d'un concurrent ?" qui bougent pas.  
Du coup on a fait un pd.merge mais on a perdu des lignes au début, on comprenait pas pourquoi... ah si ! C'est parce que certains magasins n'avaient pas de données de compétition avant une certaine année. Bref.  
Le vrai cauchemar, c'était le nettoyage. Franchement, 80% du temps on l'a passé sur pandas.  
Par exemple, y'avait des jours où le magasin est "ouvert" mais il fait "zéro vente". On s'est pris la tête pendant deux jours là-dessus. En fait c'était des jours fériés locaux ou des inventaires, je sais plus. Du coup, on a dû créer une fonction pour virer ces lignes-là parce que ça faussait tout le modèle. Si c'est fermé, tu vends zéro, c'est logique, pas besoin de machine learning pour ça, tu vois ?  
Ah et les missing values ! Dans la colonne CompetitionDistance, y'avait plein de NaN. Thomas voulait supprimer les lignes, mais moi j'ai dit non, c'est trop précieux. Du coup, on a remplacé par la valeur médiane. Euh non, attends, la valeur max je crois ? Ou une valeur aberrante genre -1 pour que l'arbre de décision capte que c'est une info manquante. Bref, on a testé plusieurs trucs.  
Pour le Feature Engineering, c'est là qu'on a gagné des points. On a extrait le jour de la semaine, le mois, l'année... classique. Mais le "game changer", ça a été de calculer le nombre de jours depuis la dernière promo. Genre "StateHoliday", c'était des string "a", "b", "c", on a dû mapper ça en entiers.  
Sarah a eu l'idée de rajouter la météo externe, mais on n'a pas réussi à trouver un dataset propre qui matchait avec les localisations des magasins en Allemagne, donc on a laissé tomber.  
Niveau algo... alors là.  
On a commencé par une Régression Linéaire simple. Une catastrophe. Le score RMSPE (c'est la métrique Root Mean Squared Percentage Error, c'est ce qu'ils demandent sur Kaggle) était genre à 0.5, horrible.  
Ensuite on a tenté un Random Forest. C'était mieux, mais super lent à entrainer. Mon ordi chauffait tellement que je pouvais faire cuire un œuf dessus.  
Et là, j'ai découvert XGBoost. Franchement, c'est une machine de guerre ce truc. J'ai passé deux nuits à tuner les hyperparamètres avec GridSearchCV. C'était long... learning\_rate, max\_depth, n\_estimators.  
Au final, on a trouvé que le max\_depth à 10 marchait le mieux.  
Par contre, on a failli se planter sur la validation. Au début on faisait un train\_test\_split aléatoire. Grosse erreur ! C'est des séries temporelles ! Tu peux pas entrainer sur le futur pour prédire le passé. Le prof nous a défoncés lors de la revue à mi-parcours. Du coup, on a coupé temporellement : on entraine sur 2013-2014, on teste sur les 6 dernières semaines de 2015.  
Résultat final ? On est descendu à un RMSPE de 0.11 environ sur le set de validation. C'est pas le top mondial (les meilleurs sont à 0.09 je crois) mais pour un projet étudiant, on était contents.  
Ce que je retiens ? Le feature engineering bat l'algorithme. Toujours. Et XGBoost c'est la vie. Ah, et faut vraiment commenter son code parce que quand j'ai relu le notebook hier pour la soutenance, je savais plus ce que faisait ma fonction def process\_data\_v3\_final\_final(df).  
Voilà, en gros c'était ça l'aventure.
