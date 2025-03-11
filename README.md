# Step-by-Step Distillation
This is my attempt at re-implementing the [Step-by-Step Distillation](https://arxiv.org/abs/2305.02301) method with a goal to test its effectiveness.  
> Distilling step-by-step, a new mechanism that (a) trains smaller models that outperform LLMs, and (b) achieves so by leveraging less training data needed by finetuning or distillation. The method extracts LLM rationales as additional supervision for training small models within a multi-task framework.


## Workflow Overview
1. **Dataset Preparation:** Use the Salesforce/cos_e dataset from Hugging Face and modify it to contain only the input and label columns.  

2. **Teacher Model & Rationale Generation:** In my approach, I replaced the original paper's teacher model, PaLM, with Qwen. Following the original paper's method, I used 10-shot prompting to generate rationales, but I applied this process only to the train split.
   
3. **Student Model Training:** I use T5-small as the student model, unlike the original paper which used T5-model variants. Next, train the model using Step-by-Step Distillation method.
   
4. **Performance Evaluation:** Compare Step-by-Step Distillation against baseline approaches, including:
   - Standard fine-tuning using T5-small.
   - Few-shot CoT (Chain-of-Thought) inference using Qwen.
