# Step-by-Step Distillation
- IN PROGRESS -

This is my attempt at re-implementing the [Step-by-Step Distillation](https://arxiv.org/abs/2305.02301) method and evaluating its performance against various baseline approaches. My goal is to test its effectiveness and explore how it compares to traditional methods.

# Workflow Overview
1. Dataset Preparation
   - Use the Salesforce/cos_e dataset from Hugging Face.
   - Modify it to contain only the input and label columns for consistency.

2. Teacher Model & Rationale Generation
   - The original paper used PaLM as the teacher model; I am replacing it with Qwen.
   - Generate rationales for the dataset using few-shot prompting (10-shot, as in the original paper).

3. Student Model Training
   - I use T5-small as the student model, while the original paper used variants like T5-medium.
   - Apply the Step-by-Step Distillation method to train it.

4. Performance Evaluation
   - Compare Step-by-Step Distillation against baseline approaches, including:  
     - Standard fine-tuning using T5-small.
     - Few-shot CoT (Chain-of-Thought) inference using Qwen.

This project is a work in progress, and I’ve made some modifications to the original approach to experiment with different aspects of the distillation process.

