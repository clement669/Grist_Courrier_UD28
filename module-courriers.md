> **Navigation :** [🏠 Accueil](index.md) | [🛠️ Cahier des Charges](cahier-des-charges.md)
> **Détail des modules :** [📥 Courriers](module-courriers.md) | [📁 Affaires](module-affaires.md) | [⚖️ Procédures](module-procedures.md)
> ---

# 📥 Pôle Courriers : L'Art de la Correspondance Automatisée

Si l'enregistrement initial des courriers reste une tâche de l'ombre *(savamment orchestrée en coulisses)*, la façon dont vous allez interagir avec ces courriers, y répondre et suivre vos délais va radicalement changer. Fini de chercher une référence perdue dans un tableur infini !

## 🔍 La Recherche "Hybride" (Le Saint Graal du Courrier Sortant)
C'est surtout de mon côté que ça facilitera les choses, mais ça limitera en conséquence les oublis et le risque d'erreur. Lorsque vous rédigez un courrier de réponse (Courrier Sortant), il faut le lier au courrier entrant initial. 
* **Avant :** Il fallait retrouver et copier-coller le bon N° de Chrono exact.
* **Maintenant :** Le champ "Réf Entrant" est intelligent. Il suffit de taper une partie de l'objet, le nom de l'exploitant, ou le N° d'ordre d'arrivée de la boîte mail. Le système filtre instantanément et propose le bon courrier. Un clic, et c'est lié.

## 🪃 L'Effet Boomerang (Zéro double saisie)
Magie noire ? Non, base de données relationnelle. Le simple fait de lier votre courrier sortant au courrier entrant déclenche une réaction en chaîne automatique sur la table des entrants :
1. La case **"Répondu"** se coche toute seule.
2. La **Date de réponse** se remplit avec la date de votre courrier sortant.
3. Le **Délai de réponse** (en jours) se calcule automatiquement.
L'information remonte en temps réel à Élodie ou Sandrine, qui pourront voir en un coup d'oeil si le dossier est traité.
> Note : une table "pilotage" pourra être ajoutée ensuite, qui permettra d'afficher en temps réel diverses statistiques pertinentes, comme le délai de réponse moyen, le nombre d'affaires en cours, le nombre global d'affaires traitées dans l'UD, et par sub.

## ⏱️ La Gestion Intelligente des Délais
Chaque courrier entrant peut être qualifié selon son "Type de procédure" (PAC, DAENV, CESS, etc.). 
Dès que ce type est renseigné, le système calcule et affiche automatiquement la **Date limite de réponse** en se basant sur les délais réglementaires. Bien sûr, l'administration ayant ses mystères et ses imprévus (et mes connaissances ayant leurs limites), le système est prévu pour être 100% flexible et cette date calculée reste modifiable manuellement si besoin.

## 🧵 Les Fils de Discussion
Pour les dossiers complexes ou les échanges à rallonge avec un exploitant têtu (MOF, te souviens-tu de d'un déchet contaminé à l'ETO i ly a quelques  temps ?), la colonne **Fil** fait son apparition.\
Elle permet de regrouper plusieurs courriers entrants et sortants sous un même "Ticket" thématique. Une vue parfaite pour reconstituer l'historique d'une conversation.
> Note : ce système pourra être étendu à d'autres choses.

## 🏷️ Des repères visuels clairs
Sur chaque courrier, des indicateurs visuels simples vous informent de son statut d'enregistrement :
* **[ M ]** : Le document est bien rangé sur le réseau. *(éventuellement, on pourra voir s'il est pertinent d'ajouter une colonne incluant le chemin d'accès)*
* **[ G ]** : Le document a été téléversé dans GUNenv. *(idem : si pertinent, pourquoi ne pas mettre un lien direct vers l'affaire sur GUN)*
