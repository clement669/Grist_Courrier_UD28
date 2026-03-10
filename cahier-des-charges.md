> **Navigation :** [🏠 Accueil](index.md) | [🛠️ Cahier des Charges](cahier-des-charges.md)
> **Détail des modules :** [📥 Courriers](module-courriers.md) | [📁 Affaires](module-affaires.md) | [⚖️ Procédures](module-procedures.md)
> ---

# 📋 Cahier des Charges - Base Courrier UD DREAL 28 (Grist)

Ce document trace l'avancement du projet.

## 1. Tables Référentielles (Les Fondations)
- [ ] **`AIOT_Sites`**
  - [ ] Import de la base de données GUNenv.
  - [x] Colonnes clés : N° AIOT, Nom Établissement, Commune, Subdivision.
- [x] **`Annuaire_Tiers`**
  - [x] Création à la volée activée.
  - [x] Colonnes clés : Nom, Type (Exploitant, BE, Mairie...), Contact.
- [x] **`Agents_DREAL`**
  - [x] Import de la table existante (15 agents).
  - [x] Colonnes clés : Nom, Prénom, Fonction, Sub, Extension, Portable.
- [x] **`Types_Procedures`**
  - [x] Colonnes clés : Type (PAC, CESS, etc.), Délai réglementaire par défaut (en jours).

## 2. Le Cœur Opérationnel (Courriers & Affaires)
- [x] **`Affaires_IC`** (Réservation et suivi des dossiers)
  - [x] `N° IC` : Génération automatique format "IC26xxxx" (Trigger formula).
  - [x] `Agent` : Référence vers Agents_DREAL.
  - [x] `Type` : Référence vers Types_Procedures.
  - [x] `AIOT` : Référence vers AIOT_Sites.
  - [x] `Sub` : Automatique (depuis AIOT) ou manuelle.
  - [x] `Objet` : Texte libre.
  - [x] `Création` : Date automatique.
  - [x] `Statut` : Choix avec code couleur (En cours, En attente, Clôturé).
- [x] **`Courriers_Entrants`**
  - [x] `Ordre d'arrivée` : Nombre entier (Saisie manuelle d'après boîte mail).
  - [x] `Chrono` : Génération auto format "AAnnnn" (Trigger formula).
  - [x] `Date Courrier` : Date.
  - [x] `Date de réception` : Date (Par défaut : date du jour).
  - [x] `Expéditeur` : Référence vers Annuaire_Tiers (Autocomplétion).
  - [x] `AIOT` : Référence vers AIOT_Sites.
  - [x] `Sub` : Automatique (depuis AIOT) ou manuelle.
  - [x] `Objet` : Texte.
  - [x] `Fil` : Référence vers Fils_Discussion.
  - [x] `Type de procédure` : Référence vers Types_Procedures.
  - [x] `Réponse à faire` : Bascule (OUI/NON).
  - [x] `Date limite` : Automatique (Date réception + Délai procédure) modifiable.
  - [x] `Répondu` : Formule booléenne (Automatique si lié à un courrier sortant).
  - [x] `Date réponse` : Formule Date (Automatique via courrier sortant).
  - [x] `Délai réponse` : Formule Numérique (Calcul auto en jours).
  - [x] `Commentaires` : Texte.
  - [x] `M` : Bascule (Enregistré réseau).
  - [x] `G` : Bascule (Enregistré GUNenv).
- [x] **`Courriers_Sortants`**
  - [x] `Date départ` : Date.
  - [x] `Date courrier` : Date.
  - [x] `Affaire` : Référence vers Affaires_IC.
  - [x] `Destinataire` : Référence vers Annuaire_Tiers.
  - [x] `Objet` : Texte.
  - [x] `Réf Entrant` : Référence Multiple vers Courriers_Entrants (Recherche hybride).
  - [x] `AIOT` : Automatique (depuis Entrant ou Affaire) ou manuelle.
  - [x] `Agent` : Référence vers Agents_DREAL.
  - [x] `Fil` : Automatique (depuis Entrant) ou Référence vers Fils_Discussion.

## 3. Suivi Réglementaire & Contentieux
- [x] **`Suivi_AP`**
  - [x] `Affaire` : Référence vers Affaires_IC.
  - [x] `AIOT` : Automatique (depuis Affaire).
  - [x] `Établissement` & `Commune` : Automatiques (depuis AIOT).
  - [x] `Type AP` : Choix avec code couleur.
  - [x] `Envoi BPE 1`, `Contradictoire`, `Rép Expl`, `Envoi Sign`, `Date Sign` : Dates.
  - [x] `Modif` : Bascule.
  - [x] `Recours` : Formule booléenne (Automatique si lié à un contentieux).
- [x] **`Contentieux`**
  - [x] `Requête` : Texte.
  - [x] `Juridiction` : Choix (TA, CAA...).
  - [x] `Attaquant` : Référence vers Annuaire_Tiers.
  - [x] `AP Attaqué` : Référence vers Suivi_AP (Déclenche le "OUI" du recours de l'AP).
  - [x] `AIOT` : Automatique (depuis AP attaqué).
  - [x] `Dépôt` : Date.
  - [x] `Obs` : Texte long.
