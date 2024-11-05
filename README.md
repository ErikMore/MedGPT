
![🚑MedGPT](https://github.com/user-attachments/assets/16c23235-0af4-47b2-9e05-de5c793f2fdd)


This project demonstrates how to fine-tune a Large Language Model (LLM) using the Hugging Face, Transformers library and additional libraries. We’ll be fine-tuning the LLaMA model, making use of quantization techniques for memory efficiency and training speed.

**Table of Contents**
1. Requirements
2. Installation
3. Model and Tokenizer Loading
4. Training Arguments
5. Fine-Tuning
6. Inference
7. Troubleshooting

**Requirements**<br />
Python 3.10+ \
Libraries 
- `PyTorch`: deepcore learning framework. 
- `accelerate`: Hugging Face library used for GPU management.
- `peft`: Parameter-Efficient Fine Tuning is needed for reducing memory usage and speeding up training.
- `bitsandbytes`: Resource manager for reducing bits in order to minimize size in memory storage.
- `transformers`: Hugging Face library used for loading, managing, and training the LLM.
- `trl`: Training Reinforcement Learning from Hugging Face manages datasets and tokenization.
- `huggingface_hub`: Hugging Face API used for connecting to datasets.
  
*Optional*:  Set up environment in Google Colab to save space in hard drive.

**Installation**<br />
Set up the environment, and install the necessary libraries.
![Installation](https://github.com/user-attachments/assets/4d94d2d6-ff9e-4285-af50-6b6a873a98bd)

**Model and Tokenizer Loading**<br />
Use the `AutoModelForCausalLM` and `AutoTokenizer` to load the pre-trained LLaMA model and tokenizer. We employ a 4-bit quantization to reduce memory usage during training.
![LoadModel](https://github.com/user-attachments/assets/225d9d8d-3db2-42c2-84ee-4f76f5b08549)

The tokenizer is also loaded with `AutoTokenizer`:
![Tokenizer](https://github.com/user-attachments/assets/04dc7a85-31c2-4511-ac79-bced70895fa8)

**Training Arguments**<br />
Define training arguments using `TrainingArguments`. Here, we set a small batch size and a limited number of training steps for demonstration purposes.
![Training Arguments](https://github.com/user-attachments/assets/c51046e0-3225-4a64-9bb7-212eea831478)

**Fine-Tuning**<br />
Create an `SFTTrainer` (Supervised Fine-Tuning Trainer) to manage the training process. We configure it with `LoRA` (Low-Rank Adaptation) to allow efficient parameter updates.
![FineTuning](https://github.com/user-attachments/assets/b435898c-2a90-4543-8e28-b75e78f93c67)

**Start Training**<br />
![InitializeTraining](https://github.com/user-attachments/assets/043472a0-972a-4282-980a-87cd6941fdc9)

**Inference**<br />
After training, use the model to generate responses to user prompts.
![Inference](https://github.com/user-attachments/assets/6c3e367e-311f-4e3d-aa16-345dff342a20)

**Troubleshooting**<br />
- Xformers Warning: If xformers is not installed, use pip install xformers to enable memory-efficient attention.
- Deprecation Warnings: Keep libraries updated as some functionalities might be deprecated.
