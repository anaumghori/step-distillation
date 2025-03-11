# Step-by-Step Distillation
This is my attempt at re-implementing the [Step-by-Step Distillation](https://arxiv.org/abs/2305.02301) method with a goal to test its effectiveness.  
> Distilling step-by-step, a new mechanism that (a) trains smaller models that outperform LLMs, and (b) achieves so by leveraging less training data needed by finetuning or distillation. The method extracts LLM rationales as additional supervision for training small models within a multi-task framework.


## Workflow Overview  
1. **Model Selection:** Replaced the original paper's teacher model 'PaLM', with Qwen, and used T5-small as the student model.  

2. **Dataset Preparation:** Modified the Salesforce/cos_e dataset from Hugging Face to include only the 'input' and 'label' columns.  

3. **Rationale Generation:** Applied 10-shot prompting to generate rationales, but restricted this process to the train split.  

4. **Student Model Training:** Trained the T5-small student model using the Step-by-Step Distillation method.  

5. **Performance Evaluation:** Evaluated Step-by-Step Distillation against baseline approaches:  
   - Standard fine-tuning with T5-small.  
   - Few-shot Chain-of-Thought (CoT) inference using Qwen.  

## Results  

| Method                     | Data Used | Accuracy |
|----------------------------|------------|-----------|
| **Standard Fine-tuning**     | 100%        | 41.20%    |
| **Step-by-Step Distillation**| ~74%     | 52.60%    |

Using the Step-by-Step Distillation method, I achieved **52.60% accuracy** while utilizing **26% less data** compared to standard fine-tuning, which achieved **41.20% accuracy**. This demonstrates that the distillation method not only improves performance but also achieves better results with reduced data.

