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

