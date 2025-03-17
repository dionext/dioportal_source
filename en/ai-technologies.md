---
title: "AI. Technologies"
description: ""
keywords: ""
lang: "en"
permalink: "ai-technologies"
aliases:
  - "ai-technologies"
---

# AI. Technologies

### Low-rank adaptation (LoRA)

For additional training, there is, for example, a popular one [https://github.com/oobabooga/text-generation-webui](https://github.com/oobabooga/text-generation-webui) But you need to be able to deploy it, and also still understand the dataset formats. So far, the industry is not very standardized and there are no solutions for Win/Mac like office packages.

[https://habr.com/ru/articles/776872/](https://habr.com/ru/articles/776872/) (ru) In this guide, author tell and show you how to additionally train the 7-billionth Saiga model by Ilya Gusev @Takagi for your tasks. This article is a kind of tutorial on additional training of a model on Kaggle.

### Embedding

[https://www.youtube.com/watch?v=F0FGcxkMElk](https://www.youtube.com/watch?v=F0FGcxkMElk) Generating Embeddings with Spring AI: Step-by-Step Guide with Pitfalls

#### Choose Embedding model

[https://www.mongodb.com/developer/products/atlas/choose-embedding-model-rag/](https://www.mongodb.com/developer/products/atlas/choose-embedding-model-rag/) [https://huggingface.co/spaces/mteb/leaderboard](https://huggingface.co/spaces/mteb/leaderboard) [https://www.pinecone.io/learn/series/rag/embedding-models-rundown/](https://www.pinecone.io/learn/series/rag/embedding-models-rundown/)

* Max Tokens: The number of tokens that can be squeezed into a single embedding. Typically, you won't want to fit more than a paragraph of text (~100 tokens) into a single embedding. So even embedding models with a max token count of 512 should be more than enough.
* Embedding Dimensions: The length of the embedding vector. Smaller embeddings allow for faster inference and are more storage efficient, while more dimensions can capture fine details and relationships in the data. Ultimately, we want to find a good tradeoff between capturing data complexity and operational efficiency.

<!-- -->

* [voyage-lite-02-instruct](https://docs.voyageai.com/embeddings/): A proprietary embedding model from VoyageAI
* [text-embedding-3-large](https://openai.com/blog/new-embedding-models-and-api-updates): One of OpenAI's latest proprietary embedding models
* [UAE-Large-V1](https://huggingface.co/WhereIsAI/UAE-Large-V1): A small-ish (335M parameters) open-source embedding model

#### Spliting

How to split text for embedding? The answer depends on each specific domain. Your main options are:

* split into paragraphssplit
* into sentencessplit
* into N words, letters or tokens.

You can also use a sliding window approach, where each chunk includes part of the previous chunk. More advanced embedding calculation options:

* Summarize chunks
* Extract possible questions or keywords using LLM

### Pinecone

[https://www.pinecone.io/pricing/](https://www.pinecone.io/pricing/)
Build knowledgeable AI

With its vector database at the core, Pinecone is the leading knowledge platform for building accurate, secure, and scalable AI applications.

### RAG

todo [https://www.youtube.com/watch?v=JanB50ALQg0](https://www.youtube.com/watch?v=JanB50ALQg0) Иван Насонов | Advanced RAG Pipelines

[https://www.youtube.com/watch?v=6Pgmr7xMjiY](https://www.youtube.com/watch?v=6Pgmr7xMjiY) Java + RAG: Create an AI-Powered Financial Advisor using Spring AI

[https://www.youtube.com/watch?v=JeqAdqBA\_Yo](https://www.youtube.com/watch?v=JeqAdqBA_Yo) Загружаем в ИИ большие данные (книги, документы), заставляем ИИ цитировать источники, автономия

[https://www.youtube.com/watch?v=NArkdDqt-F0](https://www.youtube.com/watch?v=NArkdDqt-F0) Анатомия RAG: Разбираем по косточкам современных чат-ботов. Галымжан Туткушев

[https://www.baeldung.com/spring-ai-redis-rag-app](https://www.baeldung.com/spring-ai-redis-rag-app)

[https://www.youtube.com/watch?v=FA7oLqzz8gQ\&t=16s](https://www.youtube.com/watch?v=FA7oLqzz8gQ&t=16s) Advanced RAG: Combining RAG with Text-to-SQL - LlamaIndex

#### NaiveRAG

Naive RAG is a paradigm that combines information retrieval with natural language generation to produce responses to queries or prompts. The core idea is to leverage retrieved information to enhance the context of the LLM without sophisticated strategies or techniques. [https://www.superteams.ai/blog/how-to-implement-naive-rag-advanced-rag-and-modular-rag](https://www.superteams.ai/blog/how-to-implement-naive-rag-advanced-rag-and-modular-rag)

#### RQ-RAG

[https://github.com/chanchimin/RQ-RAG](https://github.com/chanchimin/RQ-RAG)

[https://aiexpjourney.substack.com/p/a-brief-introduction-to-rq-rag](https://aiexpjourney.substack.com/p/a-brief-introduction-to-rq-rag)

#### Hypothetical Document Embeddings(HyDE)

Advanced RAG - Improving retrieval using Hypothetical Document Embeddings(HyDE)

HyDE uses a Language Learning Model, like ChatGPT, to create a theoretical document when responding to a query, as opposed to using the query and its computed vector to directly seek in the vector database. It goes a step further by using an unsupervised encoder learned through contrastive methods. This encoder changes the theoretical document into an embedding vector to locate similar documents in a vector database. Rather than seeking embedding similarity for questions or queries, it focuses on answer-to-answer embedding similarity. Its performance is robust, matching well-tuned retrievers in various tasks such as web search, QA, and fact verification [https://medium.aiplanet.com/advanced-rag-improving-retrieval-using-hypothetical-document-embeddings-hyde-1421a8ec075a](https://medium.aiplanet.com/advanced-rag-improving-retrieval-using-hypothetical-document-embeddings-hyde-1421a8ec075a)

#### GraphRAG

GraphRAG is a structured, hierarchical approach to Retrieval Augmented Generation (RAG), as opposed to naive semantic-search approaches using plain text snippets. The GraphRAG process involves extracting a knowledge graph out of raw text, building a community hierarchy, generating summaries for these communities, and then leveraging these structures when perform RAG-based tasks.

[https://microsoft.github.io/graphrag/](https://microsoft.github.io/graphrag/)

[https://medium.com/@zilliz\_learn/graphrag-explained-enhancing-rag-with-knowledge-graphs-3312065f99e1](https://medium.com/@zilliz_learn/graphrag-explained-enhancing-rag-with-knowledge-graphs-3312065f99e1)

[https://habr.com/ru/articles/857354/](https://habr.com/ru/articles/857354/)

#### LightRAG

[https://lightrag.github.io/](https://lightrag.github.io/) ( [https://arxiv.org/pdf/2410.05779v2](https://arxiv.org/pdf/2410.05779v2) )

[https://github.com/HKUDS/LightRAG](https://github.com/HKUDS/LightRAG)

[https://www.youtube.com/watch?v=oageL-1I0GE](https://www.youtube.com/watch?v=oageL-1I0GE) LightRAG: A More Efficient Solution than GraphRAG for RAG Systems?

[https://www.youtube.com/watch?v=5EmRZcJIfnw\&t=11s](https://www.youtube.com/watch?v=5EmRZcJIfnw&t=11s) LightRAG - A simple and fast RAG that beats GraphRAG? (paper explained)

### Re-reading (RE2) {\#what-is-re-reading-re2}

Sometimes [Large Language Models (LLMs)](https://learnprompting.org/docs/vocabulary/LLM) just fail to notice important details in our prompt and this leads to incorrect results.

Re-reading (RE2)[1](https://learnprompting.org/docs/advanced/zero_shot/re_reading?srsltid=AfmBOoqNe82xsNUkmxsh_P0B2928FUWwRMi_6yuJ2c18Lo9EmmENAxTU#footnotes)Xu, X., Tao, C., Shen, T., Xu, C., Xu, H., Long, G., \& guang Jian-Lou. (2024). Re-Reading Improves Reasoning in Large Language Models. [https://arxiv.org/abs/2309.06275](https://arxiv.org/abs/2309.06275) is a technique that aims to solve this problem by asking an LLM to re-read the prompt.  
RE2 Prompting  
Q: {Input Query} Read the question again: {Input Query}

While being so simple, RE2 is a general end effective technique that consistently enhances the reasoning performance of LLMs through just a rereading strategy. Furthermore, RE2 is compatible and can be combined with most thought-eliciting prompting methods, including [Chain-of-Thought (CoT)](https://learnprompting.org/docs/intermediate/chain_of_thought).
