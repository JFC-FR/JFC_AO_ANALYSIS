# Gestion des mises à jour client

## Contexte

Pendant la durée de l'AO, le client peut compléter sa demande :

- Publication d'un additif au RC ou au CCTP
- Réponses à des questions (FAQ envoyée à tous les candidats)
- Annexes complémentaires
- Modification du calendrier de réponse

Les livrables initiaux doivent pouvoir être mis à jour **sans perdre le travail déjà engagé par les contributeurs** sur le Word de réponse.

## Principe directeur

À chaque mise à jour client, on produit **les deux** :

1. Une **régénération complète** de la synthèse et des livrables Phase 1 (PPT synthèse, XLS récap docs, XLS questions).
2. Un **changelog** explicite qui met en évidence ce qui a changé, à intégrer manuellement ou semi-manuellement dans le travail en cours (Word de réponse, XLS suivi).

Le changelog est essentiel : les contributeurs ont peut-être déjà rédigé des sections du Word — on ne peut pas écraser leur travail.

## Convention de versioning

Les livrables sont versionnés selon ce schéma :

- `v1.0` — première génération
- `v1.1`, `v1.2`… — corrections internes (typo, reformulation) sans nouvelle info client
- `v2.0`, `v3.0`… — nouvelle génération suite à un complément client significatif

La date dans le nom de fichier suit la date de la nouvelle génération (pas la date du document client).

## Démarche pas à pas

### 1. Détecter qu'il s'agit d'une mise à jour

Indices que l'utilisateur dépose un complément :

- Nouveaux fichiers dans le projet Cowork après une synthèse déjà produite
- Mention explicite : « le client a envoyé un additif », « nouvelle FAQ », « réponse aux questions »

Demander confirmation à l'utilisateur avant de lancer une régénération.

### 2. Inventorier la nouveauté

Comparer la liste des documents :

- Documents **nouveaux** (jamais analysés)
- Documents **mis à jour** (même nom, contenu différent — vérifier dates et tailles)
- Documents **retirés** (rare mais possible)

### 3. Analyser les nouveaux documents

Suivre `extraction-checklist.md` sur les nouveaux/modifiés.

### 4. Produire le changelog

Format : un fichier `CHANGELOG_vX.Y_to_vX+1.0.md` (ou un onglet dédié dans l'XLS récap docs).

Pour chaque changement, indiquer :

- **Type** : Ajout / Modification / Suppression / Précision
- **Sujet** : à quoi cela touche (calendrier, lot 2, SLA, etc.)
- **Détail** : description du changement
- **Source** : document client + page
- **Impact estimé sur la réponse** :
  - `Aucun` (info purement contextuelle)
  - `Mineur` (ajustement d'une section existante)
  - `Majeur` (refonte d'une section ou ajout de section)
- **Section(s) du Word potentiellement impactée(s)** : ID section dans le plan
- **Question levée** ou résolue : OUI/NON

### 5. Régénérer les livrables Phase 1

- Nouvelle version du **PPT synthèse** : incorporer les changements et mentionner en page 2 l'historique des versions.
- Nouvelle version du **XLS récap docs** : ajouter une ligne par nouveau document, mettre à jour les statuts.
- Nouvelle version du **XLS questions** : marquer les questions résolues par la nouvelle info client, ajouter les nouvelles questions levées.

### 6. Proposer une intégration dans le travail en cours

Pour la Phase 2 déjà engagée :

- **Ne pas régénérer automatiquement** le Word de réponse ni l'XLS de suivi.
- Présenter le changelog à l'utilisateur.
- Pour chaque changement Majeur ou Mineur, proposer les actions possibles :
  - Ajouter une nouvelle section au Word (préciser où dans le plan)
  - Modifier les consignes d'une section existante (préciser laquelle)
  - Mettre à jour le XLS de suivi (statut de section, échéance)
  - Marquer une section comme `À revoir` dans le XLS de suivi
- Laisser l'utilisateur arbitrer ce qui est effectivement répercuté.

### 7. Synchroniser le Word et le XLS de suivi

Une fois les arbitrages reçus, intégrer les modifications dans le Word et dans le XLS de suivi.

Convention : appliquer les modifications du Word en **mode suivi des modifications** (track changes) pour que les contributeurs voient ce qui a changé. L'auteur des modifications est `Claude`.

## Cas particulier — modification du calendrier de réponse

Si la mise à jour modifie la date limite de remise de l'offre :

- Mettre à jour le calendrier consolidé dans la synthèse.
- Mettre à jour la **slide 17** du Go/NoGo (SQLI Response Timeline) si Go/NoGo déjà produit.
- Recalculer les échéances internes dans le XLS de suivi (proportionnellement, ou demander un arbitrage à l'utilisateur).

## Cas particulier — modification d'un lot

Si le périmètre d'un lot évolue, ou si un lot est ajouté/supprimé :

- Régénérer la synthèse.
- Dans le changelog, signaler explicitement l'impact sur la structure du Word (ajout/suppression de sections par lot).
- Ne pas supprimer le travail des contributeurs sur un lot retiré : déplacer les sections concernées vers une zone « archive » du Word avec une note explicite.

## Sortie attendue après une mise à jour

Présenter à l'utilisateur :

1. Le changelog complet.
2. Les nouvelles versions des livrables Phase 1.
3. Une recommandation d'arbitrages pour le travail en cours (Phase 2).
4. La question : « Souhaites-tu que je propage maintenant les changements dans le Word de réponse et le XLS de suivi, ou les arbitres-tu avant ? ».
