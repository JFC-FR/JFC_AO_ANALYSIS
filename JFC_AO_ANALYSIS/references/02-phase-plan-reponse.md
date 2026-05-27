# Phase 2 — Plan de réponse

## Objectif

Construire un plan de réponse complet (Word) accompagné d'un tableau de suivi (XLS) qui :

- couvre **toutes** les attentes du client,
- donne aux contributeurs des **consignes claires de rédaction** sans rédiger à leur place,
- distingue les sections communes des sections par lot quand l'AO est multi-lot,
- permet de tracer qui rédige quoi et où on en est.

## Déclencheur

L'utilisateur a validé la synthèse de Phase 1 et confirme explicitement le passage en Phase 2.

⚠️ **Ne jamais lancer la Phase 2 sans validation explicite.** Si la synthèse est demandée immédiatement suivie d'un plan, demander la validation avant de continuer.

## Étape préalable obligatoire — dialogue d'arbitrage

Avant de générer le Word et le XLS de suivi, ouvrir un dialogue avec l'utilisateur sur les choix structurants :

1. **Sur quels lots répond-on ?** (si multi-lot)
2. **Quel angle commercial / promesse principale** souhaite-t-on porter ?
3. **Y a-t-il des partenaires ou sous-traitants** à intégrer dans le plan ?
4. **Y a-t-il des références clients spécifiques** à mettre en avant ?
5. **La proposition commerciale** est-elle au forfait, en régie, en mode hybride ?
6. **Y a-t-il des contraintes internes** (capacité, calendrier équipe, budget pré-vente) ?

Synthétiser les réponses de l'utilisateur en tête du plan Word, dans une section non destinée au client (notes internes), pour cadrer les contributeurs.

## Livrables (deux)

1. **Word de réponse** — un seul document, basé sur le template SQLI Word, contenant le plan + les consignes de rédaction pour chaque section.
2. **XLS de suivi** — tableau de pilotage avec 10 colonnes contributeurs anonymes.

Le détail des structures est dans `references/livrables-formats.md`.

## Structure du plan Word — principe directeur

**Il n'y a pas de plan imposé.** Le plan doit s'adapter à ce que le client demande. Deux cas :

### Cas 1 — Le client impose un plan de réponse

Si l'AO contient un plan de réponse, un sommaire-type, une grille de réponse, un canevas, ou liste les chapitres attendus (souvent dans le RC ou un document type « plan de réponse ») :

- **Reprendre ce plan à l'identique**, dans le même ordre, avec les mêmes intitulés.
- Ne pas ajouter de chapitre absent du plan client, sauf s'il est manifestement nécessaire (proposition commerciale, annexes obligatoires) — auquel cas le signaler explicitement à l'utilisateur dans le dialogue d'arbitrage.
- Ne pas en retirer.
- Respecter la numérotation client si elle est utilisée.

### Cas 2 — Le client n'impose pas de plan

Construire un plan qui maximise la **lisibilité** et la **pédagogie** par rapport aux attentes exprimées dans l'AO. Quelques principes :

- **Suivre l'ordre des préoccupations du client** : commencer par démontrer la compréhension du besoin, puis répondre point par point aux exigences telles qu'elles apparaissent dans le CCTP, et finir par les éléments transversaux (gouvernance, planning, proposition commerciale).
- **Aligner la profondeur sur les critères d'évaluation** : si « qualité de la méthodologie » pèse 40% de la note, la section méthodologie est plus développée que les autres.
- **Distinguer clairement les lots** quand il y en a plusieurs : sections communes regroupées, puis une section par lot.
- **Toujours prévoir** : compréhension du besoin, approche/méthodologie, organisation et équipe, planning, proposition commerciale, annexes (références, CV).
- **Toujours intégrer une section interne** en début de document, marquée comme **à retirer avant envoi client**, qui contient les arbitrages issus du dialogue de cadrage, le calendrier interne de rédaction et les contacts.

### Dans tous les cas

- **La proposition commerciale est dans le plan**, en fin de document, structurée selon le modèle économique retenu (forfait, régie, hybride, abonnement, capacitaire).
- **Chaque exigence du CCTP marquée comme obligatoire ou éliminatoire** doit avoir une section ou sous-section qui y répond explicitement — utiliser la checklist de conformité de la synthèse pour vérifier.
- **Chaque question dimensionnante du XLS questions** dont la réponse est connue doit alimenter le plan ; celles dont la réponse n'est pas connue doivent rester ouvertes (à arbitrer par l'utilisateur).

## Format des consignes par section

Pour **chaque section du plan**, fournir :

- **Demande client** — citation ou paraphrase de ce qui est attendu, avec référence document (page, paragraphe).
- **Objectif de la section** — ce que cette section doit prouver/démontrer au client.
- **Éléments à couvrir** — liste à puces des points à traiter obligatoirement.
- **Longueur indicative** — en pages ou nombre de mots.
- **Pièges à éviter** — quand pertinent (par exemple « ne pas confondre supervision et infogérance »).
- **Sources internes utiles** — quand connues (réf. projet passé, doc méthodologique).

⚠️ **Ne pas rédiger le contenu lui-même.** Les consignes orientent, les contributeurs rédigent.

## Application des styles Word

Utiliser exclusivement les styles du template SQLI :

| Niveau | Style |
|---|---|
| Titre de chapitre | `Titre1` |
| Sous-titre | `Titre2` |
| Sous-sous-titre | `Titre3` (max recommandé) |
| Paragraphe courant | `Normal` |
| Encart introductif / accroche | `Accroche` |
| Puces de niveau 1 | `Point` |
| Puces de niveau 2 | `SubPoint` |
| Cadre tiret | `Tiret` |

Personnalisation de la page de garde : appliquer un Trouver/Remplacer sur les placeholders du template Word :

- `[Nom du Client]` → nom client
- `[Nom du projet]` → nom projet
- `[Référence du document]` → référence interne
- `[Version]` → version du document
- `[Date document]` → date au format JJ/MM/AAAA
- Classification → `C2 – Restreint` par défaut (ou selon consigne projet)

## Structure du XLS de suivi

Une ligne par section/sous-section du plan Word. Colonnes :

- `ID section` (ex. 6.1.2)
- `Titre section`
- `Lot concerné` (ou Commun)
- `Demande client` (résumé)
- `Échéance interne`
- `Statut` (À faire / En cours / À revoir / Validé)
- `Avancement %`
- `Notes`
- 10 colonnes `Contributeur 01` à `Contributeur 10` (case à cocher / X pour assignation)

Le détail de la mise en forme est dans `references/livrables-formats.md`.

## Sortie attendue

À la fin de la Phase 2, présenter :

1. Le Word de réponse et le XLS de suivi avec leurs chemins.
2. Un récapitulatif : nombre total de sections, nombre de lots couverts, échéances clés.
3. Une recommandation sur l'ordre d'assignation des sections aux contributeurs.

## Ne pas faire en Phase 2

- **Ne pas rédiger le contenu de la réponse.** Plan + consignes uniquement.
- **Ne pas inventer de chiffres** (prix, jours-homme, ETP) : la proposition commerciale est rédigée par l'équipe, pas par le skill.
- **Ne pas affecter de contributeurs nommés** : 10 colonnes anonymes (`Contributeur 01` à `Contributeur 10`) que l'utilisateur renommera lui-même.
- **Ne pas modifier la structure du template Word** : page de garde, en-tête, pied de page, classification, polices.
