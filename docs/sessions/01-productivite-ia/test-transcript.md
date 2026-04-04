---
title: "Exercice : Transcript"
description: "Exemple de transcription brute d'une réunion Sprint Retrospective à transformer en compte-rendu structuré."
---

# 📄 Test : Transcript

DOCUMENT CONFIDENTIEL - INTERNE ÉQUIPE DATA  
Réunion : Sprint Retrospective #32  
Date : 24/11/2023  
Durée : 1h00  
Facilitateur (Scrum Master) : Thomas  
Participants :

* Julie (Lead Data Engineer) - Humeur : Frustrée  
* Marc (Product Owner) - Humeur : Pressé / Exigeant  
* Léo (Stagiaire Data Science) - Humeur : Terrifié  
* Sarah (Data Scientist)

[00:00 - 00:05] : Ice Breaker & Check-in  
Thomas (SM) : Bon, on s'installe. Je sais que la semaine a été... compliquée. L'objectif aujourd'hui c'est pas de chercher des coupables, mais de comprendre ce qui s'est passé pour que le Sprint 33 se passe mieux. On fait un tour de table rapide ? Un mot pour décrire votre sprint.  
Julie (DE) : "Nettoyage". Ou "Enfer", au choix.  
Marc (PO) : "Urgence". Les stakeholders mettent la pression.  
Sarah (DS) : "Fatigant".  
Léo (Stagiaire) : ... "Désolé".  
Thomas : Ok. Léo, on a dit "Blameless culture". On va en parler calmement.  
[00:10 - 00:25] : L'incident de Production ("The Elephant in the room")  
Thomas : On commence par le gros morceau. L'incident de mardi matin. Le dashboard de la direction était down pendant 4 heures.  
Léo : Je... je voulais juste tester mon modèle de scoring en conditions réelles. Sur mon poste, le script tournait nickel. J'ai poussé sur la branche master parce que je pensais que c'était protégé, et le script a lancé une requête DELETE sur la table des features au lieu de l'écrire dans une table temporaire. J'ai confondu target\_table et source\_table.  
Julie (coupe la parole, énervée) : Ce n'est pas "juste" une confusion Léo ! C'est surtout qu'il n'y a AUCUNE revue de code. J'ai passé ma nuit de mardi à restaurer le snapshot de la base. J'ai dû appeler l'astreinte DevOps à 3h du matin.  
Sarah : Julie, calme-toi. Léo est stagiaire. Pourquoi il a les droits d'écriture en prod sur le Data Warehouse pour commencer ?  
Julie : Parce que Marc voulait que ça aille vite ! "Faut que Léo puisse déployer ses tests sans attendre les Ops". Voilà le résultat. On a bypassé la CI/CD (Intégration Continue), on a cassé la prod. Cqfd.  
Marc : Attendez, moi je veux juste que les features sortent. C'est votre cuisine interne la CI/CD. Si le stagiaire peut tout casser en un clic, c'est que votre système est mal foutu, non ?  
Thomas : Ok, stop. Action Item 1 : On revoit les permissions d'accès dès lundi. Action Item 2 : Plus aucun push en prod sans Pull Request validée par Julie ou Sarah. On est d'accord ?  
[Murmures d'approbation]  
[00:25 - 00:40] : La qualité des données (Le coup de gueule du Data Engineer)  
Thomas : Point suivant. On avait prévu de livrer le nouveau modèle de prédiction de churn. On en est où ?  
Julie : On est nulle part. J'ai mis un ticket rouge sur le board. "Blocked".  
Marc : Comment ça nulle part ? J'ai promis au Marketing qu'ils l'auraient pour leur campagne de Noël !  
Julie : Marc, tu as regardé les données brutes qui arrivent du CRM ? C'est une poubelle.  
Sérieusement. Le champ client\_id est vide une fois sur dix. Les formats de date changent en plein milieu du fichier : on passe de DD/MM/YYYY à MM-DD-YYYY sans prévenir. Et le pire : le champ pays... hier j'ai trouvé "France", "FR", "Farnce" et "Metropole".  
Mon pipeline ETL plante toutes les 30 minutes parce qu'il ne sait pas gérer ces exceptions. Je passe mon temps à écrire des règles de gestion d'erreurs (regex) au lieu de construire l'architecture. Je ne suis pas éboueuse de données.  
Marc : C'est le nouveau CRM Salesforce, l'équipe commerciale apprend encore à l'utiliser. Vous pouvez pas juste nettoyer ça automatiquement ? C'est ça votre job, non ? "Data Cleaning" ?  
Julie (rouge de colère) : Mon job c'est de construire des autoroutes de données, pas de trier les déchets manuellement ! Si "Garbage In", alors "Garbage Out". Ton modèle de prédiction dira n'importe quoi si les données d'entrée sont fausses.  
Sarah : Elle a raison Marc. Si on entraîne le modèle là-dessus, la précision sera en dessous de 60%. C'est inexploitable.  
Thomas : Ok. Action Item : Marc, tu organises une réunion avec le lead du CRM pour imposer des champs obligatoires et des listes déroulantes. On arrête la saisie libre. Tant que c'est pas fait, on gèle le ticket Churn.  
[00:40 - 00:55] : Le changement de KPI (Le Product Owner)  
Marc : Bon, puisqu'on parle du Churn... J'ai eu un retour du CODIR ce matin. La définition actuelle du "Churner" (client perdu), ça ne leur va plus.  
Sarah : ... Pardon ? On a validé la définition il y a 3 sprints. "Un client qui n'a pas acheté depuis 90 jours". Tout le feature engineering est basé là-dessus.  
Marc : Oui mais non. Le Marketing trouve que 90 jours c'est trop long. Ils veulent passer à 45 jours. Et ils veulent aussi exclure les clients B2B du calcul. Ah, et faudrait recalculer l'historique sur les 2 dernières années avec cette nouvelle règle pour lundi.  
[Silence pesant dans la salle]  
Julie : Tu te rends compte de ce que tu demandes ? Faut rejouer tout l'historique. Ça va prendre 2 jours de calcul sur le cluster. Et ça va coûter cher en Cloud Computing.  
Sarah : Et moi je dois réentraîner tout le modèle. Mes variables "temps moyen entre achats" ne veulent plus rien dire si on change la fenêtre de tir. C'est pas juste "changer un paramètre dans Excel", Marc. C'est un refonte de la logique métier.  
Marc : Écoutez, moi je transmets le besoin business. Si on garde l'ancienne définition, le dashboard ne sert à rien pour eux. C'est ça l'Agilité, non ? On s'adapte au changement ?  
Julie : L'Agilité c'est pas changer les fondations de la maison alors qu'on est en train de peindre le toit !  
Thomas : On se calme. Marc, tu ne peux pas changer ça pour ce sprint, c'est mort. Le sprint finit demain.  
On va créer une User Story "Spike" pour le prochain sprint : "Étude d'impact changement définition KPI". Sarah et Julie vont estimer la charge. Si c'est trop lourd, on dépriorise une autre feature.  
[00:55 - 01:00] : Clôture  
Thomas : Bon. C'était intense mais nécessaire.  
On résume :

1. Prod : On verrouille les accès. Léo, ne t'inquiète pas, c'est le métier qui rentre, mais plus jamais ça.  
2. Data Quality : Marc va voir l'équipe CRM pour stopper l'hémorragie.  
3. KPIs : On évalue le coût du changement de définition semaine prochaine.

On va boire un café ? Je crois qu'on en a besoin.  
Léo : Je peux payer les cafés... pour me faire pardonner ?  
Julie : Allez, ça marche. Mais touche pas à la machine à café, tu risques de la faire exploser. (Rires nerveux)  
Fin de la séance.
