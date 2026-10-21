# Données et API

Fait partie de la phase 1, et à mettre à jour à chaque itération qui les modifie. Livrables : `docs/04-donnees.md` et `docs/05-api.md` (modèle : `templates/api.md`).

## 1. Modèle de données

Le modèle logique de données (MLD) décrit les tables (ou collections), leurs champs et leurs liens.

- Partir des cas d'utilisation : chaque chose que le système enregistre ou affiche doit exister quelque part.
- Pour chaque table : nom, champs (nom, type, obligatoire ou non), clé primaire (l'identifiant unique), clés étrangères (les liens vers d'autres tables).
- Le dessiner en diagramme Mermaid `erDiagram`.
- Nommer de façon cohérente dans tout le projet (même langue, même style).

Bonnes pratiques actuelles :
- **Fichiers et images** : les stocker dans un stockage de fichiers (disque du serveur, S3, Supabase Storage…) et ne garder en base que l'adresse. Prévoir une miniature pour les listes et l'original pour le détail.
- **Identité** : utiliser une vraie authentification (compte, ou connexion anonyme d'un service comme Supabase/Firebase) plutôt qu'un identifiant d'appareil seul, qui se perd au changement d'appareil et se falsifie facilement.
- Prévoir dès le début la **pagination** des listes qui peuvent grandir.
- Préparer un script de création des tables et un script de données de test.

## 2. Définition des API

Une API est la liste des « adresses » que l'interface appelle pour lire ou enregistrer des données sur le serveur.

Regrouper par type de requête :
- **GET** : lire des données
- **POST** : créer
- **PUT / PATCH** : modifier
- **DELETE** : supprimer

Pour chaque API :
- **Titre** : ce qu'elle fait, en une phrase (« Afficher tous les posts identifiés d'un utilisateur »).
- **Quand** elle est appelée (quel écran, quelle action).
- **Adresse** : par exemple `GET /posts/identified?page=0&size=20`.
- **Authentification** : qui a le droit de l'appeler, et comment on le vérifie.
- **Paramètres** envoyés.
- **Exemple de réponse** en JSON valide.
- **Erreurs possibles** : par exemple 401 (non connecté), 403 (pas les droits), 404 (introuvable).

Règles : adresses au pluriel et par ressource (`/posts`, `/posts/{id}`), pagination sur les listes, format de réponse identique partout, noms de champs cohérents.

Si le projet n'a pas de serveur à soi (par exemple Supabase appelé directement), décrire à la place les tables, les règles d'accès et les fonctions appelées.
