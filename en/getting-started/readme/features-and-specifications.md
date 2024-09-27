---
description: >-
  For those already familiar with LLM application tech stacks, this document
  serves as a shortcut to understand AgentBase's unique advantages
---

# Features and Specifications

We adopt transparent policies around product specifications to ensure decisions are made based on complete understanding. Such transparency not only benefits your technical selection, but also promotes deeper comprehension within the community for active contributions.

### Project Basics

<table data-header-hidden><thead><tr><th width="341"></th><th></th></tr></thead><tbody><tr><td>Established</td><td>March 2023</td></tr><tr><td>Open Source License</td><td><a href="../../policies/open-source.md">Apache License 2.0 with commercial licensing</a></td></tr><tr><td>Official R&#x26;D Team</td><td>Over 15 full-time employees</td></tr><tr><td>Community Contributors</td><td>Over <a href="https://ossinsight.io/analyze/agent-base/agentbase#overview">290</a> people(As of Q2 2024)</td></tr><tr><td>Backend Technology</td><td>Python/Flask/PostgreSQL</td></tr><tr><td>Frontend Technology</td><td>Next.js</td></tr><tr><td>Codebase Size</td><td>Over 130,000 lines</td></tr><tr><td>Release Frequency</td><td>Average once per week</td></tr></tbody></table>

### Technical Features

<table data-header-hidden><thead><tr><th width="240"></th><th></th></tr></thead><tbody><tr><td>LLM Inference Engines</td><td>AgentBase Runtime (LangChain removed since v0.4)</td></tr><tr><td>Commercial Models Supported</td><td><strong>10+</strong>, including OpenAI and Anthropic<br>Onboard new mainstream models within 48 hours</td></tr><tr><td>MaaS Vendor Supported</td><td><strong>7</strong>, Hugging Face, Replicate, AWS Bedrock, NVIDIA, GroqCloud, together.ai,, OpenRouter</td></tr><tr><td>Local Model Inference Runtimes Supported</td><td><strong>6</strong>, Xoribits (recommended), OpenLLM, LocalAI, ChatGLM,Ollama, NVIDIA TIS </td></tr><tr><td>OpenAI Interface Standard Model Integration Supported</td><td><strong>∞</strong></td></tr><tr><td>Multimodal Capabilities</td><td><p>ASR Models</p><p>Rich-text models up to GPT-4o specs</p></td></tr><tr><td>Built-in App Types</td><td>Text generation, Chatbot, Agent,  Workflow, Chatflow</td></tr><tr><td>Prompt-as-a-Service Orchestration</td><td><p>Visual orchestration interface widely praised, moagentbase Prompts and preview effects in one place.<br></p><p><strong>Orchestration Modes</strong></p><ul><li>Simple orchestration</li><li>Assistant orchestration </li><li>Flow orchestration </li></ul><p><strong>Prompt Variable Types</strong></p><ul><li>String</li><li>Radio enum</li><li>External API</li><li>File (Q3 2024)</li></ul></td></tr><tr><td>Agentic Workflow Features</td><td><p>Industry-leading visual workflow orchestration interface, live-editing node debugging, modular DSL, and native code runtime, designed for building more complex, reliable, and stable LLM applications.</p><p><br>Supported Nodes</p><ul><li>LLM</li><li>Knowledge Retrieval</li><li>Question Classifier</li><li>IF/ELSE</li><li>CODE</li><li>Template</li><li>HTTP Request</li><li>Tool</li></ul></td></tr><tr><td>RAG Features</td><td><p>Industry-first visual knowledge base management interface, supporting snippet previews and recall testing.</p><p><strong>Indexing Methods</strong></p><ul><li>Keywords</li><li>Text vectors</li><li>LLM-assisted question-snippet model</li></ul><p><strong>Retrieval Methods</strong></p><ul><li>Keywords</li><li>Text similarity matching</li><li>Hybrid Search</li><li>N choose 1（Legacy）</li><li>Multi-path retrieval</li></ul><p><strong>Recall Optimization</strong></p><ul><li>Rerank models</li></ul></td></tr><tr><td>ETL Capabilities</td><td><p>Automated cleaning for TXT, Markdown, PDF, HTML, DOC, CSV formats. Unstructured service enables maximum support.</p><p>Sync Notion docs as knowledge bases.<br>Sync Webpages as knowledge bases.</p></td></tr><tr><td>Vector Databases Supported</td><td>Qdrant (recommended), Weaviate，Zilliz/Milvus, Pgvector, Pgvector-rs，Chroma, OpenSearch, TiDB, Tencent Vector, Oracle, Relyt</td></tr><tr><td>Agent Technologies</td><td><p>ReAct, Function Call.<br></p><p><strong>Tooling Support</strong></p><ul><li>Invoke OpenAI Plugin standard tools </li><li>Directly load OpenAPI Specification APIs as tools</li></ul><p><strong>Built-in Tools</strong></p><ul><li>40+ tools(As of Q2 2024)</li></ul></td></tr><tr><td>Logging</td><td>Supported, annotations based on logs</td></tr><tr><td>Annotation Reply</td><td>Based on human-annotated Q&#x26;As, used for similarity-based replies. Exportable as data format for model fine-tuning.</td></tr><tr><td>Content Moderation</td><td>OpenAI Moderation or external APIs</td></tr><tr><td>Team Collaboration</td><td>Workspaces, multi-member management</td></tr><tr><td>API Specs</td><td>RESTful, most features covered</td></tr><tr><td>Deployment Methods</td><td>Docker, Helm</td></tr></tbody></table>