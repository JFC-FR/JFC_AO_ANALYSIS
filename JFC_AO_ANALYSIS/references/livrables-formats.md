# Spécifications des livrables

Spécifications détaillées de chacun des six livrables produits par le skill. Chaque livrable utilise un template SQLI versionné dans `templates/`.

## Identifiant et nommage

Tous les livrables suivent la convention :

```
[YYYYMMDD]_[NomClient]_[NomProjet]_[TypeLivrable]_v[X.Y].[ext]
```

Exemple : `20260605_Acme_PortailRH_Synthese_v1.0.pptx`

Exception : le Go/NoGo conserve le préfixe `1__` du template : `1__20260605_Acme_PortailRH_GoNoGo_V2.pptx`.

---

## 1. PPT de synthèse

### Template

`templates/20260527_SQLI_PowerPoint_Example_C2_RESTRICTED.pptx` (153 slides, système de design SQLI).

### Approche

Le template est un catalogue de layouts. Sélectionner les layouts pertinents et construire un deck dont la longueur s'adapte au volume d'information à restituer — **pas de limite haute ni basse imposée**. La qualité prime sur la concision : si l'AO est complexe (multi-lot, beaucoup de risques, glossaire dense), le deck peut faire 30-50 slides ; s'il est simple, il peut en faire 10. Respecter scrupuleusement les couleurs, polices et structures du template — ne créer aucun layout custom.

### Structure recommandée

Cette structure est un guide, à adapter en fonction de la matière disponible. Ajouter des slides quand un sujet le mérite (par exemple un lot complexe peut nécessiter plusieurs slides à lui seul), en retirer si le sujet est absent ou trivial.

| Slide | Contenu | Layout suggéré |
|---|---|---|
| 1 | Cover : Synthèse AO — [Client] / [Projet] | Cover Midnight |
| 2 | Sommaire | Cream Content |
| 3 | Le client en bref (raison sociale, secteur, contexte) | Cream Content + KPI |
| 4 | Contexte du projet | Cream Content |
| 5 | Description du projet | Cream Content |
| 6 | Lots (si multi-lot) : intitulés, obligatoire/facultatif | Cream Tables |
| 7 | Donneur d'ordre et acteurs côté client | Cream Content |
| 8 | Budget et charge | Cream KPI / Tables |
| 9 | Calendrier de réponse | Cream Timeline |
| 10 | Calendrier de la prestation | Cream Timeline |
| 11+ | Détail technique global ou par lot (stack, besoin, dimensionnement, SLA, pénalités) | Cream Content + Tables (1 slide par lot ou par sujet) |
| n-4 | Points d'attention et risques | Cream Highlights |
| n-3 | Checklist de conformité (top exigences obligatoires) | Cream Tables |
| n-2 | Glossaire (top 10-15 termes) | Cream Tables |
| n-1 | Incohérences détectées | Cream Highlights |
| n | Synthèse exécutive + recommandation de lecture | Cream Content / Closing Midnight |

### Règles

- **Mentionner `Non connu`** chaque fois qu'une information manque, sans tenter d'invention ni de déduction non sourcée.
- **Citer les sources en discret** (footer de slide ou note de bas de slide) quand pertinent.
- **Ne pas remplir le footer** avec autre chose que `[Client] – [Projet]` et la classification `C2 – Restreint` (par défaut).
- **Version** : afficher `v1.0` en page de garde et en footer.

---

## 2. XLS récapitulatif des documents

### Template

`templates/20260527_SQLI_Excel_template_XLSX.xlsx` (palette et police SQLI).

### Onglets

- `Inventaire` — un onglet unique suffit en v1.

### Colonnes

| Colonne | Type | Description |
|---|---|---|
| `#` | Entier | Numéro d'ordre |
| `Fichier` | Texte | Nom exact du fichier reçu |
| `Type` | Liste | RC / CCTP / BPU / Annexe technique / Annexe juridique / Mail / Présentation / Autre |
| `Date du document` | Date | Si datée, format JJ/MM/AAAA |
| `Pages / Onglets` | Texte | Ex. `42 pages` ou `5 onglets` |
| `Langue` | Texte | FR / EN / autre |
| `Résumé` | Texte long | 3-5 lignes |
| `Statut de lecture` | Liste | Lu intégralement / Survolé / Non lu |
| `Date d'analyse` | Date | Date du skill |
| `Notes` | Texte long | Observations particulières |

### Mise en forme

- Ligne d'en-tête : fond `#0F0E2B` (navy SQLI), texte blanc, gras.
- Lignes alternées : `#FFFFFF` et `#FFFAF0` (cream SQLI).
- Police : `TWK Everett Light`, 10pt (ou Arial 10pt en fallback si la police n'est pas disponible).
- Largeurs ajustées au contenu.
- Cellules `Résumé` et `Notes` en `wrap text`.
- Pas de cellule fusionnée hors en-tête.

---

## 3. XLS questions complémentaires

### Template

`templates/20260527_SQLI_Excel_template_XLSX.xlsx`.

### Onglets

- `Questions` — onglet principal.
- `Légende` — convention de marquage.

### Colonnes de l'onglet `Questions`

| Colonne | Type | Description |
|---|---|---|
| `ID` | Texte | Identifiant court (Q001, Q002…) |
| `Catégorie` | Liste | Client / Projet / Lot 1 / Lot 2 / Stack / SLA / Pénalités / Calendrier / Budget / Autre |
| `Question` | Texte long | Formulation exacte de la question pour le client |
| `Dimensionnant` | Liste | OUI / NON — voir règle ci-dessous |
| `Pourquoi on pose la question` | Texte long | Justification courte (utile en interne) |
| `Source du doute` | Texte | Document + page si applicable |
| `Date de la question` | Date | Date à laquelle la question a été identifiée |
| `Statut` | Liste | À poser / Posée / Répondue / Sans objet |
| `Date d'envoi` | Date | Si posée au client |
| `Réponse du client` | Texte long | À renseigner quand reçue |
| `Date de réponse` | Date | À renseigner quand reçue |

### Règle de marquage `Dimensionnant`

Une question est marquée `OUI` (= dimensionnante) si la réponse impacte :

- la charge ou le délai de réalisation,
- le prix,
- la composition de l'équipe,
- le périmètre fonctionnel ou technique.

### Mise en forme

- Mêmes conventions de palette et police que le récap docs.
- **Mise en évidence des questions dimensionnantes** : les lignes où `Dimensionnant = OUI` ont un fond `#C5D8F6` (bleu très clair SQLI) sur toute la ligne.
- L'en-tête de l'onglet `Légende` rappelle cette convention.

---

## 4. Word de réponse (plan + consignes)

### Template

`templates/20260527_SQLI_Word_Template_FR_C2_RESTREINT.docx`.

### Personnalisation de la page de garde

Appliquer un Trouver/Remplacer sur les placeholders du template :

| Placeholder | Remplacer par |
|---|---|
| `[Nom du Client]` | Raison sociale exacte |
| `[Nom du projet]` | Intitulé du projet |
| `[Référence du document]` | Référence interne (ex. `SQLI-AO-2026-014`) |
| `[Version]` | Version du document (ex. `v1.0`) |
| `[Date document]` | Date au format JJ/MM/AAAA |
| `[C2 – Restreint]` | Classification (par défaut C2) |

### Styles à utiliser exclusivement

| Niveau | Style Word |
|---|---|
| Titre de chapitre | `Titre1` |
| Sous-titre | `Titre2` |
| Sous-sous-titre | `Titre3` (max recommandé, 4 exceptionnellement) |
| Paragraphe courant | `Normal` |
| Encart introductif / accroche | `Accroche` |
| Puces niveau 1 | `Point` |
| Puces niveau 2 | `SubPoint` |
| Cadre tiret | `Tiret` |
| Mention client en exergue | `Client` |

### Structure du plan

Voir `references/02-phase-plan-reponse.md` — chapitre « Structure du plan Word ».

### Format des consignes par section

Pour chaque section du plan, le contenu Word respecte ce gabarit :

```
[Titre de la section]               <- style Titre1/2/3 selon niveau

**Demande client**                  <- en gras
[Citation ou paraphrase de l'attente, avec référence document / page]

**Objectif de la section**
[1 à 3 phrases — ce que cette section doit prouver au client]

**Éléments à couvrir**
- [point 1]                          <- style Point
- [point 2]
- [point 3]

**Longueur indicative** : [X pages / Y mots]

**Pièges à éviter** (le cas échéant) :
- [piège 1]

**Sources internes utiles** (le cas échéant) :
- [référence projet, document méthodologique]
```

### Sections internes (à retirer avant envoi client)

Toutes les sections internes (notes d'arbitrage, calendrier de rédaction, contacts) sont placées **avant** la synthèse exécutive et marquées clairement :

```
1. NOTES INTERNES — À RETIRER AVANT ENVOI CLIENT
```

Avec un style visuel suffisamment distinctif (par exemple, style `Accroche` sur le titre du chapitre).

### Pied de page et en-tête

Ne pas toucher au pied de page du template : il contient `© SQLI Group 2025 [Version] – [Date] – C2 - Restreint`. Le Trouver/Remplacer sur `[Version]` et la date est suffisant.

---

## 5. XLS de suivi de la réponse

### Template

`templates/20260527_SQLI_Excel_template_XLSX.xlsx`.

### Onglets

- `Plan & Suivi` — onglet principal.
- `Contributeurs` — liste des 10 contributeurs anonymes.
- `Légende statuts` — convention des statuts.

### Colonnes de `Plan & Suivi`

| Colonne | Type | Description |
|---|---|---|
| `ID section` | Texte | Numéro hiérarchique (ex. `6.1.2`) |
| `Titre section` | Texte | Tel qu'écrit dans le Word |
| `Lot concerné` | Liste | Commun / Lot 1 / Lot 2 / ... |
| `Demande client (résumé)` | Texte long | Une à deux phrases |
| `Longueur indicative` | Texte | Ex. `2 pages` |
| `Échéance interne` | Date | |
| `Statut` | Liste | À faire / En cours / À revoir / Validé |
| `Avancement %` | Pourcentage | 0% à 100% |
| `Notes` | Texte long | |
| `Contributeur 01` à `Contributeur 10` | Texte court | Mettre `X` ou nom court pour assigner |

### Onglet `Contributeurs`

| ID | Nom | Rôle | Disponibilité |
|---|---|---|---|
| Contributeur 01 | (à compléter) | | |
| ... | | | |
| Contributeur 10 | (à compléter) | | |

### Mise en forme

- Palette et police SQLI (cf. récap docs).
- Statuts colorés (mise en forme conditionnelle) :
  - `À faire` : fond `#FFFAF0` (cream)
  - `En cours` : fond `#C5D8F6` (bleu très clair)
  - `À revoir` : fond `#8E8FEC` (lavande)
  - `Validé` : fond `#6DA5FF` (bleu clair), texte blanc gras
- Avancement % : barre de progression (mise en forme conditionnelle Excel).
- Ligne d'en-tête figée (`Freeze Panes` sur la ligne 2).

---

## 6. PPT Go/NoGo

### Template

`templates/1__YYYYMMDD_Client_Project_GoNoGo_V2.pptx` (23 slides).

### Règle absolue

**Aucune modification de structure, de design, de questions.** On remplit uniquement les zones de saisie.

Détail dans `references/03-phase-gonogo.md`.

---

## Palette et police SQLI (résumé)

Issues du thème ELEVATE et du template Excel :

| Élément | Valeur |
|---|---|
| Police principale | `TWK Everett Light` (fallback : Arial) |
| Texte foncé (dk1) | `#000000` |
| Texte clair (lt1) | `#FFFFFF` |
| Navy (dk2) | `#0F0E2B` |
| Cream (lt2) | `#FFFAF0` |
| Bleu primaire (accent1) | `#1F24E9` |
| Bleu clair (accent2) | `#6DA5FF` |
| Bleu très clair (accent3) | `#C5D8F6` |
| Slate (accent4) | `#425F8B` |
| Bleu-violet (accent5) | `#6164EB` |
| Lavande (accent6) | `#8E8FEC` |
| Hyperliens | `#1F24E9` |

Pour toute mise à jour de la charte, se référer en priorité à `references/sqli-brand.md` (fichier autoritaire fourni par SQLI).
