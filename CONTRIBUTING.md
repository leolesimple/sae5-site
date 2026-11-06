# Contribuer à sae5-site

Merci de contribuer. Ce document décrit le workflow à suivre pour que le dépôt reste propre et lisible.

## Principes

- `main` est protégée : aucun push direct, tout passe par une Pull Request (PR).
- Une PR = un sujet. Petites PR, faciles à relire.
- Les commits et les titres de PR suivent la convention **Conventional Commits** (obligatoire).

## Workflow

1. Récupérer la dernière version de `main` :
   ```bash
   git switch main && git pull
   ```
2. Créer une branche depuis `main` (voir nommage ci-dessous).
3. Commiter régulièrement, en respectant les Conventional Commits.
4. Pousser la branche et ouvrir une PR vers `main`.
5. Attendre que les checks passent (titre de PR conforme, conversations résolues).
6. Merge en **squash** : le titre de la PR devient le message de commit sur `main`.
7. La branche est supprimée automatiquement après le merge.

## Nommage des branches

Format : `type/description-courte-en-kebab-case`

Exemples : `feat/page-horaires`, `fix/bug-menu-mobile`, `docs/contributing`, `chore/setup-eslint`

## Conventional Commits

Format :

```
type(scope optionnel): description à l'impératif, en minuscules, sans point final

corps optionnel

footer optionnel (ex: BREAKING CHANGE: ..., Closes #12)
```

| Type       | Usage                                                   |
| ---------- | ------------------------------------------------------- |
| `feat`     | Nouvelle fonctionnalité                                 |
| `fix`      | Correction de bug                                       |
| `docs`     | Documentation uniquement                                |
| `style`    | Formatage, sans changement de logique (espaces, CSS pur)|
| `refactor` | Réécriture sans changement de comportement              |
| `perf`     | Amélioration de performance                             |
| `test`     | Ajout ou correction de tests                            |
| `build`    | Build, dépendances                                      |
| `ci`       | Intégration continue, workflows GitHub                  |
| `chore`    | Tâches diverses sans impact sur le code applicatif      |
| `revert`   | Annulation d'un commit précédent                        |

Exemples :

```
feat(horaires): ajouter l'affichage des prochains passages
fix(menu): corriger la fermeture du menu mobile
docs: mettre à jour le guide de contribution
feat!: refondre la structure des données
```

Un `!` après le type ou le scope (ou un footer `BREAKING CHANGE:`) signale un changement cassant.

Le titre de chaque PR est vérifié automatiquement par le workflow `.github/workflows/pr-title.yml`. Une PR dont le titre ne respecte pas le format ne peut pas être mergée.

## Pull Requests

- Remplir le template de PR.
- Lier les issues concernées (`Closes #12`).
- Vérifier soi-même le diff avant de demander une review.
- Répondre à chaque commentaire, puis marquer la conversation comme résolue.
- Garder la PR à jour avec `main` si elle entre en conflit.

## Issues

Utiliser les templates (bug, fonctionnalité). Un bon ticket contient le contexte, le résultat attendu et, pour un bug, les étapes de reproduction.

## Style de code

Les conventions de base sont dans `.editorconfig`. Configure ton éditeur pour qu'il le prenne en compte.

## Code de conduite

En contribuant, tu acceptes de respecter le [Code de conduite](CODE_OF_CONDUCT.md).
