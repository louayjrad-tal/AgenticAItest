# Stratégie d’intégration cible – Design System & UI

## 1. Objectifs

Cette stratégie définit comment le frontend intègre la librairie UI `@company/design-system`, gère le theming et pilote le versioning de la dépendance.
Elle vise à garantir une intégration cohérente, testable et facilement maintenable dans le temps.

---

## 2. Librairie UI cible : `@company/design-system`

### 2.1. Rôle de la librairie

- `@company/design-system` est **la source unique de vérité** pour les composants UI (boutons, champs de formulaire, layout, etc.).
- Le code applicatif doit **toujours privilégier les composants du Design System** plutôt que des composants maison, sauf cas très spécifiques.
- Toute évolution d’UX/UI (structure, tokens, comportements) doit être gérée **en priorité dans la librairie**, puis consommée par l’application.

### 2.2. Point d’entrée dans l’application

L’intégration se fait via un provider applicatif unique :

- Fichier : `src/design-system/DesignSystemProvider.tsx`
- Utilisation dans l’application :