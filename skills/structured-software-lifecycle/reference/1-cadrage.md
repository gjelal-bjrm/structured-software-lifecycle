# Phase 1 : Cadrage (Documentation)

But : avoir une vue d'ensemble du projet avant d'écrire du code. Livrable : `docs/01-cadrage.md` (modèle : `templates/cadrage.md`).

## 1. Problématique

- Quel problème réel le projet résout-il, et pour qui ?
- Liste à puces des problèmes, chacun en une phrase.
- Ce que le projet apporte : le besoin immédiat (ce que l'utilisateur fait tout de suite) et les bénéfices à long terme (par exemple des données récoltées qui serviront plus tard).

Si le besoin est flou, pose des questions à l’utilisateur, une par une, avant de rédiger.

## 2. Description du projet

Un ou deux paragraphes : ce que fait l'application, du point de vue de l'utilisateur, dans l'ordre où il l'utilise.

## 3. User personas

Un persona est un utilisateur type, décrit comme une vraie personne, pour savoir pour qui on construit chaque fonctionnalité.

Tableau à trois colonnes : **Rôle | Détails** (qui il est, ce qu'il sait, sa situation) **| Objectifs** (ce qu'il veut faire avec l'app, en liste).

- 2 à 4 personas, pas plus.
- Si plusieurs personas partagent des objectifs, préciser quel terme les regroupe (par exemple « utilisateur » = tous les rôles).

## 4. Fonctionnalités retenues

Liste courte des fonctionnalités qui seront réellement développées dans ce projet (le détail viendra dans le backlog).

## 5. Outils et technologies

Pour chaque technologie choisie : son rôle (front-end, back-end, base de données, gestion de version…) et **pourquoi** ce choix (contrainte du client, besoin, expérience). Pour choisir, tiens compte du type de projet et propose à l’utilisateur les options avec leurs avantages et inconvénients si rien n'est imposé.

## 6. Architecture

Décris l'architecture générale avec un schéma simple (texte ou diagramme) : quelles parties existent (interface, serveur, base de données, services externes) et comment elles communiquent. Le détail du back-end est dans `4-architecture.md`.

## 7. Méthode

Rappeler en une phrase que le projet suit cette méthode : Documentation, Spécification, Planification, puis itérations (Analyse et conception, Implémentation, Test, Évaluation).
