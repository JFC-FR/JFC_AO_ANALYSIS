# Phase 3 — Go/NoGo

## Objectif

Remplir le PPT de recommandation Go/NoGo SQLI à partir des informations collectées en Phase 1, sans modifier la structure ni la charte graphique du template.

## Déclencheur

L'utilisateur demande explicitement la production du Go/NoGo. Cette phase peut être lancée :

- en **parallèle de la Phase 2** (après validation de la synthèse),
- ou **avant la Phase 2**, si la décision Go/NoGo conditionne l'engagement de l'effort de réponse.

## Inputs attendus

- Synthèse validée de la Phase 1.
- Documents client (pour références ponctuelles).
- Le cas échéant : Excel de scoring Go/NoGo (`1__YYYYMMDD_Client_Project_GoNoGo-Scoring_V4_4.xlsx`) si l'utilisateur souhaite y associer la grille de scoring.

## Livrable

PPT Go/NoGo rempli, basé strictement sur `templates/1__YYYYMMDD_Client_Project_GoNoGo_V2.pptx`.

Convention de nommage : `1__[YYYYMMDD]_[NomClient]_[NomProjet]_GoNoGo_V2.pptx`.

## Règles strictes

1. **Ne pas modifier la structure** : pas de slide ajoutée, supprimée, ni réordonnée. Pas de changement de couleur, police, taille, position des éléments.
2. **Ne pas modifier les questions** posées dans le template.
3. **Ne rien inventer** : si une information n'est pas dans les documents client ou la synthèse, écrire `Non connu` à l'emplacement correspondant.
4. **Respecter les tags** `MANDATORY` et `RECOMMENDED` : remplir les MANDATORY systématiquement, et les RECOMMENDED dès qu'on dispose de l'information.
5. **Conserver la langue** d'origine de chaque slide (le template est bilingue FR/EN sur certaines slides — répondre dans la langue de la question).

## Cartographie des slides à remplir

Le template comporte 23 slides. Les slides à compléter (avec données issues de la synthèse) :

| Slide | Sujet | Statut | Source dans la synthèse |
|---|---|---|---|
| 1 | Cover (Client, Project, Date) | À remplir | Données projet |
| 4 | Leading Internal Stakeholders | MANDATORY | À demander à l'utilisateur |
| 5 | About the client | MANDATORY | Description du client |
| 6 | Project context | MANDATORY | Contexte projet, sources off-record |
| 7 | Issues and Objectives | MANDATORY | Besoin exprimé, contexte |
| 8 | Credit Check | MANDATORY | Données financières client (à demander si absentes) |
| 9-11 | Presales drivers | MANDATORY | Analyse de la valeur d'engagement |
| 12 | Ambition | MANDATORY | Ambition SQLI sur ce deal |
| 13 | Cooperation | MANDATORY | Conditions de coopération |
| 14 | Consultancy Conditions | MANDATORY | Conditions contractuelles vues dans le RC |
| 15 | Requested material | MANDATORY | Liste des livrables attendus par le client |
| 16 | Client Stakeholders | RECOMMENDED | Acteurs côté client (DSI, Métier, donneur d'ordre) |
| 17 | SQLI Response Timeline | MANDATORY | Calendrier de réponse |
| 20 | Exec Summary | MANDATORY | À construire avec l'utilisateur |
| 21 | (à identifier au remplissage) | MANDATORY | Selon contenu |
| 22 | BID Stakeholders | MANDATORY | Équipe pré-vente SQLI |

Les slides 2 (`PLEASE READ`), 3 (`SALES PROCESS`), 18 et 19 sont des slides d'information générale et ne doivent pas être modifiées.

## Démarche

### 1. Préparer la matière

Recharger la synthèse v1.x validée et l'extraction (extraction-checklist).

### 2. Cartographier l'information

Pour chaque slide à remplir, identifier l'information à reporter depuis la synthèse. Si une information manque côté équipe SQLI (acteurs internes, ambition, conditions de coopération…), poser la question à l'utilisateur **avant** de remplir, plutôt que d'écrire `Non connu` quand l'utilisateur pourrait répondre rapidement.

### 3. Remplir le template

Ouvrir le PPT template, repérer les zones de saisie (généralement les blocs `Please complete`), et y insérer le contenu. Conserver scrupuleusement :

- les zones de texte (taille, position, alignement)
- les polices et tailles (le thème SQLI s'applique automatiquement)
- les éléments graphiques (logos, icônes, formes)

### 4. Marquer les `Non connu`

Pour toute information manquante non récupérable par dialogue rapide, écrire `Non connu` dans la zone de saisie. Lister ces points en fin de présentation à l'utilisateur pour qu'il sache ce qui reste à compléter avant la revue Go/NoGo.

### 5. Mettre à jour la cover

Slide 1 : renseigner le nom du client, le nom du projet, la date au format `YYYYMMDD`.

## Sortie attendue

Présenter :

1. Le PPT Go/NoGo rempli avec son chemin.
2. La liste des slides effectivement remplies (MANDATORY + RECOMMENDED traités).
3. La liste des éléments restés en `Non connu` avec rappel de leur localisation (slide n°, sujet).
4. Une suggestion explicite de revue par l'utilisateur avant présentation en instance Go/NoGo.

## Cas particulier — scoring

Si l'utilisateur souhaite associer le scoring Go/NoGo :

- Conserver `1__YYYYMMDD_Client_Project_GoNoGo-Scoring_V4_4.xlsx` à l'identique en termes de structure.
- Renseigner uniquement les critères pour lesquels on a une information factuelle issue de la synthèse.
- Ne pas inventer de note. Pour les critères sans information, laisser vide et le signaler.
