# AI-Depression-Response

## Motivation
This project was intended to show a better understanding of LLMs in how they respond to depressed users. There have been recent cases of people committing suicide with LLMs reinforcing their beliefs. They lacked the ability to support the user by offering help and instead took a more sycophantic approach. By diving in to the LLM, I hoped to gain some insight into how this all worked.

## Design
I generated 50 synthetic data pairs of safe and sycophantic responses to depressed prompts from Gemini 2.5 and I chose Qwen 2.5 as my model due to how light it is and that it is open-sourced. I then began my exploration with the goal to find in its weights and layers a relation to the way it responds to depressed prompts, generating vectors for each response, finding differences, and then applying said differences in reinforcing the model.

## Analysis
Using the model tokenizer and PCA, I was able to generate and then graph the vectors from my data, finding a clear divide in how the model mapped the responses. I then averaged these vectors and attempted to steer the model by influencing a layer. After finding some influence, I attempted to strengthen the model in response to depressed prompts, attempting to find the weakest layer, and applying a weighted vector in the more assisting direction. I was able to achieve desired results and make the model more robust at responding to depressed prompts. I was also able to gain insights in how the model architecture is influencable in its layers and how it maps different emotional responses in dimensional space.

## How to Run
A .ipynb is included with data and requirements. Please run
```
pip install -r requirements.txt
```
and then run each cell. Make sure the data is in the same folder as the .ipynb.