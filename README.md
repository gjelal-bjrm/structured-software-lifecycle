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

Ce repo est aussi un **catalogue de plugins** : il contient la méthode et les skills complémentaires avec lesquels elle fonctionne le mieux. Commencez par ajouter le catalogue (une seule fois) :

```bash
claude plugin marketplace add gjelal-bjrm/structured-software-lifecycle
```

Puis choisissez **une** des options suivantes.

### Option A : le pack complet (recommandé)

La méthode et tous les skills complémentaires, en une seule commande :

```bash
claude plugin install structured-software-lifecycle-complete@structured-software-lifecycle
```

### Option B : la méthode seule

```bash
claude plugin install structured-software-lifecycle@structured-software-lifecycle
```

Le skill fonctionne seul : sans les skills complémentaires, Claude fait chaque étape lui-même en suivant la méthode, avec un peu moins d'expertise sur le design, les tests et le débogage.

### Option C : à la carte

Installez la méthode (option B), puis les complémentaires de votre choix parmi ceux du tableau ci-dessous, par exemple :

```bash
claude plugin install impeccable@structured-software-lifecycle
```

### Option D : sans plugin

Clonez ce repo et copiez (ou liez) le dossier `skills/structured-software-lifecycle` dans `~/.claude/skills/` (tous vos projets) ou dans `<votre-projet>/.claude/skills/` (un seul projet).

### Vérifier

Redémarrez Claude Code, puis demandez : « Quels skills as-tu à disposition ? ». Pour essayer la méthode : « Je veux créer une application de… ».

## Skills complémentaires

Le catalogue ne copie pas ces skills : il pointe vers leurs repos d'origine, vous recevez donc toujours leur dernière version, sous la licence de leurs auteurs.

| Plugin | Ce qu'il apporte | Skills | Source |
|---|---|---|---|
| `superpowers` | Clarifier le besoin, tests d'abord, débogage méthodique, vérification avant de dire « terminé », relecture de code | `brainstorming`, `test-driven-development`, `systematic-debugging`, `verification-before-completion`, `requesting-code-review`… | [obra/superpowers](https://github.com/obra/superpowers) |
| `impeccable` | Concevoir, critiquer, auditer et peaufiner les interfaces | `impeccable` | [pbakaus/impeccable](https://github.com/pbakaus/impeccable) |
| `emil-design-skills` | Finition de l'interface et animations | `emil-design-eng`, `animate`, `review-animations`, `improve-animations`, `animation-performance` | [emilkowalski/skills](https://github.com/emilkowalski/skills) |
| `webapp-testing` | Tester une app web dans un vrai navigateur (Playwright) | `webapp-testing` | [anthropics/skills](https://github.com/anthropics/skills) |

À savoir :
- `superpowers` installe tous ses skills, ainsi qu'un réglage qui rappelle à Claude, au début de chaque session, de vérifier s'il existe un skill adapté avant de répondre. La méthode reste prioritaire pour le déroulé du projet : les skills superpowers servent à l'intérieur de chaque étape.
- `impeccable` ajoute aussi ses propres agents et automatismes pour le design.

Selon la technologie de votre projet, des skills spécialisés sont aussi utiles (à installer depuis leurs propres repos) :

- **Mobile (Expo, React Native)** : [expo/skills](https://github.com/expo/skills), [callstackincubator/agent-skills](https://github.com/callstackincubator/agent-skills)
- **Web React / Next.js** : [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills)
- **Supabase** : [supabase/agent-skills](https://github.com/supabase/agent-skills)
- **Audit de sécurité** : [trailofbits/skills](https://github.com/trailofbits/skills)

N'installez que ce dont vous avez besoin : trop de skills qui se recoupent peuvent se contredire.

## Mettre à jour

```bash
claude plugin marketplace update structured-software-lifecycle
claude plugin update structured-software-lifecycle-complete
```

## Contenu du repo

```
.claude-plugin/
├── plugin.json         le plugin « méthode »
└── marketplace.json    le catalogue : la méthode, le pack complet et les complémentaires
bundle/                 le pack complet (une liste de dépendances, sans contenu propre)
skills/structured-software-lifecycle/
├── SKILL.md            la page principale : les phases et quand utiliser quoi
├── reference/          une fiche détaillée par phase, lue seulement au moment utile
└── templates/          les modèles de documents à remplir pour chaque projet
```

## Origine

Cette méthode est issue du travail de Bachelor de Gjelal Bajrami (Haute École de Gestion de Genève, filière Informatique de gestion, 2019), puis adaptée aux pratiques actuelles et à l'utilisation avec Claude Code.

## Licence

[MIT](LICENSE) pour ce repo. Les skills complémentaires gardent la licence de leurs auteurs respectifs.
