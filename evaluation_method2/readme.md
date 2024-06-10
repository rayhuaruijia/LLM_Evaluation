Introduction:
This is the second evaluation metric we designed. Our goal is to evaluate the readabiity, accuracy, and relevance of explanaed math problems of proofs and non-proofs. We first provide models with 60 challenging Math questions custom made by us. Then we provide them with a specific prompt in order to make it easier to collect output. Then we compare their accuracy scores.

Files:


This is the dataset we chose to use. It contains 60 challenging Math questions of proofs and non proofs



Notes:
The way we collect results from models' answer to those 600 questions depends on the models themselves. We made a prompt for the language model to follow. So basically we provide the questions, the available options along with the correct answers to the model. We tell the model to first answer the question and give a reasonable explanation without looking at the correct answer. Then we tell the model to look at the answer and tell us if he answers the question and explanation correctly or not. We tell the language models to answer in a strict json format to make it easy for us to collect results. In this experiment, we didn’t include falcon7B because it not only fails to follow the prompt, but it also fails to answer any of the questions correctly.

This is an example:

Prompt:
Solve this math problem: {Problem}. First, try to solve the problem without looking at the options and correct answer and provide your initial answer and explanation. Now, respond with a JSON object that includes your answer, explanation, and your self-evaluation of whether your answer and explanation match the correct answer from available options and the rationale

Format your response strictly as follows: {My Answer: "<answer>", Explanation: "<explanation>", Answer Correct: "<yes/no>", "Explanation Correct": "<yes/no>"}

Gemini’s answer:
{"My Answer": "$0.40", "Explanation": "If Arthur and David submit separate orders, they will not get the discount because each order will be less than 100 copies. Each would pay 80 $0.02 = $1.60, or a total of $3.20 for both orders. If they submit a single order of 160 copies, they get a 25% discount on the total cost. The discount is 0.25 $3.20 = $0.80. Therefore, each person saves $0.80 / 2 = $0.40.", "Answer Correct": "yes", "Explanation Correct": "yes"}
