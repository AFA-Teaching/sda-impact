# Structure Rules — Detailed Reference

## Lesson Files (non-index)

### Required order

```
---
title: "<Titre de la fiche>"
description: "<Description courte>"
---

# <Emoji> <Titre>

![Infographie](../../assets/images/<nom-descriptif>.png)

## Objectif

<Une phrase claire décrivant ce que l'étudiant saura faire après cette fiche.>

## <Sections de contenu (H2)>

<Corps du cours : méthode, étapes, exemples, scénarios.>

## Ce qu'il faut retenir

- Point clé 1
- Point clé 2
- Point clé 3

## Pour aller plus loin

- [Titre descriptif](url) — brève description du contenu
- [Titre descriptif](url) — brève description du contenu
- [Titre descriptif](url) — brève description du contenu
```

### Section details

**Frontmatter:**
- `title` must match the H1 text (without emoji)
- `description` should be a single sentence, useful for SEO and search

**H1:**
- Exactly one per file
- Starts with a topic emoji unique within the session
- Example: `# 💭 Maîtriser un concept avec l'IA`

**Infographic:**
- Must reference an existing file in `docs/assets/images/`
- Use relative path: `../../assets/images/<name>.png`
- Alt text: "Infographie" (singular) or "Infographies" if multiple

**Objectif:**
- Always an H2 section
- One sentence, starts with a verb (infinitive or second person)
- Example: "Savoir utiliser Canvas pour visualiser un concept complexe."

**Ce qu'il faut retenir:**
- 3 to 5 bullet points maximum
- Each bullet is one sentence, actionable or memorable
- No sub-bullets

**Pour aller plus loin:**
- Minimum 3 resources
- Each resource: `[Title](url) — what the student will find`
- Mix of formats: video, article, book, tool
- No bare URLs ever

## Index Files

Session index files have a different pattern:

```
---
title: "<Nom de la session>"
description: "<Description de la session>"
---

# <Book emoji> <Nom de la session>

<Paragraphe d'introduction : objectif global de la session.>

## Programme

<Navigation vers les sous-pages avec descriptions.>

## Ressources

<Playlist YouTube ou liens globaux de la session.>
```

Session book emojis:
- 📕 Session 1 (Productivité IA)
- 📗 Session 2 (Data Storytelling)
- 📘 Session 3 (Gestion de Produit)
- 📙 Session 4 (Travaux Pratiques)
