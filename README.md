# JFC_AO_ANALYSIS

Skill Claude pour l'analyse d'appels d'offres et la construction de réponses, conforme à la charte SQLI.

## Objectif

Industrialiser le traitement d'un appel d'offres entrant en trois phases :

1. **Synthèse** — analyse des documents client (PDF, Word, Excel) et production d'une vue synthétique de l'AO.
2. **Plan de réponse** — construction d'un plan détaillé avec consignes pour les contributeurs, sans rédiger à leur place.
3. **Go/NoGo** — remplissage du PPT décisionnel SQLI à partir des éléments collectés.

À chaque phase, le skill respecte les principes :

- **Ne jamais inventer** d'information. Si une donnée n'apparaît pas dans les documents, indiquer `Non connu`.
- **Ne jamais rédiger à la place des contributeurs**. Le rôle du skill est d'analyser, orienter, suivre et évaluer.
- **Checkpoint humain obligatoire** entre la Phase 1 (Synthèse validée) et la Phase 2 (Plan de réponse), pour arbitrer les choix structurants.

## Comment l'utiliser

1. Cloner ce repo dans un projet Claude Cowork dédié à un AO (un AO = un projet).
2. Charger le skill (Claude détecte `SKILL.md` et l'utilise automatiquement sur les sujets AO).
3. Déposer les documents client dans le projet Cowork.
4. Demander à Claude la phase souhaitée (synthèse, plan de réponse, Go/NoGo).

## Structure du repository

```
JFC_AO_ANALYSIS/
├── README.md                      # Ce fichier
├── SKILL.md                       # Point d'entrée du skill (lu par Claude)
├── references/                    # Détails opérationnels par phase et par sujet
│   ├── 01-phase-synthese.md
│   ├── 02-phase-plan-reponse.md
│   ├── 03-phase-gonogo.md
│   ├── extraction-checklist.md
│   ├── mise-a-jour.md
│   ├── livrables-formats.md
│   └── sqli-brand.md              # Charte graphique SQLI (palette, polices, layouts)
├── templates/                     # Templates SQLI versionnés (Word, Excel, PowerPoint)
│   ├── 20260527_SQLI_Word_Template_FR_C2_RESTREINT.docx
│   ├── 20260527_SQLI_Excel_template_XLSX.xlsx
│   ├── 20260527_SQLI_PowerPoint_Example_C2_RESTRICTED.pptx
│   ├── 2025_SQLI_Theme_ELEVATE.thmx
│   ├── 1__YYYYMMDD_Client_Project_GoNoGo_V2.pptx
│   ├── 1__YYYYMMDD_Client_Project_GoNoGo-Scoring_V4_4.xlsx
│   ├── 2__YYYYMMDD_Client_Project_Solution-Review_V2.pptx
│   └── 3__YYYYMMDD_Client_Project_Deal-Review_V2__1_.pptx
├── examples/                      # Exemples anonymisés (à venir)
└── .gitignore
```

## Périmètre exclu

- Les **documents clients** (cahiers des charges, annexes) ne sont jamais versionnés ici. Ils restent dans le projet Cowork.
- Les **livrables générés** (synthèse, plan, Go/NoGo remplis) restent également dans le projet Cowork.

## Versioning de la méthodologie

- `main` : version stable utilisée par tous les projets Cowork.
- Améliorations proposées via branches dédiées et pull requests.
- Chaque modification de template doit être documentée (changelog) car elle peut impacter les livrables passés.

## Mise à jour des templates

Les templates SQLI peuvent évoluer. Lorsqu'une nouvelle version est diffusée :

1. Remplacer le fichier dans `templates/`.
2. Mettre à jour les références dans `references/livrables-formats.md` si la structure change.
3. Commit avec un message explicite (ex. `templates: maj Word v2.1 — ajout style Encart`).
