# Phase 3 : Planification et risques

Livrable : `docs/06-planning.md` (modèles : `templates/planning.md` et `templates/risques.md`).

## 1. Planning

- Découper la durée du projet en **semaines**.
- Pour chaque semaine (ou groupe de semaines) : les activités prévues, en partant du backlog trié par priorité.
- Ordre habituel : cadrage et backlog, personas et cas d'utilisation, modèle de données et architecture, définition des API, mise en place de l'environnement, puis les stories Must, puis Should, puis Could.
- Réserver du temps à la fin pour relire le code, compléter les tests et finaliser la documentation.
- Tableau : **Activité | Début | Fin | Description**. Un diagramme de Gantt Mermaid est un plus.

## 2. Analyse des risques

But : repérer ce qui peut faire échouer le projet et prévoir comment l'éviter.

**Catégories** :
- **Développement** : technique, technologies, bugs, sécurité, performance.
- **Organisationnel** : planning, retard, organisation.
- **Humain** : communication, motivation, disponibilité (y compris la mienne si je travaille seul).

**Échelles** :
- Impact : 1 insignifiant, 2 léger, 3 modéré, 4 majeur, 5 lourd.
- Probabilité : 1 rare, 2 peu probable, 3 possible, 4 probable, 5 très probable.

**Tableau** : **N° | Risque | Description | Type | Impact brut | Probabilité brute | Mitigation | Impact résiduel | Probabilité résiduelle**

- La **mitigation** est l'action concrète qui réduit l'impact ou la probabilité.
- Le **risque résiduel** est ce qui reste après la mitigation.
- Classer par gravité (impact × probabilité) et traiter d'abord les plus graves.

Risques à toujours envisager : besoin du client mal compris, bugs non testés, technologie trop complexe ou nouvelle, failles de sécurité, lenteur sous la charge, retard.

Revoir les risques à chaque fin d'itération si la situation a changé.
