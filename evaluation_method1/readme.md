# Methodology 1

### Introduction:
This is the first evaluation metric we designed. Our goal is to compare the accuracy score of each model by categories. We first provide models with 600 challenging Math questions from different categories to solve it. Then we provide them with a specific prompt in order to make it easier to collect output. Then we compare their accuracy score by different categories.

### Files:
#### challenge_test.json

 This is the dataset we chose to use. It contains 600 challenging Math questions from different categories. It has general question, geometry questions, physics calculations, Gain, probability, and others. We provide language models with these questions, and they have to give us their answers and their explanations. After that we evaluate not only their accuracy, but also their explanations.

#### gpt_eval_publicDS.ipynb
This file evaluates GPT3.5 Turbo's performance on answering 600 challenging question. At the end, we calculate and visualize its overall accuracy scores and explanation accuracy scores by the categories of the questions.

#### gemini_eval_publicDS.ipynb
This file evaluates Gemini 1.5 Flash's performance on answering 600 challenging question. At the end, we calculate and visualize its overall accuracy scores and explanation accuracy scores by the categories of the questions.


#### Folder: Human Evalution
This folder contains the dataset that contains 15 selected challenging math questions along with each model's (GPT3.5, Gemini1.5, Falcon7b) response to each question. This part is primarily used for human evalution.


### Notes:
The way we collect results from models' answer to those 600 questions depends on the models themselves. We made a prompt for the language model to follow. So basically we provide the questions, the available options along with the correct answers to the model. We tell the model to first answer the question and give a reasonable explanation without looking at the correct answer. Then we tell the model to look at the answer and tell us if he answers the question and explanation correctly or not. We tell the language models to answer in a strict json format to make it easy for us to collect results. In this experiment, we didn’t include falcon7B because it not only fails to follow the prompt, but it also fails to answer any of the questions correctly.

This is an example:

#### Prompt:
Solve this math problem: {Problem}. 
First, try to solve the problem without looking at the options and correct answer and provide your initial answer and explanation.
Now, respond with a JSON object that includes your answer, explanation, and your self-evaluation of whether your answer and explanation match the correct answer from available options and the rationale

Format your response strictly as follows: {My Answer: "\<answer>", Explanation: "\<explanation>", Answer Correct: "<yes/no>", "Explanation Correct": "<yes/no>"}


#### Gemini’s answer:
{"My Answer": "$0.40", "Explanation": "If Arthur and David submit separate orders, they will not get the discount because each order will be less than 100 copies. Each would pay 80 $0.02 = $1.60, or a total of $3.20 for both orders. If they submit a single order of 160 copies, they get a 25% discount on the total cost. The discount is 0.25 $3.20 = $0.80. Therefore, each person saves $0.80 / 2 = $0.40.", "Answer Correct": "yes", "Explanation Correct": "yes"}
