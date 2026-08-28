# Music Data Preparation Pipeline

## Artist Page Lookup — Full Development Version

This repository contains the original, full development version of a music data preparation project.

A **shortened and polished presentation** of the same project is available here:

**[Music Data Preparation Pipeline - Polished Version](https://github.com/ed-cybros/Music-Data-Preparation-Pipeline-Python-Only---Polished-Version)**

## About the Project

The project is an early attempt to work through a complete data preparation process using music data as the domain context.

The pipeline starts with a synthetically corrupted music dataset and works through:

- Data inspection
- Data cleaning
- Data transformation
- Data validation
- Data structuring
- Data export

The final objective is to produce a simplified artist-level lookup dataset containing:

- Average track popularity
- Average BPM
- Most frequent genre

## Tech Stack
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![JSON](https://img.shields.io/badge/json-563d7c?style=for-the-badge&logo=json&logoColor=white)
![Git](https://img.shields.io/badge/git-%23F05033.svg?style=for-the-badge&logo=git&logoColor=white)

The project is implemented using **Python only** to practice core data cleaning, transformation, validation, and data-structuring techniques without relying on specialized data-processing libraries.

**Exception:** `pandas` was used for one optional internal investigation, separate from the main pipeline, as a personal comparison of how a library designed for data analysis changes the efficiency and practicality of working with tabular data. I wanted to experience the difference between manipulating tabular data with core Python and using a tool specifically designed for that type of work.

## Why This Project

The fundamental purpose of the project is practical learning through implementation.

Rather than practicing individual data-cleaning or transformation techniques in isolation, I wanted to work through a complete process in which decisions made at one stage affect later stages of the pipeline.

The project also represents the beginning of applying my data-preparation studies to a domain that I intend to explore further: **music data**.

## Dataset

The source dataset is the **[Spotify - All Time Top 2000s Mega Dataset](https://www.kaggle.com/datasets/iamsumat/spotify-top-2000s-mega-dataset?resource=download)**, used in a synthetically corrupted form for data-cleaning practice.

The corruption introduces several data-quality problems that require investigation before the data can be used reliably for the intended output.

## Development Process

The notebook documents the development process rather than only presenting the resulting implementation.

This includes:

- Initial approaches
- Data inspection
- Intermediate transformations
- Failed or revised approaches
- Debugging
- Repeated validation
- Comparisons with the original dataset
- Reasoning behind individual data-cleaning decisions

Some sections therefore contain repeated analysis or approaches that were later replaced.

This is intentional. The purpose of this version is to preserve the development process and make the reasoning behind the final approach visible.

## Data Preparation Approach

The general principle used throughout the project was:

- **Preserve information where possible and modify or remove it only when there is sufficient justification.**

This required more than applying predefined transformations.

Potential problems were investigated in relation to:

- The original data
- The intended output
- Relationships between fields
- The meaning of individual values
- The consequences of modifying or removing records

## Areas of Investigation

### Duplicate Records

Candidate duplicate records were identified and investigated rather than automatically removed.

The differences between apparently equivalent records were examined to determine whether they represented actual duplication, meaningful variation, or an issue in the source data.

### Missing Values

Missing values were considered according to their role in the final calculations.

Where possible, valid information in the same record was preserved rather than removing the entire record because of one missing value.

### Value Normalization

Names and other relevant values were normalized where necessary to support consistent grouping and comparison.

The effects of normalization were also reviewed to avoid unnecessarily modifying useful information.

### Domain-Specific Values

Some values required consideration of the music domain before being treated as incorrect.

BPM is one example. An unusually high or low BPM does not necessarily represent an invalid value because different tempo interpretations can exist for the same musical material.

This required distinguishing between:

- Unusual values
- Incorrect values
- Different representations
- Values that should simply be preserved

## Validation

Validation became an important part of the development process.

Intermediate and final results were repeatedly inspected to determine whether:

- Expected transformations had occurred
- Records had been unintentionally lost
- Calculations were plausible
- The final structure contained the intended information

Several issues in earlier approaches became visible only through this repeated review.

## Output

The final pipeline produces an artist-level lookup structure containing:

```text
Artist
├── Most frequent genre
├── Average BPM
└── Average popularity
```

The resulting structure is exported as JSON.

JSON was selected because the resulting data is hierarchical.

## Challenges and Lessons

One of the main lessons from the project was that the difficulty of a data-preparation task does not necessarily come from writing the code.

In several cases, the more difficult part was deciding what the data represented and determining what should happen to it.

A technically correct transformation can still produce an undesirable result if it is applied without sufficient consideration of the data and its intended use.

The project also reinforced the importance of iterative inspection and validation. Several problems were revealed only after examining intermediate results and comparing them with the source data.

Working with music data additionally demonstrated that domain knowledge can influence data-cleaning decisions. Values that appear unusual from a purely numerical perspective are not necessarily incorrect.

## Project Summary

This project provided practical experience with a complete data preparation process applied to music data.

Starting from a synthetically corrupted dataset, I worked through data inspection, cleaning, transformation, validation, and structuring with a specific downstream objective in mind.

The main focus was not on producing a complex final dataset, but on developing the ability to reason about the information contained within the data and make justified decisions about what should be preserved, transformed, excluded, or left unchanged.

The full development process also exposed several areas where a more experienced approach could become more efficient, particularly in defining validation criteria and reducing unnecessary iterations.

For that reason, the project serves both as a practical implementation and as documentation of how my understanding of data preparation developed while working through a concrete problem.

## Polished Version

A shortened and more structured presentation of the resulting approach is available here:

**[Music Data Preparation Pipeline - Polished Version](https://github.com/ed-cybros/Music-Data-Preparation-Pipeline-Python-Only---Polished-Version)**
