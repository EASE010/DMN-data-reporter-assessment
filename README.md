# DMN-data-reporter-assessment
DMN data reporter assessment by Levi Jiang

## Task 3
Overall thinking: When working with a colleague from non-tech background, I'd like to make sure:
1. Raw data is in a separate folder and never overwritten so they can do fact check
2. Analysis is traceable step-by-step so it's clear to inditify any mistakes
3. If they are not familiar with running a code or a program, then they should be able to verify numbers without running code

I will use a GitHub repo to store all the files they need. Here's the structure:
```
Story/
│
├── README.md
│
├── 01_raw_data/
│   ├── source_original.csv
│   ├── data_dictionary.md
│   └── sources_notes.md
│
├── 02_analysis/
│   ├── 01_data_cleaning.ipynb
│   └── 02_calculations_results.ipynb
│
├── 03_outputs/
│   ├── cleaned_data/
│   │   ├── cleaned_dataset.csv
│   │   └── cleaned_data_notes.md
│   │
│   ├── story_numbers/
│   │   └── story_numbers_notes.md
│   │
│   └── charts_preview/
│       ├── chart_1.png
│       ├── chart_2.png
│       └── chart_notes.md
│
├── 04_multimedia_assets/
│   ├── photos/
│   ├── graphics/
│   └── videos/
│
└── methodology.md

```
