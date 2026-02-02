# DMN-data-reporter-assessment
_This document was created by Levi Jiang in February 2026 for the exclusive reference of The Dallas Morning News' data team recruitment process._

## Task 1

## Task 2

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
### Breakdown of the files:
```
README.md
```
I will include a clear README explaining the story context, folder structure, data sources, and where to find the exact numbers used in the article for fact-checking

```
├── 01_raw_data/
│   ├── source_original.csv
│   ├── data_dictionary.md
│   └── sources_notes.md
```
This folder contains the original data files, a short data dictionary explaning every variable, and a source note documenting where each dataset came from, access dates, etc.

```
├── 02_analysis/
│   ├── 01_data_cleaning.ipynb
│   └── 02_calculations_results.ipynb
```
So for people with no coding experience, running a whole Python project can be very tricky. Instead, I will choose to do my data analysis works in Jupyter notebook. This is where I can combine narrative + code together in a step-by-step logic, and show my editor the visible output without running anything. I prefer to split data cleaning and computation into two separate files to avoid the issue of a single file becoming too large to pinpoint a specific step. Within each file, I will write explanations before and after major steps, describing in plain language what is going on and what each output represents. This allows editors to follow the logic without reading the code.

```
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
```
Here, `cleaned_data/` is the folder of all the datasets after processing and explaining notes. `story_numbers_notes.md` is where I track down all the numbers that are used in the story and where they came from, so editors can double check if they appears in the right place and if they're accurate. `charts_preview/` has the static PNGs or screenshots of our data viz so editors can quickly review them. With the `chart_notes.md`, graphics team can rebuild these charts.

```
├── 04_multimedia_assets/
│   ├── photos/
│   ├── graphics/
│   └── videos/
```
This is where we store all multimedia assets except the data viz. Editors can review visual elements here and verify information such as credits and captions.

```
methodology.md
```
If this is a large and complex project, I will also add a methodology file for our assumptions, cleaning decisions, calculations, etc.
