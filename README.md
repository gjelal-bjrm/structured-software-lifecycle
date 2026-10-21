# Structured Software Lifecycle

Un skill pour [Claude Code](https://claude.com/claude-code) qui applique une méthode de développement structurée, du besoin jusqu'à la livraison : cadrage, spécification, modèle de données, API, architecture, planification, analyse des risques et développement par itérations, avec une documentation tenue à jour à chaque étape.

La méthode ne dépend d'aucune technologie : elle convient aussi bien à un site web, une application mobile ou tablette, un programme desktop qu'à un outil interne.

*A Claude Code skill for running a software project end to end with a structured, technology-agnostic method. The skill content is written in French; Claude writes the project documentation in the user's language.*

## La méthode

| Phase | Ce qu'on fait | Livrables |
|---|---|---|
| 1. Documentation | Comprendre le problème, les utilisateurs, les technologies, l'architecture | Problématique, user personas, choix techniques, architecture, modèle de données, définition des API |
| 2. Spécification | Décider quoi construire | User stories classées MoSCoW et estimées (Fibonacci), product backlog, cas d'utilisation avec flots alternatifs |
| 3. Planification | Décider dans quel ordre et anticiper les problèmes | Planning par semaine, analyse des risques (impact × probabilité, mitigation, risque résiduel) |
| 4. Itérations | Développer une story à la fois | Analyse et conception → Implémentation → Test → Évaluation, puis « problèmes rencontrés » |

Les phases 1 à 3 ont lieu une fois au début du projet ; la phase 4 se répète pour chaque story. Pour une petite modification, le skill ne se déclenche pas : il est réservé aux nouveaux projets et aux fonctionnalités importantes.

La documentation produite est rangée dans un dossier `docs/` du projet, à partir des modèles fournis dans [`templates/`](skills/structured-software-lifecycle/templates).

## Installation

### Option 1 : comme plugin (recommandé)

```bash
claude plugin marketplace add gjelalb96/structured-software-lifecycle
claude plugin install structured-software-lifecycle@structured-software-lifecycle
```

### Option 2 : à la main

1. Cloner ce repo :
   ```bash
   git clone https://github.com/gjelalb96/structured-software-lifecycle.git
   ```
2. Copier (ou lier) le dossier `skills/structured-software-lifecycle` dans `~/.claude/skills/` pour l'avoir dans tous vos projets, ou dans `<votre-projet>/.claude/skills/` pour un seul projet.

### Vérifier

Dans une nouvelle session Claude Code, demandez : « Quels skills as-tu à disposition ? ». Puis lancez un projet : « Je veux créer une application de… ».

## Skills complémentaires (facultatifs)

Le skill fonctionne seul. Il sait aussi faire appel à d'autres skills quand ils sont installés, pour apporter plus d'expertise à certaines étapes. S'ils ne sont pas installés, Claude fait l'étape lui-même en suivant la méthode.

| Pour quoi | Skills | Source |
|---|---|---|
| Clarifier le besoin, tests, débogage, vérification, relecture de code | `brainstorming`, `test-driven-development`, `systematic-debugging`, `verification-before-completion`, `requesting-code-review` | [obra/superpowers](https://github.com/obra/superpowers) |
| Conception et qualité des interfaces | `impeccable` | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) |
| Finition et animations | `emil-design-eng`, `review-animations`, `improve-animations`, `animation-performance` | [emilkowalski/skills](https://github.com/emilkowalski/skills) |
| Tester une app web dans un navigateur | `webapp-testing` | [anthropics/skills](https://github.com/anthropics/skills) |

Selon la technologie de votre projet, des skills spécialisés sont aussi utiles, par exemple :

- **Mobile (Expo, React Native)** : [expo/skills](https://github.com/expo/skills), [callstackincubator/agent-skills](https://github.com/callstackincubator/agent-skills)
- **Web React / Next.js** : [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills)
- **Supabase** : [supabase/agent-skills](https://github.com/supabase/agent-skills)
- **Audit de sécurité** : [trailofbits/skills](https://github.com/trailofbits/skills)

Chaque repo explique sa propre installation. N'installez que ce dont vous avez besoin : trop de skills qui se recoupent peuvent se contredire.

## Contenu du repo

```
skills/structured-software-lifecycle/
├── SKILL.md       la page principale : les phases et quand utiliser quoi
├── reference/     une fiche détaillée par phase, lue seulement au moment utile
└── templates/     les modèles de documents à remplir pour chaque projet
```

## Origine

Cette méthode est issue du travail de Bachelor de Gjelal Bajrami (Haute École de Gestion de Genève, filière Informatique de gestion, 2019), puis adaptée aux pratiques actuelles et à l'utilisation avec Claude Code.

## Licence

[MIT](LICENSE)
