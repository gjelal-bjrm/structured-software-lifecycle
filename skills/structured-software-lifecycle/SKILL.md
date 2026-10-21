---
name: structured-software-lifecycle
description: Structured, technology-agnostic method to run a software project end to end — scoping, specification, data model, API, architecture, planning, risk analysis and iterative development with living documentation — for websites, mobile or tablet apps, desktop programs and tools. Use when starting a new project or app, adding a substantial feature or module, or when the user asks to structure, document, specify or plan a project (personas, user stories, backlog, use cases, data model, API definition, backend architecture, risk analysis, planning, iterations). Not for small fixes, quick questions or one-off edits.
---

# Structured Software Lifecycle

Méthode de développement indépendante de la technologie. Elle mène un projet du besoin jusqu'aux itérations de développement, en produisant une documentation claire et tenue à jour.

**Proportionner l'effort.** Projet nouveau ou grosse fonctionnalité : suivre les phases. Fonctionnalité moyenne dans un projet déjà cadré : aller directement à une itération (phase 4). Petite modification : ne pas utiliser ce skill.

**Langue.** Rédiger la documentation dans la langue de l'utilisateur.

## Les 4 phases

Les phases 1 à 3 ont lieu une fois, au début. La phase 4 se répète.

| Phase | Objectif | Fiche à lire | Livrables |
|---|---|---|---|
| 1. Documentation | Comprendre le problème, les utilisateurs, les technologies, l'architecture | `reference/1-cadrage.md`, `reference/3-donnees-et-api.md`, `reference/4-architecture.md` | Problématique, personas, choix techniques, architecture, modèle de données, API |
| 2. Spécification | Décider quoi construire | `reference/2-specification.md` | User stories (MoSCoW + estimation), backlog, cas d'utilisation |
| 3. Planification | Décider dans quel ordre et estimer les risques | `reference/5-planification-risques.md` | Planning par semaine, analyse des risques |
| 4. Itérations | Développer une story (ou une partie) à la fois | `reference/6-iteration.md` | Code, tests, démonstration, « problèmes rencontrés » |

Ne lis que la fiche de la phase en cours.

## Où ranger la documentation

Dans le projet, un dossier `docs/` :

```
docs/
├── 01-cadrage.md          problématique, personas, choix techniques, architecture
├── 02-backlog.md          stories MoSCoW, estimation, backlog
├── 03-cas-utilisation.md  cas d'utilisation détaillés
├── 04-donnees.md          modèle de données
├── 05-api.md              définition des API
├── 06-planning.md         planning et analyse des risques
└── iterations/
    └── NN-nom-story.md    une fiche par itération
```

Les modèles vides sont dans `templates/` : copie-les dans `docs/` et remplis-les. Si le projet a déjà sa propre documentation, adapte-toi à elle au lieu d'imposer cette structure.

## Skills complémentaires (facultatifs)

Cette méthode décide du **déroulé** du projet. D'autres skills peuvent apporter l'**expertise** à l'intérieur de chaque étape. Pour chacun : **s'il est installé, utilise-le ; sinon, fais l'étape toi-même** en suivant la fiche de la phase. Ne recopie jamais leur contenu.

| Moment | Skill recommandé |
|---|---|
| Clarifier un besoin flou avant la phase 1 | `brainstorming` (seulement la partie questions, la suite se fait avec cette méthode) |
| Écran, interface, rendu visuel (conception et évaluation) | `impeccable` ; finition : `emil-design-eng` |
| Animations | `review-animations`, `improve-animations`, `animation-performance` |
| Étape Test d'une itération | `test-driven-development` pour la logique métier ; `webapp-testing` pour une app web |
| Bug pendant une itération | `systematic-debugging` |
| Fin d'itération | `verification-before-completion`, puis `requesting-code-review` pour une grosse story |
| Technologie spécifique (mobile, React/Next.js, base de données…) | Le skill spécialisé de cette technologie s'il est installé ; sinon, suggère à l'utilisateur d'en installer un (voir le README) |

Si un skill complémentaire propose son propre déroulé de projet (par exemple un plan formel), cette méthode reste prioritaire : le plan d'une itération se fait avec `reference/6-iteration.md`.

## Règles générales

- Avancer phase par phase et montrer chaque livrable à l'utilisateur avant de passer à la suite.
- Les documents restent vivants : si une itération change le modèle de données ou une API, mets à jour `04-donnees.md` ou `05-api.md`.
- Toujours noter les problèmes rencontrés et leur solution : c'est la mémoire du projet.
