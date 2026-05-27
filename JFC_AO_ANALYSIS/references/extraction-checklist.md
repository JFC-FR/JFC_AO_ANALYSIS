# Checklist d'extraction

Liste exhaustive des informations à chercher dans les documents client lors de la Phase 1. Si une information n'est pas trouvée : écrire `Non connu` et créer une question dans le XLS questions complémentaires.

## A. Identification du client

- Raison sociale exacte
- Forme juridique
- Secteur d'activité / branche métier
- Filiale, groupe d'appartenance
- Taille (CA, effectif) si disponible
- Implantation géographique pertinente pour le projet
- Historique éventuel avec SQLI (à compléter par l'utilisateur si pas dans les documents)

## B. Contexte du projet côté client

- Pourquoi ce projet maintenant (driver business ou technique)
- Enjeux stratégiques exprimés
- Périmètre d'utilisation (entités, géographies, populations)
- Existant à remplacer / faire évoluer
- Projets connexes mentionnés

## C. Description du projet

- Objet du projet (en une phrase)
- Description détaillée
- Présence de **lots** :
  - Nombre de lots
  - Intitulé de chaque lot
  - Réponse à chaque lot **obligatoire** ou **facultative**
  - Possibilité de répondre à un seul lot, plusieurs, ou tous
  - Notation par lot ou globale
- Phasage projet (Cadrage, Build, Run, etc.)
- Périmètre fonctionnel
- Périmètre technique
- Hors périmètre explicitement mentionné

## D. Donneur d'ordre et acteurs côté client

- Entité émettrice de l'AO (DSI, Direction Métier, Direction des Achats, Direction Générale…)
- Sponsor projet identifié
- Acteurs cités (chef de projet, MOA, MOE, métier, RSSI, DPO…)
- Relations entre acteurs si exprimées (rapports hiérarchiques, comités)
- Présence d'un AMOA / cabinet d'accompagnement de l'AO

## E. Budget et charge

- Budget annoncé (TTC / HT, par lot ou global)
- Fourchette ou plafond mentionné
- Charge exprimée (jours-homme, ETP, mois)
- Modèle économique attendu (forfait, régie, hybride, abonnement, capacitaire)
- Conditions de facturation (mensuel, à la livraison, jalons)
- Conditions de paiement (délai, acompte autorisé ou non)
- Révision de prix prévue

## F. Calendrier de réponse

- Date de publication de l'AO
- Date limite pour poser des questions
- Date limite de remise des offres
- Date prévue d'audition / soutenance (si applicable)
- Date prévue de notification
- Période de validité de l'offre demandée
- Format de remise attendu (papier, plateforme dématérialisée, email)

## G. Calendrier de la prestation

- Date prévue de démarrage
- Date de fin / durée totale
- Jalons intermédiaires (cadrage, MVP, mise en production, fin de garantie…)
- Durée de la garantie / TMA / Run

## H. Stack technique et architecture

Pour le projet global et pour chaque lot s'il y en a :

- Technologies imposées
- Technologies recommandées ou attendues
- Stack existante à intégrer
- Contraintes d'architecture (cloud, on-premise, hybride, souveraineté)
- Référentiels techniques imposés (normes ANSSI, RGAA, RGPD, ISO…)
- Outillage imposé (gestion de tickets, CI/CD, observabilité…)

## I. Besoin exprimé

Pour le projet global et pour chaque lot :

- Macro-fonctionnalités demandées
- User stories ou exigences fonctionnelles si fournies
- Exigences non fonctionnelles (perf, scalabilité, disponibilité)
- Volumétrie cible (utilisateurs, transactions, données)

## J. Dimensionnement

- Charge estimée par le client (s'il l'exprime)
- Équipe attendue (taille, profils, séniorité, mix on/off-shore)
- Localisation imposée (sur site, télétravail, mixte)
- Langue de travail

## K. Éléments particuliers par lot

Quand l'AO est multi-lot, vérifier pour chaque lot :

- Calendrier propre éventuellement différent
- Stack propre
- Critères d'évaluation propres
- Conditions financières propres
- Engagements de service propres

## L. SLA et engagements

- Niveaux de service attendus (disponibilité, temps de réponse, MTTR…)
- Plages horaires de service
- Taux de disponibilité contractuel
- Engagements de productivité ou de capacité
- Engagements de résultats (au-delà d'une obligation de moyens)

## M. Pénalités, bonus, malus

- Pénalités de retard
- Pénalités de non-qualité
- Pénalités de non-respect des SLA
- Bonus éventuels
- Plafonnement des pénalités
- Régime de responsabilité

## N. Critères d'évaluation de l'offre

- Critères listés
- Pondération de chaque critère
- Méthode de notation décrite
- Critères éliminatoires

## O. Points d'attention / risques

À signaler explicitement dans la synthèse :

- Délais de réponse < 4 semaines
- Délais d'exécution agressifs ou irréalistes
- Pénalités lourdes (> 5% du montant) ou non plafonnées
- Clauses d'exclusivité
- Propriété intellectuelle restrictive ou cession totale
- Engagement de résultats sans contrepartie
- Conditions financières contraignantes
- Exigences inhabituelles (caution bancaire élevée, certifications rares)
- Volume documentaire considérable côté réponse
- Critères éliminatoires nombreux ou très exigeants

## P. Checklist de conformité

Lister **toutes** les exigences marquées comme **obligatoires**, **éliminatoires**, ou formulées avec « devra », « doit », « impératif », « obligatoire », « sous peine de rejet ».

Cette liste sert de checklist de revue en fin de rédaction de la réponse.

## Q. Glossaire et acronymes

Recenser tous les termes métier, acronymes, abréviations. Si la définition n'est pas dans les documents : `Non connu` et question pour le client si nécessaire.

## R. Incohérences inter-documents

Croiser les documents pour détecter :

- RC vs CCTP (volumétrie, jalons, lots, prix)
- CCTP vs annexes techniques
- Calendrier vs charge demandée
- Critères d'évaluation vs périmètre demandé
- Termes utilisés inconsistants

## S. Inventaire des documents reçus

Pour chaque fichier :

- Nom du fichier (tel que reçu)
- Type (RC, CCTP, BPU, annexe technique, mail, présentation…)
- Date du document si datée
- Nombre de pages ou d'onglets
- Résumé en 3-5 lignes du contenu
- Statut de lecture (`Lu intégralement` / `Survolé` / `Non lu`)

## Format de stockage interne

Pour chaque information extraite, conserver en interne (sans nécessairement l'exposer dans les livrables) :

- La **valeur** extraite
- La **source** (nom du document + page/section ou cellule)
- Le **niveau de certitude** (extrait textuellement, paraphrasé, déduit)

Cela permet de tracer les informations et de répondre rapidement si l'utilisateur demande « où as-tu lu ça ? ».
