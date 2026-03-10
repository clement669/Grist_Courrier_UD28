> **Navigation :** [🏠 Accueil](index.md) | [🛠️ Cahier des Charges](cahier-des-charges.md)
> **Détail des modules :** [📥 Courriers](module-courriers.md) | [📁 Affaires](module-affaires.md) | [⚖️ Procédures](module-procedures.md)
> ---

# ⚖️ Pôle Procédures & Contentieux : La Rigueur Sans l'Effort

Le suivi des Arrêtés Préfectoraux (AP) et des contentieux exige une précision absolue. Jusqu'ici, cela impliquait de recopier fastidieusement les noms d'établissements, les communes et les références croisées. Le nouveau système automatise le travail clérical pour nous laisser nous concentrer sur le fond.

## 📜 Le Suivi des Arrêtés Préfectoraux (AP)
La table `Suivi_AP` est conçue pour retracer la vie d'un projet d'arrêté, de sa rédaction à sa signature. Tout comme avant *mais en plus facile et plus pratique*.

* **Le Remplissage Magique :** Une seule chose à faire : lier l'AP à son N° d'Affaire (ex: `IC260042`). Dès cet instant, le système remonte la chaîne. Il trouve l'AIOT lié à l'affaire, et affiche **automatiquement** le nom de l'Établissement et sa Commune. Zéro frappe au clavier, zéro erreur possible.
* **La Ligne du Temps :** Des colonnes dédiées permettent de suivre chaque jalon de la procédure contradictoire : Envoi au BPE, transmission à l'exploitant, réception de ses observations (avec une case à cocher si le projet a dû être modifié en conséquence), et enfin la date de signature de l'AP final.

## 🏛️ La Gestion des Contentieux
Lorsqu'un exploitant ou un tiers conteste une décision du préfet, le recours est enregistré dans la table `Contentieux`. 

Ici aussi, l'interconnexion brille :
1. On renseigne le **N° de requête** et la juridiction (TAA, CAA...).
2. On sélectionne dans l'Annuaire qui est l'**Attaquant** (bien sûr, il suffit d'écrire et la liste déroulante s'affine à la volée pour autocompléter).
3. On pointe vers l'**AP attaqué**.

**Le système fait le reste :** Il récupère automatiquement l'AIOT du site concerné. Mieux encore, il repart dans la table du suivi AP, trouve la ligne de l'AP attaqué, et vient y cocher silencieusement la case **"Recours"**.\

Ainsi, n'importe quel agent consultant le suivi des AP verra immédiatement, grâce à cette alerte visuelle, que l'arrêté fait l'objet d'une procédure juridique en cours, sans avoir besoin d'aller fouiller dans l'onglet des contentieux.
