> **Navigation :** [🏠 Accueil](index.md) | [🛠️ Cahier des Charges](cahier-des-charges.md)
> **Détail des modules :** [📥 Courriers](module-courriers.md) | [📁 Affaires](module-affaires.md) | [⚖️ Procédures](module-procedures.md)
> ---

# 📁 Pôle Affaires : La Fin de la Guerre des Numéros IC

Imaginez *(mais ne fermez pas les yeux, autrement vous ne pourrez pas lire la suite)*: vous allez rédiger un rapport. Vous ouvrez le dossier 2026, cherchez le dernier numéro d'affaire utilisé, faites "+1" dans votre tête, et commencez la rédaction d'un document bien chronophage.\
Vous déposez votre fichier enfin fini dans le dossier, vous attendez qu'il soit signé, vous passez à autre chose ... Et MALHEUR ! Un collègue a fait exactement la même chose pendant ce temps, et au moment de l'envoi, *l'adorable standardiste* vous dit qu'il y a un souci et que deux courriers, tous deux déjà signés, portent le même numéro !\
Rebelotte, il faut décider qui va changer de numéro, et devoir remettre son courrier en signature.\
Conflit de numéros, perte de temps, frustration. **Ce temps est révolu !**
> *D'accord, c'est un problème mineur et pas si fréquent que ça, mais bon si on peut s'en dispenser, pourquoi s'en priver ?*

## 🎟️ Le Distributeur Automatique de N° IC
Le cœur de ce module est la table `Affaires_IC`. Elle agit comme un générateur de tickets infaillible. 
Lorsque vous prenez en charge un nouveau dossier (une demande d'enregistrement, une visite d'inspection, un PAC...) :
1. Vous cliquez sur "Ajouter une Affaire".
2. **Le système verrouille instantanément le N° suivant** (ex: `IC260087`). Il est à vous.
3. Vous n'avez plus qu'à sélectionner votre nom dans la colonne **Agent** pour vous auto-attribuer cette réservation.

## 🧠 L'Intelligence Géographique (Liaison AIOT)
L'autre force de la création d'une Affaire, c'est sa connexion à la matrice de notre petit monde : la base **GUNenv**.
Lorsque vous renseignez le **N° AIOT** concerné par votre affaire, le système sait immédiatement de quoi on parle. Il va automatiquement rapatrier la **Subdivision** en charge du dossier. 
> Je dis "vous", parce que je pense que ce système pourrait être utilisé et étendu, notamment pour consulter les dossiers qui vous sont attribués, ou pour faciliter aux chefs de sub le pilotage de leurs minions respectifs.

## 📊 Un Tableau de Bord Visuel pour l'Unité
Pour que l'équipe et la Cheffe d'Unité puissent piloter l'activité sereinement, chaque Affaire dispose d'un **Statut** assorti d'un code couleur :
* 🟢 **Clôturé** : Le dossier est rangé, l'AP est signé, on n'en parle plus.
* 🔵 **En cours** : L'instruction bat son plein.
* 🟠 **En attente** : La balle est dans le camp de l'exploitant (attente de compléments), d'un autre service, ou on n'a juste pas encore eu le temps de s'y mettre.

**✨ Cette vue centralisée permet de filtrer en un clic toutes les affaires actives de la "Sub X", ou tous les "PAC" actuellement gérés par un agent spécifique. L'information est claire, nette et partagée. ✨**
