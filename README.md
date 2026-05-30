# BidManagerJFC

Skill Claude d'analyse d'appels d'offres et de construction de réponses,
conforme à la charte SQLI. Anciennement `ao-analysis`.

## Objectif

Industrialiser le traitement d'un appel d'offres entrant en trois phases :

1. **Synthèse** — analyse des documents client (PDF, Word, Excel) et production
   d'une vue synthétique de l'AO.
2. **Plan de réponse** — plan détaillé avec consignes pour les contributeurs,
   sans rédiger à leur place.
3. **Go/NoGo** — remplissage du PPT décisionnel SQLI.

Principes : ne jamais inventer (`Non connu` si absent), ne jamais rédiger à la
place des contributeurs, checkpoint humain obligatoire entre Phase 1 et Phase 2,
respect strict des templates SQLI.

## Messages du skill

- Au démarrage : « JFC va vous aider à analyser l'appel d'offre et à structurer
  la réponse. C'est parti ! »
- En fin de traitement : « Vous avez des suggestions pour améliorer ce
  BidManager Skill ? Contactez jfcrepeau@sqli.com »

## Dépendance

La génération des présentations est déléguée au skill **`sqli-pptx-canvas`**
(rendu graphique conforme au template SQLI). Pour un usage complet, installer
les deux skills. Exception : le Go/NoGo se remplit dans le template fourni, il
n'est pas régénéré.

## Structure du repository

```
JFC_AO_ANALYSIS/
├── README.md                 # Ce fichier
├── SKILL.md                  # Point d'entrée du skill (lu par Claude)
├── .gitignore
├── references/               # Détails par phase et par sujet
│   ├── 01-phase-synthese.md
│   ├── 02-phase-plan-reponse.md
│   ├── 03-phase-gonogo.md
│   ├── extraction-checklist.md
│   ├── mise-a-jour.md
│   ├── livrables-formats.md
│   └── sqli-brand.md
├── templates/                # Templates SQLI versionnés
├── examples/                 # Exemples anonymisés
└── BidManagerJFC.skill       # Archive prête à installer / partager
```

## Installer le skill

- Depuis le repo : cloner dans un projet Claude Cowork, Claude lit `SKILL.md`.
- Pour partager : envoyer `BidManagerJFC.skill`, le collègue l'installe via le
  bouton « Save skill ». Installer aussi `sqli-pptx-canvas` pour les PPT.

## Un AO = un projet Cowork

Les documents client et les livrables générés restent dans le projet Cowork,
ils ne sont pas versionnés ici.

## Versioning de la méthodologie

- `main` : version stable. Améliorations via branches et pull requests.
- Toute évolution de template est documentée (changelog), car elle peut impacter
  les livrables passés.
