# 召回模式

当用户构建知识库问答类的 AI 应用时，如果在应用内关联了多个知识库，此时需要应用 AgentBase 的召回策略决定从哪些知识库中检索内容。

<figure><img src="../../../../img/zh-rag-multiple.png" alt=""><figcaption><p>召回模式设置</p></figcaption></figure>

### 召回设置

根据用户意图同时匹配所有知识库，从多路知识库查询相关文本片段，经过重排序步骤，从多路查询结果中选择匹配用户问题的最佳结果，需配置 Rerank 模型 API。在多路召回模式下，检索器会在所有与应用关联的知识库中去检索与用户问题相关的文本内容，并将多路召回的相关文档结果合并，并通过 Rerank 模型对检索召回的文档进行语义重排序。

在多路召回模式下，建议配置 Rerank 模型。你可以阅读 [重排序](https://docs.agentbase.ai/v/zh-hans/learn-more/extended-reading/retrieval-augment/rerank) 了解更多。

以下是多路召回模式的技术流程图：

<figure><img src="../../../.gitbook/assets/image (2) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1) (1).png" alt=""><figcaption><p>多路召回</p></figcaption></figure>

由于多路召回模式不依赖于模型的推理能力或知识库描述，该模式在多知识库检索时能够获得质量更高的召回效果，除此之外加入 Rerank 步骤也能有效改进文档召回效果。因此，当创建的知识库问答应用关联了多个知识库时，我们更推荐将召回模式配置为多路召回。