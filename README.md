# SPEED++
Data for our EMNLP-2024 paper "SPEED++: A Multilingual Event Extraction Framework for Epidemic Prediction and Preparedness"
--

Owing to Twitter's data-sharing policy, we can't publicly share the data. But you can fill out this [Google Form](https://forms.gle/G8hUwZaLqa2EYg596), and we can reach out to you with steps to procure the data.

## Data Statistics

Here are some high level statistics of our data categorized by language (* indicates length is measured based on number of characters):

| **Language** | **# Sentences** | **Average Length** | **# Event Mentions** | **# Arguments** |
|--------------|-----------------|--------------------|----------------------|-----------------|
| English      | 2,560           | 32.5               | 2,887                | 8,423           |
| Spanish      | 1,012           | 32.4               | 614                  | 1,485           |
| Japanese     | 716             | 30.0               | 627                  | 2,344           |
| Hindi        | 819             | 89.2*              | 549                  | 1,575           |

We also present the statistics for the train-dev-test splits of our data below:

| **Split** | **Disease** | **Language** | **# Sentences** | **# Event Mentions** |
|-----------|-------------|--------------|-----------------|----------------------|
| Train     | COVID       | English      | 1,601           | 1,746                |
| Dev       | COVID       | English      | 374             | 471                  |
| Test      | COVID       | Spanish      | 534             | 365                  |
| Test      | COVID       | Japanese     | 542             | 395                  |
| Test      | COVID       | Hindi        | 416             | 412                  |
| Test      | Mpox        | English      | 286             | 398                  |
| Test      | Zika/Dengue | English      | 299             | 272                  |
| Test      | Zika/Dengue | Spanish      | 478             | 249                  |
| Test      | Zika/Dengue | Japanese     | 277             | 154                  |
| Test      | Zika/Dengue | Hindi        | 300             | 215                  |

## Synthetic Data Generation

In our work, we utilize [CLaP](https://github.com/PlusLabNLP/CLaP) to create synthetic multilingual data by translating the original SPEED++ training English data. Specifically, we utilize Google Machine Translation (GMT) to translate the English data and utilize CLaP to create EE specific data. For subsequent training, we combine the synthetic data with our original data.

## Training/Evaluating Models

For all model training/evaluations, we utilize [TextEE](https://github.com/ej0cl6/TextEE). Majorly we export our data as a dataset in this repo, create specific configs, and train/evaluate the models using the TextEE scripts.
