# Architecture et structure du projet

Fait partie de la phase 1 et de la première itération (mise en place de l'environnement).

## 1. Principe : séparer les responsabilités

Quelle que soit la technologie, le code est découpé en couches, chacune avec un seul rôle :

| Couche | Rôle | Exemple d'équivalent |
|---|---|---|
| **Vue / Interface** | Afficher et réagir aux actions de l'utilisateur | Écrans, composants React/Ionic/SwiftUI |
| **Contrôleur / Routes** | Recevoir une requête sur une adresse, vérifier les droits, appeler la logique, renvoyer la réponse | `Controller` (Spring), routes (Express, Next.js) |
| **Service / Logique métier** | Les règles du métier (par exemple : un spécialiste ne vote qu'une fois) | `Service` |
| **Accès aux données** | Lire et écrire en base, rien d'autre | `Dao` / `Repository` |
| **Modèle** | Les objets métier (Post, Utilisateur…) | `Model` / types |
| **Erreurs** | Les erreurs propres au projet (non autorisé, introuvable…) | `Exceptions` |
| **Outils** | Fonctions réutilisées partout (dates, images…) | `Tools` / `utils` |

Règle : une couche n'appelle que celle juste en dessous. L'interface ne parle jamais directement à la base (sauf avec un service comme Supabase et des règles d'accès bien définies).

## 2. Adapter à la technologie

Garde le principe, mais suis les conventions de la technologie choisie (nom et organisation des dossiers). En cas de doute, utilise le skill spécialisé de la technologie s'il est installé, ou suggère à l'utilisateur de l'installer (voir la liste des skills recommandés dans le README).

Décris la structure retenue dans `docs/01-cadrage.md` : un tableau **Dossier | Contenu**, et un schéma des composants (diagramme Mermaid).

## 3. Mise en place de l'environnement (première itération)

1. Créer le projet avec l'outil officiel de la technologie.
2. Créer la structure de dossiers ci-dessus.
3. Créer la base de données et ses scripts (création des tables, données de test).
4. Mettre en place la gestion de version (Git) et un premier commit.
5. Vérifier que tout démarre (« hello world » de bout en bout : l'interface affiche une donnée venue de la base).

## 4. Sécurité de base

- Vérifier les droits **côté serveur** à chaque requête, jamais seulement dans l'interface.
- Ne jamais mettre de mot de passe ou de clé secrète dans le code : utiliser des variables d'environnement.
- Valider les données reçues avant de les enregistrer.
- Avant une mise en production : un audit de sécurité (avec un skill de sécurité s’il est installé, par exemple ceux de Trail of Bits).
