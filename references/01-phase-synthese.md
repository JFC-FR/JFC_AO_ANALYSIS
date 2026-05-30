# Phase 1 — Synthèse de l'appel d'offres

## Objectif

Produire une vue synthétique de l'AO permettant à la direction et aux équipes de comprendre rapidement la demande, ses contraintes et ses zones d'ombre, avant d'engager un effort de réponse.

## Déclencheurs

- L'utilisateur partage des documents AO et demande une synthèse, un résumé, ou une analyse.
- L'utilisateur ouvre un nouveau projet Cowork avec des documents client et n'a pas encore lancé d'analyse.

## Inputs attendus

- Documents client : PDF, DOC/DOCX, XLS/XLSX (cahier des charges, RC, CCTP, AAPC, annexes techniques, BPU…).
- Éventuellement : courriels, comptes rendus de réunion, slides client.

Si aucun document n'est fourni, demander à l'utilisateur de les déposer dans le projet Cowork avant de continuer.

## Livrables (trois)

1. **PPT de synthèse** — vue exécutive structurée.
2. **XLS récapitulatif des documents** — inventaire des fichiers reçus avec résumé par document.
3. **XLS questions complémentaires** — questions à poser au client, avec mise en évidence des questions de dimensionnement.

Le détail des structures, colonnes, slides est dans `references/livrables-formats.md`.

## Démarche

### 1. Inventaire des documents

Lister tous les fichiers reçus. Pour chacun :

- Nom du fichier
- Type (RC, CCTP, BPU, annexe, mail, etc.)
- Date du document
- Pages ou nombre d'onglets
- Résumé en 3-5 lignes
- Statut : `Lu intégralement` / `Survolé` / `Non lu`

→ alimente l'**XLS récapitulatif des documents**.

### 2. Extraction des informations

Suivre `references/extraction-checklist.md` pour la liste exhaustive des éléments à chercher.

Pour chaque information :

- Citer la source (document + page/section) en interne pour traçabilité.
- Si l'information n'est pas explicite : écrire `Non connu` et créer une entrée dans la liste des questions.
- Si plusieurs documents donnent des informations contradictoires : signaler dans la section incohérences.

### 3. Détection des lots

Identifier si l'AO est divisé en lots :

- Un seul lot ou pas de notion de lot → traitement global.
- Plusieurs lots → produire le détail par lot dans la synthèse et indiquer pour chacun :
  - Numéro et intitulé
  - Réponse **obligatoire** ou **facultative**
  - Possibilité de répondre à un seul lot, plusieurs, ou tous

### 4. Détection des risques et points d'attention

Signaler dans la synthèse :

- Pénalités lourdes ou clauses bonus/malus
- Délais de réponse serrés (< 4 semaines)
- Délais d'exécution agressifs
- Exigences techniques inhabituelles
- Clauses d'exclusivité
- Engagement de résultats
- Propriété intellectuelle restrictive
- Conditions financières contraignantes (acompte refusé, paiement à 60+ jours, etc.)

### 5. Checklist de conformité

Extraire toutes les exigences marquées comme **obligatoires** ou **éliminatoires** dans les documents, pour vérification au moment de la finalisation de la réponse.

### 6. Calendrier consolidé

Compiler toutes les dates clés en un seul tableau :

- Dates côté réponse (questions, dépôt, soutenance, négociation, notification)
- Dates côté prestation (démarrage, jalons, livraisons, recettes, fin)

### 7. Glossaire et acronymes

Extraire tous les termes métier, acronymes et abréviations utilisés par le client. Une définition par entrée si elle apparaît dans les documents, sinon `Non connu`.

### 8. Détection d'incohérences

Croiser les documents pour repérer les contradictions :

- RC vs CCTP (volumétrie, jalons, lots)
- CCTP vs annexes techniques
- Calendrier vs charge mentionnée
- Critères d'évaluation vs périmètre demandé

### 9. Questions complémentaires

Pour chaque `Non connu`, contradiction, ou besoin d'arbitrage : créer une question dans l'**XLS questions complémentaires**.

Marquer les questions de **dimensionnement** (impact sur la charge, le délai ou le prix) — voir `references/livrables-formats.md` pour la convention de marquage.

## Sortie attendue

À la fin de la Phase 1, présenter à l'utilisateur :

1. Les trois livrables (PPT + 2 XLS) avec leurs chemins.
2. Un résumé en 5-10 lignes des points saillants.
3. Le nombre de `Non connu`, de risques détectés, de questions de dimensionnement.
4. Une invitation explicite au checkpoint :
   > "Synthèse v1.0 prête. Je te propose d'en discuter ensemble pour arbitrer les choix structurants avant de passer à la Phase 2 (plan de réponse). Dis-moi quand tu es prêt."

## Ne pas faire en Phase 1

- Ne pas commencer à rédiger ou esquisser une réponse.
- Ne pas proposer de plan de réponse.
- Ne pas remplir le Go/NoGo (il a sa propre phase, qui peut être déclenchée en parallèle après validation).
- Ne pas masquer les zones d'ombre par des suppositions.
