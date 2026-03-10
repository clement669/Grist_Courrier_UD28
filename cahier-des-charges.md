> **Navigation :** [🏠 Accueil](index.md) | [🛠️ Cahier des Charges](cahier-des-charges.md)
> **Détail des modules :** [📥 Courriers](module-courriers.md) | [📁 Affaires](module-affaires.md) | [⚖️ Procédures](module-procedures.md)
> ---

# 📋 Cahier des Charges - Base Courrier UD DREAL 28 (Grist)

Ce document trace l'avancement du projet.

## 1. Tables Référentielles (Les Fondations)
- [ ] **`AIOT_Sites`**
  - [ ] Import de la base de données GUNenv.
  - [ ] Colonnes clés : N° AIOT, Nom Établissement, Commune, Subdivision.
- [ ] **`Annuaire_Tiers`**
  - [ ] Création à la volée activée.
  - [ ] Colonnes clés : Nom, Type (Exploitant, BE, Mairie...), Contact.
- [ ] **`Agents_DREAL`**
  - [ ] Import de la table existante (15 agents).
  - [ ] Colonnes clés : Nom, Prénom, Fonction, Sub, Extension, Portable.
- [ ] **`Types_Procedures`**
  - [ ] Colonnes clés : Type (PAC, CESS, etc.), Délai réglementaire par défaut (en jours).

## 2. Le Cœur Opérationnel (Courriers & Affaires)
- [ ] **`Affaires_IC`** (Réservation et suivi des dossiers)
  - [ ] `N° IC` : Génération automatique format "IC26xxxx" (Trigger formula).
  - [ ] `Agent` : Référence vers Agents_DREAL.
  - [ ] `Type` : Référence vers Types_Procedures.
  - [ ] `AIOT` : Référence vers AIOT_Sites.
  - [ ] `Sub` : Automatique (depuis AIOT) ou manuelle.
  - [ ] `Objet` : Texte libre.
  - [ ] `Création` : Date automatique.
  - [ ] `Statut` : Choix avec code couleur (En cours, En attente, Clôturé).
- [ ] **`Courriers_Entrants`**
  - [ ] `Ordre d'arrivée` : Nombre entier (Saisie manuelle d'après boîte mail).
  - [ ] `Chrono` : Génération auto format "AAnnnn" (Trigger formula).
  - [ ] `Date Courrier` : Date.
  - [ ] `Date de réception` : Date (Par défaut : date du jour).
  - [ ] `Expéditeur` : Référence vers Annuaire_Tiers (Autocomplétion).
  - [ ] `AIOT` : Référence vers AIOT_Sites.
  - [ ] `Sub` : Automatique (depuis AIOT) ou manuelle.
  - [ ] `Objet` : Texte.
  - [ ] `Fil` : Référence vers Fils_Discussion.
  - [ ] `Type de procédure` : Référence vers Types_Procedures.
  - [ ] `Réponse à faire` : Bascule (OUI/NON).
  - [ ] `Date limite` : Automatique (Date réception + Délai procédure) modifiable.
  - [ ] `Répondu` : Formule booléenne (Automatique si lié à un courrier sortant).
  - [ ] `Date réponse` : Formule Date (Automatique via courrier sortant).
  - [ ] `Délai réponse` : Formule Numérique (Calcul auto en jours).
  - [ ] `Commentaires` : Texte.
  - [ ] `M` : Bascule (Enregistré réseau).
  - [ ] `G` : Bascule (Enregistré GUNenv).
- [ ] **`Courriers_Sortants`**
  - [ ] `Date départ` : Date.
  - [ ] `Date courrier` : Date.
  - [ ] `Affaire` : Référence vers Affaires_IC.
  - [ ] `Destinataire` : Référence vers Annuaire_Tiers.
  - [ ] `Objet` : Texte.
  - [ ] `Réf Entrant` : Référence Multiple vers Courriers_Entrants (Recherche hybride).
  - [ ] `AIOT` : Automatique (depuis Entrant ou Affaire) ou manuelle.
  - [ ] `Agent` : Référence vers Agents_DREAL.
  - [ ] `Fil` : Automatique (depuis Entrant) ou Référence vers Fils_Discussion.

## 3. Suivi Réglementaire & Contentieux
- [ ] **`Suivi_AP`**
  - [ ] `Affaire` : Référence vers Affaires_IC.
  - [ ] `AIOT` : Automatique (depuis Affaire).
  - [ ] `Établissement` & `Commune` : Automatiques (depuis AIOT).
  - [ ] `Type AP` : Choix avec code couleur.
  - [ ] `Envoi BPE 1`, `Contradictoire`, `Rép Expl`, `Envoi Sign`, `Date Sign` : Dates.
  - [ ] `Modif` : Bascule.
  - [ ] `Recours` : Formule booléenne (Automatique si lié à un contentieux).
- [ ] **`Contentieux`**
  - [ ] `Requête` : Texte.
  - [ ] `Juridiction` : Choix (TA, CAA...).
  - [ ] `Attaquant` : Référence vers Annuaire_Tiers.
  - [ ] `AP Attaqué` : Référence vers Suivi_AP (Déclenche le "OUI" du recours de l'AP).
  - [ ] `AIOT` : Automatique (depuis AP attaqué).
  - [ ] `Dépôt` : Date.
  - [ ] `Obs` : Texte long.
