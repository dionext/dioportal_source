---
title: "Dionext software development notes"
description: ""
keywords: ""
lang: "en"
permalink: "ai-java"
aliases:
  - "ai-java"
---


## AI. Java. Spring AI

[https://www.youtube.com/watch?v=H\_58SyQfl\_U](https://www.youtube.com/watch?v=H_58SyQfl_U) New Vector APIs coming to Java - Java 23 update

AI Model API Portable

Model API across AI providers for Chat, Text to Image, Audio Transcription, Text to Speech, and Embedding models. Both synchronous and stream API options are supported. With support for AI Models from OpenAI, Microsoft, Amazon, Google, Amazon Bedrock, Hugging Face and more [https://docs.spring.io/spring-ai/reference/api/index.html](https://docs.spring.io/spring-ai/reference/api/index.html)

* [OpenAI Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/openai-chat.html) (streaming, multi-modality \& function-calling support)

* [Microsoft Azure Open AI Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/azure-openai-chat.html) (streaming \& function-calling support)

* [Ollama Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/ollama-chat.html) (streaming, multi-modality \& function-calling support)

* [Hugging Face Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/huggingface.html) (no streaming support)

* [Google Vertex AI PaLM2 Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/vertexai-palm2-chat.html) (no streaming support)

* [Google Vertex AI Gemini Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/vertexai-gemini-chat.html) (streaming, multi-modality \& function-calling support)

* [Amazon Bedrock](https://docs.spring.io/spring-ai/reference/api/bedrock.html)
  
  * [Cohere Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/bedrock/bedrock-cohere.html)
  
  * [Llama Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/bedrock/bedrock-llama.html)
  
  * [Titan Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/bedrock/bedrock-titan.html)
  
  * [Anthropic Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/bedrock/bedrock-anthropic.html)
  
  * [Jurassic2 Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/bedrock/bedrock-jurassic2.html)

* [Mistral AI Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/mistralai-chat.html) (streaming \& function-calling support)

* [Anthropic Chat Completion](https://docs.spring.io/spring-ai/reference/api/chat/anthropic-chat.html) (streaming \& function-calling support)

The project draws inspiration from notable Python projects, such as LangChain and LlamaIndex, but Spring AI is not a direct port of those projects. The project was founded with the belief that the next wave of Generative AI applications will not be only for Python developers but will be ubiquitous across many programming languages.  
Spring AI provides the following features:

* Support for all major Model providers such as OpenAI, Microsoft, Amazon, Google, and Hugging Face.

* Supported Model types are Chat, Text to Image, Audio Transcription, Text to Speech, and more on the way.

* Portable API across AI providers for all models. Both synchronous and stream API options are supported. Dropping down to access model specific features is also supported.

* Mapping of AI Model output to POJOs.

* Support for all major Vector Database providers such as Apache Cassandra, Azure Vector Search, Chroma, Milvus, MongoDB Atlas, Neo4j, Oracle, PostgreSQL/PGVector, PineCone, Qdrant, Redis, and Weaviate.

* Portable API across Vector Store providers, including a novel SQL-like metadata filter API that is also portable.

* Function calling.

* Spring Boot Auto Configuration and Starters for AI Models and Vector Stores.

* ETL framework for Data Engineering.

[https://docs.spring.io/spring-ai/reference/api/prompt.html](https://docs.spring.io/spring-ai/reference/api/prompt.html)  
The primary roles are:

* System Role: Guides the AI's behavior and response style, setting parameters or rules for how the AI interprets and replies to the input. It's akin to providing instructions to the AI before initiating a conversation.

* User Role: Represents the user's input -- their questions, commands, or statements to the AI. This role is fundamental as it forms the basis of the AI's response.

* Assistant Role: The AI's response to the user's input. More than just an answer or reaction, it's crucial for maintaining the flow of the conversation. By tracking the AI's previous responses (its 'Assistant Role' messages), the system ensures coherent and contextually relevant interactions. The Assistant message may contain Function Tool Call request information as well. It's like a special feature in the AI, used when needed to perform specific functions such as calculations, fetching data, or other tasks beyond just talking.

* Tool/Function Role: The Too/Function Role focuses on returning additional information in response to Tool Call Aisstnat Messages.

[https://spring.io/projects/spring-ai](https://spring.io/projects/spring-ai)

[https://docs.spring.io/spring-ai/reference/](https://docs.spring.io/spring-ai/reference/)

[https://docs.spring.io/spring-ai/reference/api/embeddings/ollama-embeddings.html](https://docs.spring.io/spring-ai/reference/api/embeddings/ollama-embeddings.html) Ollama - run AI models on your local machine

[https://www.youtube.com/watch?v=QWKs0aOZaVQ\&list=PLO66QfE8gWT1lyNltpE73ee8mVn6C4xN9](https://www.youtube.com/watch?v=QWKs0aOZaVQ&list=PLO66QfE8gWT1lyNltpE73ee8mVn6C4xN9) [Spring AI Tutorials : Generative AI for Java Developers](https://www.youtube.com/watch?v=QWKs0aOZaVQ&list=PLO66QfE8gWT1lyNltpE73ee8mVn6C4xN9&pp=iAQB)

[https://www.youtube.com/watch?v=ACpLp2KXqgE](https://www.youtube.com/watch?v=ACpLp2KXqgE) Working with Prompts in Spring AI - Effectively Communicating with LLMs - Dan Vega

[https://foojay.io/today/spring-ai-how-to-write-genai-applications-with-java/](https://foojay.io/today/spring-ai-how-to-write-genai-applications-with-java/) (Neo4j Vector Database)

Getting started with (Retrieval Augmented Generation) RAG in Java \& Spring AI [https://www.youtube.com/watch?v=4-rG2qsTrAs](https://www.youtube.com/watch?v=4-rG2qsTrAs)

[https://www.baeldung.com/spring-ai](https://www.baeldung.com/spring-ai)

[https://www.youtube.com/watch?v=aNKDoiOUo9M](https://www.youtube.com/watch?v=aNKDoiOUo9M) Spring Tips: Spring AI [D:\\Projects\\examples\\ai\\llm-rag-with-spring-ai](file:///D:/Projects/examples/ai/llm-rag-with-spring-ai) (vector store example)

[https://www.youtube.com/watch?v=yPu-WV\_00Tk](https://www.youtube.com/watch?v=yPu-WV_00Tk) Spring Tips: Vector Databases with Spring AI [https://www.youtube.com/watch?v=Q65-Zade25w](https://www.youtube.com/watch?v=Q65-Zade25w)

[https://www.youtube.com/watch?v=QWgiOoB4OOU](https://www.youtube.com/watch?v=QWgiOoB4OOU) Spring into the AI Era: A Practical Exploration for Developers (Workshop) - базовый старый доклад

[https://www.youtube.com/watch?v=jJ63tedBAzI](https://www.youtube.com/watch?v=jJ63tedBAzI) Building a ChatGPT Clone in Java with HTMX, Spring Boot, and Spring AI провстое прокси приложение [https://github.com/danvega/chatgpt-clone](https://github.com/danvega/chatgpt-clone) интересно своим интефейсом

[https://www.youtube.com/watch?v=7K6YPRUtBkQ](https://www.youtube.com/watch?v=7K6YPRUtBkQ) Generating Images with Spring AI

[https://www.youtube.com/watch?v=qL9A21N-6J4](https://www.youtube.com/watch?v=qL9A21N-6J4) Unleashing AI in Java: A Guide to Semantic Kernel, LangChain4j, and Spring AI by Marcus Hellberg

[https://www.youtube.com/watch?v=k3fSQpz2Esg](https://www.youtube.com/watch?v=k3fSQpz2Esg) Code your own dating bot with Spring Boot \& React \& AI [https://github.com/koushikkothagal/tinder-ai-backend](https://github.com/koushikkothagal/tinder-ai-backend) пример огранизации фейкового чат диалога , фронт на React

[https://www.youtube.com/watch?v=0QVdJcxGf1M](https://www.youtube.com/watch?v=0QVdJcxGf1M) Generate Dynamic Websites using ChatGPT and Spring AI

[https://www.youtube.com/watch?v=6Pgmr7xMjiY](https://www.youtube.com/watch?v=6Pgmr7xMjiY) Java + RAG: Create an AI-Powered Financial Advisor using Spring AI

[https://www.youtube.com/@DevMastersDb](https://www.youtube.com/@DevMastersDb)

[https://www.youtube.com/watch?v=jClr5LtQFIQ\&t=216s](https://www.youtube.com/watch?v=jClr5LtQFIQ&t=216s) Spring AI RAG | Chat with your PDF Documents using Java and Spring Boot

[https://dev.to/brunooliveira/basic-rag-app-with-spring-ai-docker-and-ollama-1i7j](https://dev.to/brunooliveira/basic-rag-app-with-spring-ai-docker-and-ollama-1i7j)

```
    environment:
      - SPRING_DATASOURCE_URL=jdbc:postgresql://db:5432/ragdb
      - SPRING_DATASOURCE_USERNAME=postgres
      - SPRING_DATASOURCE_PASSWORD=password
      - SPRING_AI_OLLAMA_BASE_URL=http://ollama-llm:11434/
      - SPRING_AI_OLLAMA_CHAT_OPTIONS_MODEL=tinydolphin
      - SPRING_AI_OLLAMA_CHAT_OPTIONS_ALTERNATIVE_MODEL=tinyllama
      - SPRING_AI_OLLAMA_CHAT_OPTIONS_ALTERNATIVE_SECOND_MODEL=llama3.1
      - SPRING_AI_OLLAMA_EMBEDDING_OPTIONS_MODEL=mxbai-embed-large
      - SPRING_AI_VECTORSTORE_PGVECTOR_REMOVE_EXISTING_VECTOR_STORE_TABLE=true
      - SPRING_AI_VECTORSTORE_PGVECTOR_INDEX_TYPE=HNSW
      - SPRING_AI_VECTORSTORE_PGVECTOR_DISTANCE_TYPE=COSINE_DISTANCE
      - SPRING_AI_VECTORSTORE_PGVECTOR_DIMENSIONS=1024
```
