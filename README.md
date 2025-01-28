# Dataset and ground truth for hypotheses and claims extraction benchmark
 
## Data (directory ./data)
### Ground Truth (directory ./data/ground_truth)
#### Contains the actual ground truth dataset constructed for the benchmark. There are two csv files for each task (claims extraction and hypotheses extraction). Each files contains the following columns:model_name - The name of the AI model used (e.g., "o1-mini")
- temperature - The temperature setting used for the model (e.g., 1.0)
- prompt_id - Identifier for the prompt used (e.g., "prompt-8", prompts available at ./Prompts)
- paper_id - Unique identifier for the academic paper (e.g., "79VGGIEY")
- title - The title of the academic paper
- url - URL of the paper
- open_access - whether the paper 
- claim/hypothesis - An extracted claim/hypothesis or finding from the paper
- explanation - A brief explanation of why this statement is considered a claim or hypothesis

### Inference (directory ./data/inference)

- Contains inference outputs for different models for the two tasks

## Dataset

### Statistics:

- Below are the dataset statistics:

| Metric                     | Claims   | Hypotheses   |
|----------------------------|----------|--------------|
| **Total unique papers**    | 145      | 145          |
| **Fraction claims/hypotheses** | 95.9%    | 35.2%        |
| **Mean per paper**         | 6.7      | 3.1          |
| **Median per paper**       | 6.0      | 2.0          |
| **Max per paper**          | 25       | 15           |


### Pdf/Text data:
- Note that some articles are paywalled. Hence we have not released the pdf or text of these articles, only their urls.
- When an article is open access, we have included the open access url, and in this case ./data/paper_urls.csv contains open_access = True column/flag.
- You need an institutional login to download the pdfs of these articles.

### Benchmark:

- We suggest weighted F-1 score as the single most useful metric for comparison across models. It averages the precision, recall for each paper and weighs them according to the number of gold extracted texts per paper.

#### Task - Claim Extraction

| Model          | Macro         |               |       | Micro         |               |       | Weighted      |               |       |
|----------------|---------------|---------------|-------|---------------|---------------|-------|---------------|---------------|-------|
|                | P             | R             | F1    | P             | R             | F1    | P             | R             | F1    |
|----------------|---------------|---------------|-------|---------------|---------------|-------|---------------|---------------|-------|
| gpt-4o         | 0.47          | 0.39          | 0.40  | 0.44          | 0.34          | 0.38  | 0.50          | 0.34          | **0.38** |
| gpt-4o-mini    | 0.36          | 0.37          | 0.34  | 0.35          | 0.32          | 0.34  | 0.40          | 0.32          | **0.34** |
| llama3.3_70b   | 0.33          | 0.33          | 0.31  | 0.32          | 0.30          | 0.31  | 0.39          | 0.30          | **0.32** |
| llama3.1_8b    | 0.18          | 0.24          | 0.19  | 0.15          | 0.24          | 0.19  | 0.22          | 0.24          | **0.21** |
| qwen2.5_7b     | 0.26          | 0.19          | 0.20  | 0.28          | 0.16          | 0.21  | 0.29          | 0.16          | **0.20** |
| mistral_7b     | 0.20          | 0.17          | 0.16  | 0.17          | 0.15          | 0.16  | 0.24          | 0.15          | **0.17** |


#### Task - Hypothesis Extraction

| Model          | Macro         |               |       | Micro         |               |       | Weighted      |               |       |
|----------------|---------------|---------------|-------|---------------|---------------|-------|---------------|---------------|-------|
|                | P             | R             | F1    | P             | R             | F1    | P             | R             | F1    |
|----------------|---------------|---------------|-------|---------------|---------------|-------|---------------|---------------|-------|
| gpt-4o         | 0.34          | 0.35          | 0.33  | 0.39          | 0.42          | 0.41  | 0.48          | 0.42          | **0.43** |
| llama3.3_70b   | 0.30          | 0.40          | 0.31  | 0.25          | 0.43          | 0.31  | 0.41          | 0.43          | **0.40** |
| gpt-4o-mini    | 0.21          | 0.40          | 0.25  | 0.20          | 0.46          | 0.28  | 0.38          | 0.46          | **0.37** |
| qwen2.5_7b     | 0.19          | 0.21          | 0.19  | 0.19          | 0.27          | 0.23  | 0.29          | 0.27          | **0.27** |
| mistral_7b     | 0.19          | 0.34          | 0.21  | 0.15          | 0.40          | 0.21  | 0.31          | 0.40          | **0.28** |
| llama3.1_8b    | 0.12          | 0.32          | 0.16  | 0.01          | 0.41          | 0.16  | 0.23          | 0.41          | **0.27** |
