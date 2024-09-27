# Prompting Expert Mode

Currently, the orchestration for creating apps in AgentBase is set to **Basic Mode** by default. This is ideal for non-tech-savvy individuals who want to quickly make an app. For example, if you want to create a corporate knowledge-base ChatBot or an article summary Generator, you can use the **Basic Mode** to design `Pre-prompt` words, add `Query`, integrate `Context`, and other straightforward steps to launch a complete app. For more head to 👉 [text-generation-application.md](../../user-guide/creating-agentbase-apps/prompt-engineering/text-generation-application.md "mention") and [conversation-application.md](../../user-guide/creating-agentbase-apps/prompt-engineering/conversation-application.md "mention").

💡However, you surely want to design prompts in a more customized manner if you're a developer who has conducted in-depth research on prompts, then you should opt for the **Expert Mode**. In this mode, you are granted permission to customize comprehensive prompts rather than using the pre-packaged prompts from AgentBase. You can moagentbase the built-in prompts, rearrange the placement of `Context` and `History` , set necessary parameters, and more. If you're familiar with the OpenAI's Playground, you can get up to speed with this mode more quickly.

***

Well, before you try the new mode, you should be aware of some essential elements in it:

*   **Complete**

    When choosing a model, if you see "COMPLETE" on the right side of the model name, it indicates a Text completion model e.g. <img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/screenshot-20231017-092613.png" alt="" data-size="line">

    This type of model accepts a freeform text string and generates a text completion, attempting to match any context or pattern you provide. For example, if you write the prompt `As René Descartes said, "I think, therefore"`, it's highly likely that the model will return `"I am."` as the completion.\\
*   **Chat**

    When choosing a model, if you see "CHAT" on the right side of the model name, it indicates a Chat completions model e.g. <img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/screenshot-20231017-092957.png" alt="" data-size="line">

    This type of model takes a list of messages as input and returns a message generated by the model as output. It consists of three message types: `SYSTEM`, `USER`, and `ASSISTANT`.

    *   `SYSTEM`

        System messages help guide the behavior of the AI assistant. For example, you can alter the personality of the AI assistant or provide specific instructions on how it should perform throughout the conversation. System messages are optional. Without system messages, the AI assistant might behave like it's using generic messages such as `"you are a helpful assistant."`
    *   `USER`

        User messages provide requests or comments for the AI assistant to respond to.
    *   `ASSISTANT`

        Assistant messages store previous assistant responses, but they can also be written by you to provide examples of desired behavior.\\
*   **Stop\_Sequences**

    Stop\_Sequences refers to specific words, phrases, or characters used to send a signal to LLM to stop generating text.\\
*   **Blocks**

    <img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/Context.png" alt="" data-size="line">

    When users input a query, the app processes the query as search criteria for the knowledge. The organized results from the search then replace the variable `Context`, allowing the LLM to reference the content for its response.

    <img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/QUERY.png" alt="" data-size="line">

    The query content is only available in the Text completion models of conversational applications. The content entered by the user during the conversation will replace this variable, initiating a new turn of dialogue.

    <img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/history (1).png" alt="" data-size="line">

    The conversation history is only available in the Text completion model of conversational applications. When engaging in multiple conversations in dialogue applications, AgentBase will assemble and concatenate the historical dialogue records according to built-in rules and replace the 'Conversation History' variable. The `Human` and `Assistant` prefixes can be modified by clicking on the `...` after "Conversation History".\\
*   **Prompt Template**

    In this mode, before formal orchestration, an initial template is provided in the prompt box. We can directly moagentbase this template to have more customized requirements for LLM. Different types of applications have variations in different modes.

    For more head to 👉 [prompt-template.md](prompt-template.md "mention")

***

## Comparison of the two modes

<table><thead><tr><th width="333">Comparison Dimension</th><th width="197">Basic Mode</th><th>Expert Mode</th></tr></thead><tbody><tr><td>Visibility of Built-in Prompts</td><td>Invisible</td><td>Visible</td></tr><tr><td>Automatic Design</td><td>Available</td><td>Disabled</td></tr><tr><td>Variable Insertion</td><td>Available</td><td>Available</td></tr><tr><td>Block Validation</td><td>Disabled</td><td>Available</td></tr><tr><td>SYSTEM / USER / ASSISTANT</td><td>Invisible</td><td>Visible</td></tr><tr><td>Context parameter settings</td><td>Available</td><td>Available</td></tr><tr><td>PROMPT LOG</td><td>Available</td><td>Available</td></tr><tr><td>Stop_Sequences</td><td>Disabled</td><td>Available</td></tr></tbody></table>

## Operation Guide

### 1. How to enter the Expert Mode

After creating an application, you can switch to the **Expert Mode** on the prompt design page.

<figure><img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/000.png" alt=""><figcaption><p>Access to the <strong>Expert Mode</strong></p></figcaption></figure>

{% hint style="warning" %}
After moagentbaseing the prompts in the **Expert Mode** and publishing the application, you will not be able to revert back to the **Basic Mode**.
{% endhint %}

### 2. Moagentbase Context parameters

In both two modes, you can moagentbase the parameters for the inserting context, which includes **TopK** and **Score Threshold**.

<figure><img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/Context parameters.png" alt=""><figcaption><p>Context parameters</p></figcaption></figure>

{% hint style="warning" %}
Please note that only after uploading the context, the built-in prompts containing <img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/Context.png" alt="" data-size="line"> will be displayed on the prompt design page.
{% endhint %}

**TopK:** The value is an integer from 1 to 10.

It is used to filter the text fragments with the highest similarity to the user's query. The system will also dynamically adjust the number of fragments based on the context window size of the selected model. The default system value is 2. This value is recommended to be set between 2 and 5, because we expect to get answers that match the embedded context more closely.\\

**Score Threshold:** The value is a floating-point number from 0 to 1, with two decimal places.

It is used to set the similarity threshold for text segment selection, i.e., it only recalls text chunks that exceed the set score. By default, the system turns this setting off, meaning there's no filtering based on the similarity value of the recalled text chunks. When activated, the default value is 0.7. We recommend keeping this setting deactivated by default. If you have more stringent reply requirements, you can set a higher value, though it's not advisable to set it excessively high.

### 3. **Stop\_Sequences**

We do not expect the LLM to generate excessive content. Therefore, it's necessary to set specific words, phrases, or characters to signal the LLM to stop generating text. The default setting is `Human:` .For example, if you've written the _Few-Shot_ below:

```
Human1: What color is the sky?

Assistant1: The sky is blue.

Human1: What color is the fire?

Assistant1: The fire is red.

Human1: What color is the soil?

Assistant1: 
```

Then, in the model parameters, you need to locate `Stop_Sequences` and input `Human1:`. Do not forget to press the `Tab` key. In this way, the LLM will only respond with one sentence when replying instead of generating any extra dialogues:

```
The soil is yellow.
```

Because LLM stops generating content before the next `Human1:`.

### 4.Use "/" to insert Variables and Blocks

You can enter "/" in the text editor to quickly bring up Blocks to insert into the prompt.

<figure><img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/shortcut.png" alt=""><figcaption><p>shortcut "/"</p></figcaption></figure>

{% hint style="warning" %}
Except for `Variables`, other Blocks cannot be inserted repeatedly. In different applications and models, the Blocks that can be inserted will vary based on different prompt template structures.
{% endhint %}

### 5. Input Pre-prompt

The system's initial Prompt Template provides the necessary parameters and requirements for LLM's response. For more head to 👉 [prompt-template.md](prompt-template.md "mention").

The core of the early-stage development by developers is the Pre-prompt for the conversation. It requires designing built-in prompts, with the suggested insertion position below:

```
When answer to user:
- If you don't know, just say that you don't know.
- If you don't know when you are not sure, ask for clarification.
Avoid mentioning that you obtained the information from the context.
And answer according to the language of the user's question.

You are a customer service assistant for Apple Inc., and you can provide iPhone consultation services to users.
When answering, you need to list the detailed specifications of the iPhone, and you must output this information in a vertical {{Format}} table. If the list is too long, it should be transposed.
You are allowed to take a long time to think to generate a more reasonable output.
Note: You currently have knowledge of only a subset of iPhone models, not all of them.
```

You can also customize and moagentbase the initial prompt template. For example, if you want LLM's responses to be in English, you can moagentbase the built-in prompts as follows:

```
When answer to user:
- If you don't know, just say that you don't know.
- If you don't know when you are not sure, ask for clarification.
Avoid mentioning that you obtained the information from the context.
And answer according to the language English.
```

### 6. Check the Prompt Log

During debugging, you can not only check the user's input and LLM's responses but also view the complete prompts by clicking on the icon in the upper-left corner of the send message button. This makes it convenient for developers to confirm whether the input Variable content, Context, Chat History, and Query content meet expectations.

#### 6.1 Access to the Prompt Log

In the debugging preview interface, after engaging in a conversation with the AI, simply move the mouse pointer over any user session, and you will see the "Log" icon button in the upper-left corner. Click on it to view the Prompt Log.

<figure><img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/Access to the Prompt Log (1).png" alt=""><figcaption><p>Access to the Prompt Log</p></figcaption></figure>

In the Prompt Log, we can clearly see:

1. Complete built-in prompts.
2. Relevant text chucks referenced in the current session.
3. Historical session records.

<figure><img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/log1.png" alt=""><figcaption><p>Prompt Log</p></figcaption></figure>

From the log, we can view the complete prompts that have been assembled by the system and sent to LLM, and we can continuously improve prompt input based on debugging results.

#### 6.2 Trace Debugging History

In the initial application's main interface, you can find "Logs & Ann." in the left-side navigation bar. Clicking on it will allow you to view the complete logs. In the "Logs & Ann." main interface, you can click on any conversation log entry. In the right-side dialog box that appears, simply move the mouse pointer over the conversation and then click the "Log" button to check the Prompt Log.

For more head to 👉 [logs.md](../logs.md "mention") .

<figure><img src="/en/.gitbook/assets/guides/application_orchestrate/prompt-engineering/33333.png" alt=""><figcaption><p>Logs &#x26; Ann.</p></figcaption></figure>