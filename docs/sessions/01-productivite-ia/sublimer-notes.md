---
title: "Sublimer ses notes"
description: "Capturer l'information en vrac puis laisser Gemini structurer, corriger et enrichir vos notes en fiches de révision parfaites."
---

# 📝 Sublimer ses notes

**Objectif :** Ne plus perdre de temps à faire de la mise en page pendant le cours. L'objectif est de capturer l'information en vrac, puis de laisser Gemini structurer, corriger et surtout enrichir vos notes pour en faire une fiche de révision parfaite.

**Le scénario**  
Vous êtes en cours visio. Le prof parle vite. Vous notez tout ce que vous pouvez : des phrases incomplètes, des fautes de frappe, des abréviations, des concepts flous… À la fin, vous avez un brouillon difficile à relire. Au lieu de passer 1h à le remettre au propre ou de revoir la vidéo, nous allons créer un outil qui le fait instantanément.

**La méthode**

1\. La technique des deux onglets (workflow de création)  
Pour travailler proprement, séparez la réflexion de la construction. Ouvrez deux onglets Gemini dans votre navigateur :

1. Onglet 1 (l'architecte) : Il servira à demander à Gemini de rédiger les instructions (le prompt).  
2. Onglet 2 (le constructeur) : Il servira à créer et tester le Gem final.

2\. Le meta-prompting (onglet 1)  
On ne va pas écrire les instructions complexes à la main. On va demander à Gemini de le faire pour nous.

- L'action : Dans l'onglet 1, écrivez un prompt de ce type : "Je veux créer un assistant IA expert en pédagogie. Son rôle est de prendre en entrée mes notes de cours brutes (mal écrites, incomplètes) et de générer une fiche de cours structurée, claire et enrichie. Rédige-moi les instructions pour cet assistant."

- Le résultat : Gemini va générer un texte long et précis, définissant le ton, la structure (Titre, Définitions, Exemples, Résumé) et les règles (corriger les fautes, compléter les trous).

3\. La création du Gem (onglet 2)  
Maintenant, on assemble.

- L'action : Allez dans le gestionnaire de Gems (Onglet 2) → "Créer un Gem".

- Configuration :  
  - Nom : "Fiche de Révision Maker"  
  - Instructions : Copiez-collez le texte généré par l'onglet 1.

- Le petit plus : Dans les instructions, assurez-vous qu'il est précisé que l'IA doit enrichir le contenu. Si vous avez noté "SVM = marge max", le Gem doit compléter avec une vraie définition de la maximisation de la marge dans les Support Vector Machines.

4\. Le test en conditions réelles  
C'est le moment de vérité.

- L'action : Prenez un bloc de notes brouillon (vos notes d'aujourd'hui ou l'[exemple fourni ici]()). Collez-le dans votre nouveau Gem.

- Le résultat : Voyez comment le Gem transforme le chaos en ordre. Il ajoute des titres, des puces, et comble les manques.

- Itération : Si le format ne vous plaît pas (ex: vous voulez plus d'emojis ou un format markdown spécifique), retournez dans l'onglet 1, dites "Modifie les instructions pour ajouter...", et mettez à jour le Gem.

**Ce qu'il faut retenir**

- Séparez les rôles : Utilisez toujours un onglet pour concevoir le prompt et un autre pour configurer l'outil.

- Capturez, ne formatez pas : En cours, concentrez-vous sur l'écoute et la prise de notes rapide. Gemini gère la forme (structure) et le fond (complétion) après coup.

- L'enrichissement : La vraie valeur ajoutée n'est pas juste la mise en page, mais la capacité du Gem à combler les trous de votre prise de notes grâce à sa base de connaissance.
