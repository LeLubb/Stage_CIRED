# Stage_CIRED

Ce dépôt contient le chapitre LaTeX sur l'acceptabilité des politiques de redistribution internationale. L'objectif du workflow est de permettre une relecture précise dans GitHub, avec commentaires ligne par ligne, réponses, corrections traçables et conservation complète de l'historique.

## Organisation du chapitre

```text
chapter/
├── main.tex
├── sections/
│   ├── 01_introduction.tex
│   ├── 02_deep_values_and_universalism.tex
│   ├── 03_foreign_aid.tex
│   ├── 04_international_taxation.tex
│   ├── 05_global_governance.tex
│   ├── 06_international_climate_policy.tex
│   ├── 07_willingness_to_contribute.tex
│   ├── 08_explaining_lack_of_prominence.tex
│   └── 09_conclusion.tex
├── features/
│   └── packages.tex
├── references.bib
├── draft_1.tex
└── draft_2/
    ├── intro_draft_2.tex
    └── section_2_draft_2.tex
```

`chapter/main.tex` est le point d'entrée à compiler. Les neuf fichiers de `chapter/sections/` sont les fichiers de travail courants et facilitent les commentaires ciblés dans une pull request.

`draft_1.tex` et `draft_2/` sont conservés comme sources historiques. Ils ne doivent pas servir de base à de nouveaux dossiers de version.

## Compiler

Depuis la racine du dépôt :

```bash
latexmk -pdf -interaction=nonstopmode -halt-on-error -file-line-error \
  -outdir=chapter/build chapter/main.tex
```

Le PDF est produit dans `chapter/build/main.pdf`. Les fichiers temporaires de compilation sont ignorés par Git.

## Workflow de collaboration

```text
branche de révision
→ modifications
→ commits
→ push
→ pull request
→ commentaires ligne par ligne
→ réponses et corrections
→ résolution des discussions
→ fusion après validation
```

1. Mettre `main` à jour, puis créer une branche dédiée, par exemple `review/revise-foreign-aid`.
2. Modifier de préférence un ou quelques fichiers dans `chapter/sections/`.
3. Créer des commits courts et cohérents, sans mélanger plusieurs sujets.
4. Pousser la branche et ouvrir une pull request vers `main`, d'abord en brouillon si le texte n'est pas prêt.
5. Relire l'onglet **Files changed** et commenter les lignes concernées avec le bouton `+`.
6. Répondre dans chaque discussion. Les corrections sont ajoutées sur la même branche, puis poussées : la pull request se met à jour automatiquement.
7. Résoudre une discussion uniquement lorsque le commentaire a reçu une réponse et que la correction est acceptée.
8. Passer la pull request en **Ready for review**, puis fusionner seulement après validation et compilation.

Ne pas pousser directement sur `main` et ne pas utiliser de push forcé.

## Conserver les versions

Git conserve chaque état dans les commits et les pull requests. Pour marquer une version importante après validation, utiliser un tag annoté, par exemple `chapter-v1.0`. Il n'est donc pas nécessaire de créer un dossier complet par version future.

- **Commit** : étape de travail retrouvable.
- **Branche** : proposition de révision isolée.
- **Pull request** : revue, commentaires, réponses et décision de fusion.
- **Tag** : jalon stable ou version transmise.

## Intégration de `draft_2`

| Fichier de `draft_2` | Section modulaire | Confiance | Décision |
|---|---|---:|---|
| `intro_draft_2.tex` | `01_introduction.tex` | Élevée | Intégré |
| `section_2_draft_2.tex` | `02_deep_values_and_universalism.tex` | Élevée | Intégré ; section rendue numérotée dans le document complet |
| Aucun fichier fourni | Sections 03 à 09 | Aucune correspondance disponible | Contenu de `draft_1.tex` conservé |

Toute future correspondance incertaine doit être décrite dans la pull request et validée avant intégration.
