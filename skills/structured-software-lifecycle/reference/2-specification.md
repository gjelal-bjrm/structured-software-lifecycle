# Phase 2 : Spécification

But : décider précisément quoi construire. Livrables : `docs/02-backlog.md` (modèle : `templates/backlog.md`) et `docs/03-cas-utilisation.md` (modèle : `templates/cas-utilisation.md`).

## 1. User stories

Format : **« En tant que [persona], je souhaite [action] afin de [bénéfice]. »**

- Une story = un besoin d'un persona, testable.
- Les grosses stories sont des **EPIC** découpées en sous-stories numérotées (1.1, 1.2…).

## 2. Priorité MoSCoW

- **Must** : indispensable, le projet échoue sans.
- **Should** : important, mais le projet fonctionne sans.
- **Could** : bonus si le temps le permet.
- (Won't : explicitement hors du projet, à noter pour éviter les malentendus.)

## 3. Estimation

1. Choisir une **story de base** simple et bien connue, lui fixer une difficulté et une durée.
2. Estimer chaque story **par comparaison** avec la story de base.
3. Difficulté en suite de Fibonacci : 1, 2, 3, 5, 8, 13. Au-delà de 13, la story est trop grosse : la découper.
4. Durée en jours (1 jour = 8 h).

## 4. Product backlog

Tableau : **MoSCoW | EPIC | Story | Difficulté | Jours**, trié par priorité, avec le total des jours en bas.

## 5. Temps à disposition

Tableau : durée du projet, jours par mois, total en jours et en heures, puis le **temps réel** (environ 80 % du total, pour les imprévus). Comparer avec le total du backlog : si le backlog dépasse, retirer des Could ou des Should et le signaler à l’utilisateur.

## 6. Cas d'utilisation

D'abord un **diagramme global** : les acteurs (personas) et les cas d'utilisation qui les concernent (diagramme Mermaid si possible).

Puis, pour chaque cas important, une fiche détaillée :

- **Nom**, **Acteur**, **Acteur secondaire**, **Déclencheur** (ce qui lance le cas : un clic, un onglet…)
- **Flot principal** : étapes numérotées, en alternant « Le système… » et « L'utilisateur… », terminé par « Fin ».
- **Flots alternatifs** : numérotés par rapport à l'étape concernée (3a, 3a1…), avec où l'on reprend (« Retour à l'étape 1 », « Passage à l'étape 4 », « Fin »).

Les flots alternatifs sont essentiels : ce sont eux qui révèlent les cas d'erreur (pas de connexion, permission refusée, liste vide…) à gérer dans le code.
