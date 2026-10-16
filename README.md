# Impact Data Scientist

[![Deploy to GitHub Pages](https://github.com/The-AI-Thinker/training-sda-impact/actions/workflows/deploy.yml/badge.svg)](https://github.com/The-AI-Thinker/training-sda-impact/actions/workflows/deploy.yml)

**Les compétences transversales essentielles pour le data scientist** — Sorbonne Data Analytics

Ce dépôt contient les supports de cours pour le module **Impact Data Scientist** du [Diplôme Sorbonne Data Analytics](https://formations.pantheonsorbonne.fr/fr/catalogue-des-formations/diplome-d-universite-DU/diplome-d-universite-KBVXM363/diplome-d-universite-sorbonne-data-analytics-KPMK3V7Z.html).

**[Accéder au portail étudiant](https://the-ai-thinker.github.io/training-sda-impact/)**

## Sessions

| # | Session | Objectif |
|---|---------|----------|
| 1 | **Productivité IA** | Devenir un étudiant et futur pro "augmenté" grâce à l'IA |
| 2 | **Data Storytelling** | Valoriser votre travail technique par la communication |
| 3 | **Gestion de Produit** | Comprendre le pourquoi avant le comment |
| 4 | **Travaux Pratiques** | Passer de la théorie à la pratique |

## Stack technique

- [MkDocs Material](https://squidfundamentals.github.io/mkdocs-material/) — générateur de site statique
- [GitHub Actions](https://github.com/The-AI-Thinker/training-sda-impact/actions) — déploiement automatique sur GitHub Pages
- Markdown avec extensions : admonitions, onglets, détails dépliables, emoji

## Structure du projet

```
docs/                       # Contenu du site (68 fichiers markdown)
├── index.md                # Page d'accueil
├── sessions/
│   ├── 01-productivite-ia/ # 18 fiches
│   ├── 02-data-storytelling/ # 22 fiches
│   ├── 03-gestion-produit/ # 23 fiches
│   └── 04-travaux-pratiques/ # 3 fiches
├── assets/images/          # 65 infographies PNG
└── stylesheets/extra.css   # CSS personnalisé
mkdocs.yml                  # Configuration MkDocs (navigation, thème, extensions)
```

## Développement local

```bash
pip install mkdocs-material
mkdocs serve
```

Le site sera accessible sur `http://localhost:8000`.

Le déploiement sur GitHub Pages est automatique à chaque push sur `main`.

## Contact

Adam Faik — [adam.faik.perso+sda@gmail.com](mailto:adam.faik.perso+sda@gmail.com)
