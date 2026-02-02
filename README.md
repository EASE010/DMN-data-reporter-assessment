# DMN-data-reporter-assessment
_This document was created by Levi Jiang in February 2026 for the exclusive reference of The Dallas Morning News' data team recruitment process._

## Task 1

## Task 2
### Steps to assess the dataset’s strength and weaknesses
1. I will get an overall understanding of the dataset first. I will read the column definitions carefully, and pull out some rows to see if they align with the definition, and whether each row reflects an individual contribution, credit, or other transaction type and how amounts should be interpreted. I will also try to download avaliable files to see what fomat is used here. I aim to understand what each record represents and how reliable the fields are for analysis.
2. The second step is to assess completeness and coverage by checking date ranges, records by candidate, and the prevalence of missing values in key fields such as amount, donor name, business name, and address. This will identify temporal gaps, underreported candidates, or structural bias in the data.
3. Then we can evaluate data quality in some columns like contribution amounts, dates, and contributor identifiers, looking for formatting issues, missing values or inconsistencies. Also, since the dataset includes geo info, I will check how complete and accurate it is to determine whether location-based analysis can be applied here.
4. Clarify the dataset’s scope and limitations, such as whether it includes only itemized contributions, how non-cash transactions are recorded, and what reporting thresholds may affect the coverage.

### Strength
1. **Data Transparency and Credibility**: In each record, there's a direct link to original PDFs so reporters can pull context and verify the data easily. Readers also can benefit from the accessbility of primary sources.
2. **Geographic Info**: With the address and geo_location info, we are able to analyze the money a candidate spent on local or outstate business. 
3. **Transaction-level Detail**: Each row appears to represent an individual contribution or transaction with amount, time, location, etc. We are able to track the money over time, aggregate by candidate, identify any time or location-based patterns and compare them. This is stronger than summary-level reports.


### Weakness
1. **Formatting Problem**: In the Amount column, the amount should be numeric instead of text. This will cost us some time to clean them up and double check the numbers and potential calculation errors.
2. **Name Spelling Inconsistency**: For example, for candidate William Roth, his name is spelt in 3 different ways in this dataset: Bill Roth, William Roth and WILLIAM ROTH. This might cause double counting or grouping in our analysis. We have to check all of the candidates and do some manual standardizations.
3. **Lack of Details**: After carefully reviewing several campaign finance reports, I noticed that the dataset still lack certain details. For instance, the reports clearly disclose the purpose of each expenditure, the data tables only list a vague term like “Expenditure.” If we only look at the dataset, we cannot tell whether a candidate spent $1,000 at Walmart for lobbying or simply buying office supplies.


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
