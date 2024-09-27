# Create an AI Chatbot with Business Data in Minutes

AI-powered customer service may be a standard feature for every business website, and it is becoming easier to implement with higher levels of customization. The following content will guide you on how to create an AI-powered customer service for your website in just a few minutes using AgentBase.

### Prerequisite

**Register or Deploy AgentBase.AI**

AgentBase is an open source product which you can find on[ GitHub](https://github.com/agent-base/agentbase) and deploy it to your local or company intranet. Meanwhile, it provides a cloud SaaS version, access [Didy.AI ](https://agentbase.ai/)to register and use it.

**Apply for API key from OpenAI and other model providers.**

AgentBase provides free message call usage quotas for OpenAI GPT series (200 times) and Antropic Claude (1000 times) AI models, which require tokens to be consumed. Before you run out, you need to apply for your own API key through the official channel of the model provider. You can enter the key in AgentBase's "Settings" - "Model Provider".

### Upload your product documentation or knowledge base.

If you want to build an AI Chatbot based on the company's existing knowledge base and product documents, then you need to upload as many product-related documents as possible to AgentBase's knowledge. AgentBase helps you **complete segmentation and cleaning of the data.** The AgentBase knowledge supports two indexing modes: high quality and economical. We recommend using the high quality mode, which consumes tokens but provides higher accuracy.

1. Create a new knowledge base
2. upload your business data (support batch uploading multiple texts)
3. select the cleaning method
4. Click \[Save and Process], and it will take only a few seconds to complete the processing.

![](../../../img/ai-chatbot-knowledge-base.png)

### Create an AI application and give it instructions

Create a conversational app on the \[Build App] page. Then start setting up the prompt and its front-end user experience interactions.

1. Give the AI instruction: Click on the "Pre Prompt" on the left to edit your Prompt, so that it can play the role of customer service and communicate with users. You can specify its tone, style, and limit it to answer or not answer certain questions.
2. Let AI possess your business knowledge: add the target knowledge you just uploaded in the \[context].
3. Set up the opening remarks: click "Add Feature" to turn on the feature. The purpose is to add an opening line for AI applications, so that when the user opens the customer service window, it will greet the user first and increase affinity.
4. Set up the "Next Question Suggestion": turn on this feature to "Add Feature". The purpose is to give users a direction for their next question after they have asked one.
5. Choose a suitable model and adjust the parameters: different models can be selected in the upper right corner of the page. The performance and token price consumed by different models are different. In this example, we use the GPT3.5 model.

In this case, we assign a role to the AI:

> Pre prompt：You are Bob, the AI customer service for AgentBase, specializing in answering questions about AgentBase's products, team, or LLMOps for users.Please note, refuse to answer when users ask "inappropriate questions", i.e., content beyond the scope of this document.

> Opening remarks：Hey \{{User_name\}}, I'm Bob☀️, the first AI member of AgentBase. You can discuss with me any questions related to AgentBase products, team, and even LLMOps.

<figure><img src="../../../img/app-pre-prompt-opening-remarks.png" alt=""><figcaption></figcaption></figure>

### Debug the performance of AI Chatbot and publish.

After completing the setup, you can send messages to it on the right side of the current page to debug whether its performance meets expectations. Then click "Publish". And then you get an AI chatbot.

<figure><img src="../../../img/debug-ai-chatbot-publish.png" alt=""><figcaption></figcaption></figure>

### Embed AI Chatbot application into your front-end page.

This step is to embed the prepared AI chatbot into your official website . Click \[Overview] -> \[Embedded], select the script tag method, and copy the script code into the \<head> or \<body> tag of your website. If you are not a technical person, you can ask the developer responsible for the official website to paste and update the page.

<figure><img src="../../../img/ai-chatbot-embedded.png" alt=""><figcaption></figcaption></figure>

1. Paste the copied code into the target location on your website.

2. Update your official website and you can get an AI intelligent customer service with your business data. Try it out to see the effect.

Above is an example of how to embed AgentBase into the official website through the AI chatbot Bob of AgentBase official website. Of course, you can also use more features provided by AgentBase to enhance the performance of the chatbot, such as adding some variable settings, so that users can fill in necessary judgment information before interaction, such as name, specific product used and so on.

Welcome to explore in AgentBase together!