---
title: "Canvas : Hypothèse et test utilisateur"
description: "Template Canvas pour structurer votre hypothèse, votre prototype et votre guide d'entretien utilisateur."
---

# 📋 Canvas : Hypothèse et test utilisateur

![Infographie](../../assets/images/s4-travaux-pratiques.png)

## Objectif

Structurer votre démarche produit avant de coder : formuler une hypothèse claire, concevoir un prototype testable et préparer un guide d'entretien pour valider votre idée auprès d'un utilisateur réel.

## Pourquoi ce canvas existe

Mon conseil : ne tombez pas "amoureux" de votre solution. J'ai vu trop de projets data échouer parce que l'équipe construisait une fonctionnalité sans jamais vérifier que le problème existait vraiment. Ce document vous force à penser comme un **product manager** (responsable produit) avant de penser comme un développeur.

Le canvas suit une logique simple : **hypothèse → prototype → validation**. Vous allez construire un prototype réaliste (interface + IA) pour vérifier une hypothèse auprès d'un utilisateur testeur.

## Le template

Copiez tout le contenu ci-dessous dans un Google Doc partagé avec votre squad.

---

**Identité de la squad**

Membres de l'équipe : \[complétez\]

Le projet choisi \[cochez une case\] :

- [ ] A. L'assistant de rédaction
- [ ] B. Le coach de négociation
- [ ] C. Le chasseur intelligent
- [ ] D. Le détecteur de fraude
- [ ] E. Le concierge d'après-vente
- [ ] F. Le réparateur de poche
- [ ] Autre : \[complétez\]

---

**L'hypothèse (le pari risqué)**

*Avant de coder, quel est le pari que vous faites sur le comportement humain ?*

Nous pensons que : \[complétez\]
*(Décrivez le Persona et sa douleur)*
*Ex : "Les vendeurs novices abandonnent parce qu'ils ont le syndrome de la page blanche devant la description."*

Pour vérifier cela, nous allons créer : \[complétez\]
*(Votre solution IA en une phrase)*
*Ex : "Un générateur qui rédige tout à partir d'une simple photo."*

Nous saurons que c'est vrai si : \[complétez\]
*(Critère de succès lors du test)*
*Ex : "L'utilisateur testeur publie l'annonce sans modifier plus de 3 mots du texte généré."*

---

**Le prototype**

*Décrivez ici l'interface que l'utilisateur va voir et manipuler.*

La fonctionnalité (specs UX) :
*Où se trouve l'IA dans le parcours ? Comment l'utilisateur interagit-il ?*

Point d'entrée : \[complétez\]
*(ex : un bouton "M'aider à rédiger" sous le champ Description)*

Action utilisateur : \[complétez\]
*(ex : l'utilisateur uploade une photo)*

Réaction de l'interface : \[complétez\]
*(ex : le champ description se remplit tout seul avec une animation de chargement)*

Visuel / résultat :
\[collez ici un screenshot de votre interface obtenue sur Google AI Studio\]

---

**Le guide d'entretien**

*Vous allez faire manipuler votre prototype à un utilisateur. L'objectif n'est pas de "vendre" votre solution, mais d'observer honnêtement les réactions.*

Phase 1 : Avant de montrer le prototype (contextualisation)
*Vérifiez si le problème existe vraiment chez ce testeur.*
*Q1 : "La dernière fois que tu as été dans cette situation (vendre/acheter/réparer), quelle a été l'étape la plus pénible pour toi ?"*
\[complétez\]

Phase 2 : Pendant la démo (observation)
*Laissez l'utilisateur cliquer (ou simuler le clic) et observez sa réaction face au résultat.*
*Q2 : "Voici ce que l'interface te propose. Dis-moi honnêtement : qu'est-ce qui te choque ou te semble faux là-dedans ?"*
*(On cherche les hallucinations, le mauvais ton, ou l'UX confuse.)*
\[complétez\]

## Ce qu'il faut retenir

- Formulez votre hypothèse **avant** de construire quoi que ce soit : "Nous pensons que... pour vérifier, nous allons... nous saurons que c'est vrai si...".
- Un bon prototype n'a pas besoin d'être beau : il doit être suffisamment réaliste pour provoquer une réaction authentique chez le testeur.
- Le guide d'entretien sert à **écouter**, pas à convaincre : posez des questions ouvertes et observez les réactions.
- Les hallucinations de l'IA et les erreurs de ton sont les premiers signaux à surveiller lors du test.

## Pour aller plus loin

- [The Mom Test (Rob Fitzpatrick)](https://www.momtestbook.com/) — le livre de référence pour apprendre à poser les bonnes questions lors d'un entretien utilisateur
- [Lean Canvas (Ash Maurya)](https://leanstack.com/lean-canvas) — le modèle original qui inspire ce template, adapté aux startups
- [Google Design Sprint](https://designsprintkit.withgoogle.com/) — la méthode complète de prototypage et test en 5 jours, développée par Google Ventures
