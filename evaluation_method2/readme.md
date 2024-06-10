Introduction:
This is the second evaluation metric we designed. Our goal is to evaluate the readabiity, accuracy, and relevance of explanaed math problems of proofs and non-proofs. We first provide models with 60 challenging Math questions custom made by us. Then we provide them with a specific prompt in order to make it easier to collect output. Then we compare their accuracy scores.

Files:


This is the dataset we chose to use. It contains 60 challenging Math questions of proofs and non proofs



Notes:
The way we collect results from models' answer to those 600 questions depends on the models themselves. We made a prompt for the language model to follow. So basically we provide the questions, the available options along with the correct answers to the model. We tell the model to first answer the question and give a reasonable explanation without looking at the correct answer. Then we tell the model to look at the answer and tell us if he answers the question and explanation correctly or not. We tell the language models to answer in a strict json format to make it easy for us to collect results. In this experiment, we didn’t include falcon7B because it not only fails to follow the prompt, but it also fails to answer any of the questions correctly.

This is an example:

Prompt:
If |2x−7|≤8 what is the greatest possible value of |x−7|? (without calculator) show work. Format your response strictly as follows: {My Answer: "<answer>", Explanation: "<explanation>"]

Gemini’s answer:
We know that |2x - 7| ≤ 8. This means that -8 ≤ 2x - 7 ≤ 8.  To find the greatest possible value of |x - 7|, we need to maximize the value of |x - 7|. Let's consider the two inequalities separately:\n\n1. -8 ≤ 2x - 7\n   Adding 7 to both sides gives: -1 ≤ 2x. \n   Dividing both sides by 2 gives: -1/2 ≤ x. \n\n2. 2x - 7 ≤ 8\n   Adding 7 to both sides gives: 2x ≤ 15.\n   Dividing both sides by 2 gives: x ≤ 15/2.\n\nCombining these inequalities, we have -1/2 ≤ x ≤ 15/2.\n\nTo maximize |x - 7|, we want to find the largest possible value of x. The largest possible value of x within this range is x = 15/2.\n\nTherefore, the greatest possible value of |x - 7| is |15/2 - 7| = |1/2| = 1/2. However, this is not the answer as we want the greatest possible value of |x-7|.  We want to make |x-7| as big as possible.  Therefore, we should make x as small as possible, but still satisfy the original inequality.  We see that x=-1/2 satisfies the original inequality.  Plugging this into |x-7| we have |-1/2 - 7| = 15/2.  Therefore, the greatest possible value of |x - 7| is 15/2.
