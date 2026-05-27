# Charte graphique SQLI

Référence graphique pour tous les livrables produits par le skill. La source autoritaire est le PowerPoint Example SQLI :

`templates/20260527_SQLI_PowerPoint_Example_C2_RESTRICTED.pptx`

Ce fichier consolide en texte les éléments à connaître ; en cas de doute, ouvrir le PPT et inspecter visuellement les layouts concernés.

## Polices

- **Titres et corps** : `TWK Everett Light` (police unique du thème SQLI ELEVATE)
- **Fallback** quand TWK Everett n'est pas installée : `Arial`

## Palette officielle (thème ELEVATE)

| Rôle | Code | Usage typique |
|---|---|---|
| Texte principal (dk1) | `#000000` | Corps de texte sur fond clair |
| Fond clair (lt1) | `#FFFFFF` | Fond blanc standard |
| Navy SQLI (dk2) | `#0F0E2B` | Slides Midnight, en-têtes Excel, accents forts |
| Cream SQLI (lt2) | `#FFFAF0` | Slides Cream, lignes alternées Excel |
| Bleu primaire (accent1) | `#1F24E9` | Accents principaux, titres, hyperliens |
| Bleu clair (accent2) | `#6DA5FF` | Statuts validés, hyperliens visités |
| Bleu très clair (accent3) | `#C5D8F6` | Surlignage doux, lignes en cours |
| Slate (accent4) | `#425F8B` | Texte secondaire, séparateurs |
| Bleu-violet (accent5) | `#6164EB` | Variations d'accent |
| Lavande (accent6) | `#8E8FEC` | Variations d'accent, statuts à revoir |

## Familles de layouts du PPT Example

Le template propose 152 slides organisées en familles. Choisir le layout adapté au type de contenu, **sans en créer de nouveau**.

| Famille | Plage approximative | Usage |
|---|---|---|
| Cover Layouts | 1-2 | Page de garde |
| Divider Layouts | 3-16 | Slides de transition entre parties |
| Cream Content Layouts | 17-37 | Contenus standards (texte, listes, deux colonnes) |
| Cream Tables & Highlights | 38-51 | Tableaux, KPI, mises en exergue |
| Midnight Layouts | 52-72 | Fond navy : impact, ouverture, clôture, transitions |
| Image Layouts | 73+ | Slides avec image dominante |

### Règles d'usage

- **Cover et closing** : utiliser un layout Midnight pour l'impact.
- **Corps du document** : layouts Cream pour la lisibilité.
- **Pas plus de 2 slides Midnight consécutives** — éviter la fatigue visuelle.
- **Pas de Midnight pour des contenus denses ou techniques** — le fond foncé nuit à la lecture.
- **Tableaux et données** : layouts Tables & Highlights, pas de tableau improvisé sur un layout texte.

## Conventions Word

Le template `templates/20260527_SQLI_Word_Template_FR_C2_RESTREINT.docx` fournit les styles suivants — **les utiliser exclusivement, ne jamais créer de style ad hoc** :

| Style | Usage |
|---|---|
| `Titre1` | Titre de chapitre |
| `Titre2` | Sous-titre |
| `Titre3` | Sous-sous-titre (maximum recommandé pour la TOC) |
| `Titre4` | Exceptionnel, hors TOC |
| `Normal` | Paragraphe courant |
| `Accroche` | Encart introductif ou mise en exergue |
| `Client` | Mention client en exergue |
| `Point` | Puces niveau 1 |
| `SubPoint` | Puces niveau 2 |
| `Tiret` | Cadre tiret |

Classification : `C2 – Restreint` par défaut sur tous les livrables internes. Adapter ponctuellement à `C0 – Public`, `C1 – Interne`, ou `C3 – Confidentiel` si requis.

## Conventions Excel

Reprendre la palette et la police du template `templates/20260527_SQLI_Excel_template_XLSX.xlsx` :

- Ligne d'en-tête : fond `#0F0E2B` (navy), texte `#FFFFFF`, gras
- Lignes alternées : `#FFFFFF` et `#FFFAF0` (cream)
- Mise en évidence : utiliser les bleus de la palette (`#C5D8F6`, `#6DA5FF`) — pas de jaune, rouge ou vert hors charte
- Police : `TWK Everett Light` 10pt (fallback Arial 10pt)
- Pas de cellule fusionnée hors en-tête

## Logo et éléments graphiques

Le logo SQLI est embarqué dans les templates Word et PowerPoint, généralement en pied de page ou page de garde. **Ne jamais le repositionner, le redimensionner ou le retirer**.

Les éléments décoratifs (formes, lignes, séparateurs) présents dans les layouts du PPT Example sont à conserver tels quels — ils participent de l'identité visuelle SQLI.

## Récapitulatif des dont'ts

- Pas de police hors `TWK Everett Light` (ou Arial en fallback).
- Pas de couleur hors palette ci-dessus.
- Pas de layout PowerPoint inventé : toujours partir d'un layout du PPT Example.
- Pas de style Word ad hoc : toujours utiliser les styles nommés du template.
- Pas de modification du logo, des pieds de page ou en-têtes des templates.
