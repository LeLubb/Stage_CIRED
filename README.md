# Stage_CIRED

Les trois sections corrigées du `draft_1` se trouvent directement dans `chapter/` et portent le suffixe `draft_2`.

Les versions antérieures sont conservées dans `chapter/autres/`. Aucun contenu n'a été supprimé.

## Organisation du chapitre

```text
chapter/
├── intro_draft_2.tex
├── section_2_draft_2.tex
├── section_3_draft_2.tex
├── autres/
│   ├── draft_1.tex
│   └── sections/
│       ├── 01_introduction.tex
│       ├── 02_deep_values_and_universalism.tex
│       ├── 03_foreign_aid.tex
│       ├── 04_international_taxation.tex
│       ├── 05_global_governance.tex
│       ├── 06_international_climate_policy.tex
│       ├── 07_willingness_to_contribute.tex
│       ├── 08_explaining_lack_of_prominence.tex
│       └── 09_conclusion.tex
├── features/
│   └── packages.tex
├── chapter_intl_redistr_PLAN.md
├── main.tex
└── references.bib
```

`chapter/main.tex` conserve le document modulaire antérieur et appelle désormais les neuf sections archivées dans `chapter/autres/sections/`.
