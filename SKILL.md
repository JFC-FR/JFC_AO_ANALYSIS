---
name: ao-analysis
description: "Utilise ce skill dès qu'il s'agit d'analyser un appel d'offres (AO, RFP, RFI, consultation), de produire une synthèse d'AO, de construire un plan de réponse, ou de remplir un dossier Go/NoGo SQLI. Se déclenche sur la présence de documents client de type cahier des charges, CCTP, RC, AAPC, ou sur les mots-clés appel d'offres, RFP, AO, soumissionner, réponse à consultation, Go/NoGo, plan de réponse. Le skill encadre trois phases : Synthèse, Plan de réponse, Go/NoGo, avec un checkpoint humain obligatoire entre Phase 1 et Phase 2."
---

# AO Analysis — méthodologie SQLI

Skill d'analyse d'appels d'offres et de construction de réponses, conforme à la charte SQLI.

## Principes cardinaux — à respecter en toutes circonstances

1. **Ne jamais inventer.** Si une information n'est pas dans les documents fournis par le client, écrire `Non connu` (et ouvrir une question si pertinent).
2. **Ne jamais rédiger à la place des contributeurs.** Le skill produit des plans, des consignes, des analyses, des suivis — jamais le contenu final de la réponse commerciale ou technique.
3. **Checkpoint humain obligatoire** entre la Phase 1 (Synthèse) et la Phase 2 (Plan de réponse). Le passage en Phase 2 nécessite une validation explicite de l'utilisateur et un dialogue d'arbitrage sur les choix structurants.
4. **Respect strict des templates SQLI** (Word, Excel, PowerPoint Example, Go/NoGo). Couleurs, polices, structure, page de garde, en-tête, pied de page, classification : aucune modification.
5. **Le client doit pouvoir compléter sa demande.** Le skill prévoit une logique de mise à jour : régénération + changelog (voir `references/mise-a-jour.md`).

## Vue d'ensemble du workflow

```
                                              ┌─── XLS récapitulatif des documents
                                              │
[Documents client] ──► PHASE 1: Synthèse ─────┼─── PPT de synthèse
                                              │
                                              └─── XLS questions complémentaires

                              │
                              ▼
                       VALIDATION HUMAINE
                       (dialogue d'arbitrage)
                              │
                              ▼

[Synthèse validée] ───► PHASE 2: Plan de réponse ─┬─── Word plan + consignes (un seul doc)
                                                   │
                                                   └─── XLS suivi (10 contributeurs)

[Synthèse validée] ───► PHASE 3: Go/NoGo ─────────────── PPT Go/NoGo rempli
```

Les phases 2 et 3 peuvent être lancées en parallèle après validation de la Phase 1.

## Inventaire des templates (dans `templates/`)

| Usage | Fichier |
|---|---|
| Réponse Word (plan + consignes) | `20260527_SQLI_Word_Template_FR_C2_RESTREINT.docx` |
| Suivi de réponse, questions, récap docs | `20260527_SQLI_Excel_template_XLSX.xlsx` |
| Synthèse et tout autre PPT à produire | `20260527_SQLI_PowerPoint_Example_C2_RESTRICTED.pptx` |
| Thème PowerPoint SQLI | `2025_SQLI_Theme_ELEVATE.thmx` |
| Go/NoGo (à remplir, ne pas modifier la structure) | `1__YYYYMMDD_Client_Project_GoNoGo_V2.pptx` |
| Go/NoGo scoring | `1__YYYYMMDD_Client_Project_GoNoGo-Scoring_V4_4.xlsx` |
| Solution Review (référence, hors scope direct) | `2__YYYYMMDD_Client_Project_Solution-Review_V2.pptx` |
| Deal Review (référence, hors scope direct) | `3__YYYYMMDD_Client_Project_Deal-Review_V2__1_.pptx` |

## Convention de nommage des livrables

Tous les livrables générés par le skill suivent le format :

```
[YYYYMMDD]_[NomClient]_[NomProjet]_[TypeLivrable]_v[X.Y].[ext]
```

Exemples :

- `20260605_Acme_PortailRH_Synthese_v1.0.pptx`
- `20260605_Acme_PortailRH_Questions_v1.0.xlsx`
- `20260612_Acme_PortailRH_Reponse_v1.1.docx` (après complément client)

Pour le Go/NoGo, conserver le préfixe `1__` du template :

- `1__20260605_Acme_PortailRH_GoNoGo_V2.pptx`

## Pour les détails

| Sujet | Fichier |
|---|---|
| Phase 1 — Synthèse, livrables et règles | `references/01-phase-synthese.md` |
| Phase 2 — Plan de réponse, Word, XLS suivi | `references/02-phase-plan-reponse.md` |
| Phase 3 — Go/NoGo | `references/03-phase-gonogo.md` |
| Que faut-il extraire des documents client | `references/extraction-checklist.md` |
| Gestion des mises à jour client | `references/mise-a-jour.md` |
| Spécifications détaillées de chaque livrable | `references/livrables-formats.md` |
| Charte graphique SQLI | `references/sqli-brand.md` |

## Démarrage rapide

Quand l'utilisateur ouvre un projet Cowork avec des documents AO :

1. Confirmer la phase souhaitée (par défaut : Phase 1).
2. Lire `references/01-phase-synthese.md` et `references/extraction-checklist.md`.
3. Inspecter les documents fournis (PDF, DOC/DOCX, XLS/XLSX).
4. Produire les trois livrables de la Phase 1.
5. Présenter au validateur et attendre l'arbitrage avant de basculer en Phase 2.
