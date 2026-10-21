# Phase 4 : Les itérations

Chaque itération développe une story (ou une partie de story). Livrable : une fiche `docs/iterations/NN-nom-story.md` (modèle : `templates/iteration.md`).

La première itération est spéciale : architecture, modèle de données et mise en place de l'environnement (voir `4-architecture.md`).

## Les 4 étapes

### 1. Analyse et conception

- Rappeler la story : tableau **MoSCoW | Story | Difficulté**.
- **Identification des tâches** : découper la story en tâches concrètes, chacune décrite en quelques phrases du point de vue de l'utilisateur (quel écran, quel bouton, où il est redirigé ensuite).
- Pour chaque tâche : quelles API, quelles données, quels composants, quels services externes (notifications, carte, appareil photo…).
- Pour les échanges importants entre l'interface, le serveur et la base, faire un **diagramme de séquence** (Mermaid `sequenceDiagram`) : qui appelle qui, dans quel ordre, y compris le cas « pas les droits ».
- Pour les écrans : utiliser `impeccable` pour la conception.
- Montrer cette analyse à l’utilisateur avant d'implémenter si la story est grosse.

### 2. Implémentation

Séparer **Front-end** et **Back-end** :
- Lister les bibliothèques ou plugins ajoutés et pourquoi.
- Respecter la structure en couches (`4-architecture.md`).
- Mettre à jour `docs/04-donnees.md` et `docs/05-api.md` si quelque chose change.
- En cas de bug : `systematic-debugging`.

### 3. Test

- Logique métier : tests automatiques (`test-driven-development`).
- App web : vérifier dans un vrai navigateur (`webapp-testing`).
- Mobile : tester aussi sur un **vrai appareil** quand une fonction dépend du matériel (notifications push, appareil photo, localisation), car les émulateurs ne les gèrent pas toujours.
- Tester les flots alternatifs des cas d'utilisation (liste vide, permission refusée, pas les droits…).

### 4. Évaluation

- Faire une démonstration : captures d'écran ou description de ce que voit l'utilisateur, étape par étape.
- Vérifier que la story correspond aux attentes (`verification-before-completion`).
- Pour une grosse story : `requesting-code-review`.

## Problèmes rencontrés

Terminer chaque fiche par cette section : pour chaque problème, **ce qui s'est passé**, **pourquoi**, **la solution retenue**. Si rien de particulier, l'écrire (« Aucun problème particulier »).

## Fin d'itération

- Mettre à jour le backlog (story terminée) et, si besoin, le planning et les risques.
- Proposer la story suivante selon la priorité MoSCoW.
