---
title: "AI. Prompts"
description: ""
keywords: ""
lang: "en"
permalink: "ai-prompts"
aliases:
  - "ai-prompts"
---

# AI. Prompts

### Overview

A prompt contains any of the following elements:

* Instruction - a specific task or instruction you want the model to perform
* Context - external information or additional context that can steer the model to better responses
* Input Data - the input or question that we are interested to find a response for
* Output Indicator - the type or format of the output.

### General tips

* Start Simple. You can start with simple prompts and keep adding more elements and context as you aim for better results.
* The Instruction.[](https://www.promptingguide.ai/introduction/tips#the-instruction) You can design effective prompts for various simple tasks by using commands to instruct the model what you want to achieve, such as "Write", "Classify", "Summarize", "Translate", "Order", etc.
* Specificity.[](https://www.promptingguide.ai/introduction/tips#specificity) It's more important to have a good format and descriptive prompt. In fact, providing examples in the prompt is very effective to get desired output in specific formats. Be specific, descriptive and as detailed as possible about the desired context, outcome, length, format, style, etc
* Avoid Impreciseness. It's often better to be specific and direct. The analogy here is very similar to effective communication -- the more direct, the more effective the message gets across.
* To do or not to do?[](https://www.promptingguide.ai/introduction/tips#to-do-or-not-to-do) Another common tip when designing prompts is to avoid saying what not to do but say what to do instead.
* Put instructions at the beginning of the prompt and use ### or """ to separate the instruction and context
* Code Generation Specific - Use "leading words" to nudge the model toward a particular pattern

### LLM Settings

**Temperature** - In short, the lower the temperature, the more deterministic the results in the sense that the highest probable next token is always picked. Increasing temperature could lead to more randomness, which encourages more diverse or creative outputs. You are essentially increasing the weights of the other possible tokens. In terms of application, you might want to use a lower temperature value for tasks like fact-based QA to encourage more factual and concise responses. For poem generation or other creative tasks, it might be beneficial to increase the temperature value.

**Top P** - A sampling technique with temperature, called nucleus sampling, where you can control how deterministic the model is. If you are looking for exact and factual answers keep this low. If you are looking for more diverse responses, increase to a higher value. If you use Top P it means that only the tokens comprising the top\_p probability mass are considered for responses, so a low top\_p value selects the most confident responses. This means that a high top\_p value will enable the model to look at more possible words, including less likely ones, leading to more diverse outputs.

The general recommendation is to alter temperature or Top P but not both.

**Max Length** - You can manage the number of tokens the model generates by adjusting the max length. Specifying a max length helps you prevent long or irrelevant responses and control costs.

**Stop Sequences** - A stop sequence is a string that stops the model from generating tokens. Specifying stop sequences is another way to control the length and structure of the model's response. For example, you can tell the model to generate lists that have no more than 10 items by adding "11" as a stop sequence.

**Frequency Penalty** - The frequency penalty applies a penalty on the next token proportional to how many times that token already appeared in the response and prompt. The higher the frequency penalty, the less likely a word will appear again. This setting reduces the repetition of words in the model's response by giving tokens that appear more a higher penalty.

**Presence Penalty** - The presence penalty also applies a penalty on repeated tokens but, unlike the frequency penalty, the penalty is the same for all repeated tokens. A token that appears twice and a token that appears 10 times are penalized the same. This setting prevents the model from repeating phrases too often in its response. If you want the model to generate diverse or creative text, you might want to use a higher presence penalty. Or, if you need the model to stay focused, try using a lower presence penalty.

### Prompting Techniques

#### Zero-shot Prompting

Zero-shot prompting means that the prompt used to interact with the model won't contain examples or demonstrations.

#### Few-shot Prompting

This is awesome! // Negative  
This is bad! // Positive  
Wow that movie was rad! // Positive  
What a horrible show! //

*Negative*

#### Chain-of-Thought Prompting

chain-of-thought (CoT) prompting enables complex reasoning capabilities through intermediate reasoning steps. [https://www.promptingguide.ai/techniques/cot](https://www.promptingguide.ai/techniques/cot)

#### Meta Prompting

meta prompting and few-shot prompting are different in that it meta prompting focuses on a more structure-oriented approach as opposed to a content-driven approach which few-shot prompting emphasizes.

!["Meta Prompting"](https://www.promptingguide.ai/_next/image?url=%2F_next%2Fstatic%2Fmedia%2Fmeta-prompting.66b824be.png&w=1920&q=75)

#### Self-Consistency

Perhaps one of the more advanced techniques out there for prompt engineering is self-consistency. Proposed by [Wang et al. (2022)(opens in a new tab)](https://arxiv.org/abs/2203.11171), self-consistency aims "to replace the naive greedy decoding used in chain-of-thought prompting". The idea is to sample multiple, diverse reasoning paths through few-shot CoT, and use the generations to select the most consistent answer. This helps to boost the performance of CoT prompting on tasks involving arithmetic and commonsense reasoning.

#### Generate Knowledge Prompting

[https://www.promptingguide.ai/techniques/knowledge](https://www.promptingguide.ai/techniques/knowledge)

#### Prompt Chaining

[https://www.promptingguide.ai/techniques/prompt\_chaining](https://www.promptingguide.ai/techniques/prompt_chaining)

#### Tree of Thoughts

[https://www.promptingguide.ai/techniques/tot](https://www.promptingguide.ai/techniques/tot)

#### Retrieval Augmented Generation

[https://www.promptingguide.ai/techniques/rag](https://www.promptingguide.ai/techniques/rag)

#### Automatic Reasoning and Tool-use

[https://www.promptingguide.ai/techniques/art](https://www.promptingguide.ai/techniques/art)

#### Automatic Prompt Engineer

[https://www.promptingguide.ai/techniques/ape](https://www.promptingguide.ai/techniques/ape)

#### Active-Prompt

[https://www.promptingguide.ai/techniques/activeprompt](https://www.promptingguide.ai/techniques/activeprompt)

#### Directional Stimulus Prompting

[https://www.promptingguide.ai/techniques/dsp](https://www.promptingguide.ai/techniques/dsp)

#### Program-Aided Language Models

[https://www.promptingguide.ai/techniques/pal](https://www.promptingguide.ai/techniques/pal)

#### ReAct

[https://www.promptingguide.ai/ru/techniques/react](https://www.promptingguide.ai/ru/techniques/react)

#### Reflexion

[https://www.promptingguide.ai/techniques/reflexion](https://www.promptingguide.ai/techniques/reflexion)

#### Multimodal CoT

[https://www.promptingguide.ai/techniques/multimodalcot](https://www.promptingguide.ai/techniques/multimodalcot)

#### Graph Prompting

[https://www.promptingguide.ai/techniques/graph](https://www.promptingguide.ai/techniques/graph)

### Tips and Examples

#### Input format

SYSTEM  
You will be provided with a pair of articles (delimited with XML tags) about the same topic. First summarize the arguments of each article. Then indicate which of them makes a better argument and explain why.  
USER  
\<article\> insert first article here \</article\> \<article\> insert second article here \</article\>

SYSTEM  
You will be provided with a thesis abstract and a suggested title for it. The thesis title should give the reader a good idea of the topic of the thesis but should also be eye-catching. If the title does not meet these criteria, suggest 5 alternatives.  
USER  
Abstract: insert abstract here Title: insert title here

#### Instruct the model to answer with citations from a reference text {\#tactic-instruct-the-model-to-answer-with-citations-from-a-reference-text}

SYSTEM  
Use the provided articles delimited by triple quotes to answer questions. If the answer cannot be found in the articles, write "I could not find an answer."  
USER  
\<insert articles, each delimited by triple quotes\> Question: \<insert question here\>

SYSTEM  
You will be provided with a document delimited by triple quotes and a question. Your task is to answer the question using only the provided document and to cite the passage(s) of the document used to answer the question. If the document does not contain the information needed to answer this question then simply write: "Insufficient information." If an answer to the question is provided, it must be annotated with a citation. Use the following format for to cite relevant passages ({"citation": ...}).  
USER  
"""\<insert document here\>""" Question: \<insert question here\>

#### Output format

```
Extract the important entities mentioned in the text below. First extract all company names, then extract all people names, then extract specific topics which fit the content and finally extract general overarching themes

Desired format:
Company names: <comma_separated_list_of_company_names>
People names: -||-
Specific topics: -||-
General themes: -||-

Text: {text}
```

```
 
```

USER  
Summarize the text delimited by triple quotes in about 50 words. """insert text here"""  
USER  
Summarize the text delimited by triple quotes in 2 paragraphs. """insert text here"""  
USER  
Summarize the text delimited by triple quotes in 3 bullet points. """insert text here"""

```
 
```

```
 
```

#### Step by step

SYSTEM  
Use the following step-by-step instructions to respond to user inputs.  
Step 1 - The user will provide you with text in triple quotes. Summarize this text in one sentence with a prefix that says "Summary: ".  
Step 2 - Translate the summary from Step 1 into Spanish, with a prefix that says "Translation: ".

USER  
"""insert text here"""

#### Text Summarization

Antibiotics are a type of medication used to treat bacterial infections. They work by either killing the bacteria or preventing them from reproducing, allowing the body's immune system to fight off the infection. Antibiotics are usually taken orally in the form of pills, capsules, or liquid solutions, or sometimes administered intravenously. They are not effective against viral infections, and using them inappropriately can lead to antibiotic resistance.

Explain the above in one sentence:

```
Summarize the text below as a bullet point list of the most important points.

Text: """
{text input here}
"""
```

Summarize the text delimited by triple quotes with a haiku. """insert text here"""

Summarize the meeting notes in a single paragraph. Then write a markdown list of the speakers and each of their key points. Finally, list the next steps or action items suggested by the speakers, if any.

#### Data extraction

Your task is to extract model names from machine learning paper abstracts. Your response is an array of the model names in the format \[\\"model\_name\\"\]. If you don't find model names in the abstract or you are not sure, return \[\\"NA\\"\]

Abstract: Large Language Models (LLMs), such as ChatGPT and GPT-4, have revolutionized natural language processing research and demonstrated potential in Artificial General Intelligence (AGI). However, the expensive training and deployment of LLMs present challenges to transparent and open academic research. To address these issues, this project open-sources the Chinese LLaMA and Alpaca...

Инструкция: Найди все упомянутые даты и время в тексте. Выпиши их, каждый с новой строки. Пример результата: 22-01-2019 17:00 Завтра 18:15 Вчера Если в тексте нет дат, верни 0.

#### Question Answering

Answer the question based on the context below. Keep the answer short and concise. Respond "Unsure about answer" if not sure about the answer.

Context: Teplizumab traces its roots to a New Jersey drug company called Ortho Pharmaceutical. There, scientists generated an early version of the antibody, dubbed OKT3. Originally sourced from mice, the molecule was able to bind to the surface of T cells and limit their cell-killing potential. In 1986, it was approved to help prevent organ rejection after kidney transplants, making it the first therapeutic antibody allowed for human use.

Question: What was OKT3 originally sourced from?

Answer:

***Output:***  
Mice.

#### Text improvement

Instructions: Correct grammar, spelling and punctuation errors in the text. Keep the original word order.

Instructions: You are an experienced copywriter. Rewrite the marketing text taking into account the type of text and the chosen tone.

Instructions: Rewrite the text, replacing all numbers with digits.
\*

#### Classification

  ```
  SYSTEM
  You will be provided with customer service queries. Classify each query into a primary category and a secondary category. Provide your output in json format with the keys: primary and secondary.
  
  Primary categories: Billing, Technical Support, Account Management, or General Inquiry.
  
  Billing secondary categories:
  - Unsubscribe or upgrade
  - Add a payment method
  - Explanation for charge
  - Dispute a charge
  
  Technical Support secondary categories:
  - Troubleshooting
  - Device compatibility
  - Software updates
  
  Account Management secondary categories:
  - Password reset
  - Update personal information
  - Close account
  - Account security
  
  General Inquiry secondary categories:
  - Product information
  - Pricing
  - Feedback
  - Speak to a human
  USER
  I need to get my internet working again.
  ```

#### Text Classification

Classify the text into neutral, negative or positive.

Text: I think the vacation is okay.  
Sentiment: neutral

Text: I think the food was okay.  
Sentiment:

***Output:***

  ```
  neutral
  ```

#### Generating Data

Produce 10 exemplars for sentiment analysis. Examples are categorized as either positive or negative. Produce 2 negative examples and 8 positive examples. Use this format for the examples:  
Q: \<sentence\>  
A: \<sentiment\>

#### Conversation

The following is a conversation with an AI research assistant. The assistant tone is technical and scientific.

Human: Hello, who are you?  
AI: Greeting! I am an AI research assistant. How can I help you today?  
Human: Can you tell me about the creation of blackholes?  
AI:

***Output:***

  ```
  Sure! Black holes are regions of spacetime where the gravitational force is so strong that nothing, not even light, can escape from it. They are created when a very massive star dies and its core collapses in on itself, forming a singularity of infinite density. The intense gravity of the singularity pulls in all the matter and radiation around it, creating the black hole.
  ```

#### Identify Hallucination in LLM Responses

Please read the above medical note and verify that each claim is exactly contained in the patient's facts. Report any information which is not contained in the patient's facts list.

#### Code Generation

/\*  
Ask the user for their name and say "Hello"  
\*/

*Output:*

  ```
  let name = prompt("What is your name?");console.log(`Hello, ${name}!`);
  ```

  ```
   
  ```

In this code example below, adding "import" hints to the model that it should start writing in Python. (Similarly "SELECT" is a good hint for the start of a SQL statement.)

  ```
  # Write a simple python function that
  # 1. Ask me for a number in mile
  # 2. It converts miles to kilometers
   
  import
  ```

Create a web app called Opossum Search.

  * Every time you make a search query, it should redirect you to a Google search with the same query, but with the word "opossum" added to it.
  * It should be visually similar to Google search.
  * Instead of the google logo, it should have a picture of this opossum: [https://upload.wikimedia.org/wikipedia/commons/thumb/2/27/Opossum\_2.jpg/292px-Opossum\_2.jpg](https://www.google.com/url?sa=E&q=https%3A%2F%2Fupload.wikimedia.org%2Fwikipedia%2Fcommons%2Fthumb%2F2%2F27%2FOpossum_2.jpg%2F292px-Opossum_2.jpg)
  * It should be a single HTML file, with no separate JS or CSS files.
  * It should say Powered by opossum search in the footer.
  * Do not use any unicode characters.

#### Explain Code

SELECT students.StudentId, students.StudentName  
FROM students  
INNER JOIN departments  
ON students.DepartmentId = departments.DepartmentId  
WHERE departments.DepartmentName = 'Computer Science';

Explain the above SQL statement.

#### SQL generation

##### SQL query generation

"""  
Table departments, columns = \[DepartmentId, DepartmentName\]  
Table students, columns = \[DepartmentId, StudentId, StudentName\]  
Create a MySQL query for all students in the Computer Science Department  
"""

*Output:*

SELECT StudentId, StudentName  
FROM students  
WHERE DepartmentId IN (SELECT DepartmentId FROM departments WHERE DepartmentName = 'Computer Science');

##### Database schema generation

Table departments, columns = \[DepartmentId, DepartmentName\]  
Table students, columns = \[DepartmentId, StudentId, StudentName\]  
Create a valid database schema with the above tables and columns

*Output:*

CREATE TABLE departments (  
DepartmentId INT PRIMARY KEY,  
DepartmentName VARCHAR(50)  
);

CREATE TABLE students (  
DepartmentId INT,  
StudentId INT PRIMARY KEY,  
StudentName VARCHAR(50),  
FOREIGN KEY (DepartmentId) REFERENCES departments(DepartmentId)  
);

##### Test data generation

CREATE TABLE departments (  
DepartmentId INT PRIMARY KEY,  
DepartmentName VARCHAR(50)  
);

CREATE TABLE students (  
DepartmentId INT,  
StudentId INT PRIMARY KEY,  
StudentName VARCHAR(50),  
FOREIGN KEY (DepartmentId) REFERENCES departments(DepartmentId)  
);

Given the database schema above, generate valid insert statements include 4 rows for each table.

*Output:*

INSERT INTO departments (DepartmentId, DepartmentName)  
VALUES (1, 'Computer Science'), (2, 'Mathematics'), (3, 'Physics'), (4, 'Biology');

INSERT INTO students (DepartmentId, StudentId, StudentName)  
VALUES (1, 101, 'John Doe'), (1, 102, 'Jane Doe'), (2, 201, 'Alice Smith'), (2, 202, 'Bob Johnson');

### Prompt for Blog writing

[https://www.youtube.com/watch?v=eaivzIPKhqg](https://www.youtube.com/watch?v=eaivzIPKhqg) How To Create Blog Using AI | Complete Blogging Tutorial

### Prompt for media generation

Example form [https://www.youtube.com/watch?v=SE4IotjLWzc](https://www.youtube.com/watch?v=SE4IotjLWzc) (ru) How to make hand-drawn illustrations in a neural network, create and color a comic in a single style!

A simple sketch illustration of \[INSERT CUSTOM SCENE DESCRIPTION HERE\]. The lines are slightly uneven and hand-drawn, giving a warm, organic feel. The background is white. The illustration has minimalistic, slightly rough lines and is black and white.

  1) Оставь текст вне квадратных скобок \[INSERT CUSTOM SCENE DESCRIPTION HERE\] неизменным.
  2) Замени текст внутри квадратных скобок \[INSERT CUSTOM SCENE DESCRIPTION HERE\] на описание сцены с участием человека или персонажа, которое я тебе напишу или попрошу придумать.
  3) Имей ввиду, что иллюстрации у нас черно-белые (об этом сказано в промпте)
  4) Не используй в иллюстрациях "текст", то есть никаких табличек, знаков и т.п.
  5) Эта фраза всегда должна быть в начале: A simple sketch illustration of
  6) Эта фраза всегда должна быть в конце: The lines are slightly uneven and hand-drawn, giving a warm, organic feel. The background is white. The illustration has minimalistic, slightly rough lines and is black and white.

Придумай промпт с ленивцем (животным) -фрилансером, который сидит за ноутбуком и у него горят сроки по дедлайну

==== Result ====

A simple sketch illustration of a sloth freelancer sitting at a small wooden desk, typing frantically on a laptop. The sloth has a slightly panicked expression, with one hand on the keyboard and the other holding a cup of coffee. The desk is cluttered with papers, a clock showing a late hour, and a calendar with a circled deadline date. The sloth is wearing round glasses and a loose scarf, adding to its stressed but endearing appearance. The lines are slightly uneven and hand-drawn, giving a warm, organic feel. The background is white. The illustration has minimalistic, slightly rough lines and is black and white.

### Prompt libraries

[https://www.youtube.com/watch?v=2KBpbppVM\_E](https://www.youtube.com/watch?v=2KBpbppVM_E) 8 лучших библиотек промптов + OpenAI выпустила бесплатный генератор промптов

  * [https://yandex.cloud/ru/docs/foundation-models/prompts/yandexgpt](https://yandex.cloud/ru/docs/foundation-models/prompts/yandexgpt) для запросов на русском языке
  * [https://ai.google.dev/gemini-api/prompts](https://ai.google.dev/gemini-api/prompts)
  * [https://hero.page/discover](https://hero.page/discover)
  * [https://snackprompt.com/](https://snackprompt.com/) +
  * [https://docs.anthropic.com/en/prompt-library/library](https://docs.anthropic.com/en/prompt-library/library)
  * [https://github.com/pacholoamit/chatgpt-prompts](https://github.com/pacholoamit/chatgpt-prompts)
  * [https://console.cloud.google.com/projectselector2/vertex-ai/studio/prompt-gallery?supportedpurview=project](https://console.cloud.google.com/projectselector2/vertex-ai/studio/prompt-gallery?supportedpurview=project)
  * [https://platform.openai.com/playground/chat?models=gpt-4o](https://platform.openai.com/playground/chat?models=gpt-4o)
  * [https://github.com/VoloBuilds/prompts/blob/main/LearnToCode.md](https://github.com/VoloBuilds/prompts/blob/main/LearnToCode.md)

### References

[https://www.promptingguide.ai/](https://www.promptingguide.ai/)

[https://platform.openai.com/docs/guides/prompt-engineering](https://platform.openai.com/docs/guides/prompt-engineering)

[https://help.openai.com/en/articles/6654000-best-practices-for-prompt-engineering-with-the-openai-api](https://help.openai.com/en/articles/6654000-best-practices-for-prompt-engineering-with-the-openai-api)

[https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/prompt-engineering](https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/prompt-engineering)

[https://www.youtube.com/watch?v=ntACspNRNXk](https://www.youtube.com/watch?v=ntACspNRNXk) (ru)

[https://www.youtube.com/watch?v=rJVHjE8t1qs](https://www.youtube.com/watch?v=rJVHjE8t1qs) (ru)
\*
