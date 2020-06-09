# 相关论文 (2018-2020)

## 基于知识图谱表示学习的

### 联合学习

+ Unifying Knowledge Graph Learning and Recommendation: Towards a Better Understanding of User Preferences  [Cao2019WWW.pdf](Cao2019WWW.pdf)

   KTUP  提出一种新的类似transH的模型捕获用户的偏好兴趣做图嵌入    

- Knowledge Graph Convolutional Networks for Recommender Systems  [HongweiWang2019WWW.pdf](HongweiWang2019WWW.pdf)

   提出知识图卷积网络（KGCN）以知识图谱中一个实体及其邻居实体作为一个感受野进行卷积 一个实体的表示包括邻居实体的信息。特征表示与用户表示传入预测函数预测概率

- RippleNet: Propagating User Preferences on the Knowledge Graph for Recommender Systems   [HongweiWang2018CIKM.pdf](HongweiWang2018CIKM.pdf)  

  用水波在水面传播模拟用户的兴趣在图谱上传播

- AKUPM: Attention-Enhanced Knowledge-Aware User Preference Model for Recommendation [Tang2019KDD.pdf](Tang2019KDD.pdf)

   利用实体链接技术把用户交互矩阵的item链接知识图谱上相应实体  实体用TransR嵌入  用自注意网络得到一组实体的表示  聚合带权的实体表示到用户上表示用户对输入项的关注（得到用户表示） 最后用用户表示和物品表示计算概率

- Learning Heterogeneous Knowledge Base Embeddings for Explainable Recommendation  [Ai2018.pdf](Ai2018.pdf)

  CFKG 生成可解释推荐 利用TransE的规则做嵌入   然后发现解释路径  提出在潜在空间构建实体软匹配的方式（构建中间实体连接头尾实体）以寻找解释路径 通过计算概率排序每条路径生成自然语言解释

- News Graph: An Enhanced Knowledge Graph for News Recommendation  [Liu2019CIKM.pdf](Liu2019CIKM.pdf )

  为新闻推荐提出NewsGraph 添加一组实体记录中主题上下文信息 在实体间添加基于用户点击和共同出现的关系 移除不相关实体  

  添加samenews 、sameuser 关系 和考虑出现在同一浏览会话中的实体捕获时间关系

  提取主题实体利用transE得到实体嵌入attention聚合后添加文档嵌入信息得到新的文档嵌入  

  用户特征通过用户点击文章的文章特征通过简单的随时间衰减计算平均得到

  最后通过用户特征和文档特征计算概率

### 交替学习

+ Multi-Task Feature Learning for Knowledge Graph Enhanced Recommendation  [Wang2019WWW.pdf](Wang2019WWW.pdf)

  MKR 在推荐任务和图嵌入任务之间加一个模块交叉共享特征信息，最后交替完成学习

+ KGAT: Knowledge Graph Attention Network for Recommendation [Wang2019KDD.pdf](Wang2019KDD.pdf)

  定义协作知识图 把用户交互矩阵和知识图谱结合起来   用TransR嵌入协作知识图  传入注意嵌入传播层（利用节点邻居来更新自己表示捕获传播信息，并通过知识感知机制加权每个邻居）最后传入预测函数预测概率  最后交替优化

### 依次学习

+ DKN: Deep Knowledge-Aware Network for News Recommendation  [Wang2018WWW.pdf](Wang2018WWW.pdf)

  DKN  先做图嵌入任务，利用得到的特征进行推荐

## 基于知识图谱路径信息的

- A Knowledge-Aware Attentional Reasoning Network for Recommendation [Zhu2020AAAI.pdf](Zhu2020AAAI.pdf)

   通过用户的历史兴趣和用户和物品的路径信息计算概率

   物品实体表示（该实体和相关实体信息都考虑  卷积网络）-》 用户历史兴趣（SRA 循环网络和attention 提取用户点击序列特征）-》从用户-物品对中提取用户潜在的意图（A-SRA   提取每条路径特征 再加权融合）

     拼接历史兴趣和潜在意图激活后作为用户特征与物品特征计算激活得到概率

- Explainable Reasoning over Knowledge Graphs for Recommendation  [Wang2019AAAI.pdf](Wang2019AAAI.pdf)

   KPRN组合实体和关系的语义生成路径表示，通过路径的顺序依赖关系对路径进行推理，来推断用户和物品交互的基本原理

   KPRN= 嵌入+lstm+pooling  

   嵌入表示实体  lstm捕获实体路径基于关系上的语义 pool结合多条路径最终得到分数

- Recurrent knowledge graph embedding for effective recommendation  [Sun2018ISWC.pdf](Sun2018ISWC.pdf)

   RKGE 采用循环神经网络捕获实体表示和路径语义  通过池化操作判断路径重要性并聚合所有路径得到用户和物品间的关系（相似度）作为推荐概率

- Jointly Learning Explainable Rules for Recommendation with Knowledge Graph  [Ma2019WWW.pdf](Ma2019WWW.pdf)

   通过知识图谱学习物品之间的规则再通过规则和历史交互记录推荐

## 其他利用知识图谱的

+ Reinforced Negative Sampling over Knowledge Graph for Recommendation [Wang2020WWW.pdf](Wang2020WWW.pdf)     

  通过知识图谱提取负样本，“物品i，j 通过e相关联，如果e是用户对物品i感兴趣的重要因素，j可能已经通过其他方式（例如搜索、营销或广告系统）暴露于用户，但他没选j说明比起i他更喜欢j，j就作为负样本。” 

+ Layered Graph Embedding for Entity Recommendation using Wikipedia in the Yahoo! Knowledge Graph   [Ni2020WWW.pdf](Ni2020WWW.pdf)  

  在多层图上deepwalk提取特征  word2vec/doc2vec提取语义特征 

+ Content based News Recommendation via Shortest Entity Distance over Knowledge Graphs  [Kevin2019WWW.pdf](Kevin2019WWW.pdf)

  基于新闻内容提取实体生成知识子图 通过子图节点距离相似度做推荐


+ Knowledge-aware Graph Neural Networks with Label Smoothness Regularization for Recommender Systems  [HongweiWang2019KDD.pdf](HongweiWang2019KDD.pdf)

  把知识图谱转化成针对用户的权重图（代表了用户兴趣) 用关系打分函数计算关系r对用户u的重要性（边权重） 再考虑用户关系函数更新实体表达 最后传入预测函数预测概率

  标签平滑正则化：以往的GNN边权重是固定的  论文里是可学习的，然后为了防止过拟合提出了Label Smoothness Regularization

+ Computing recommendations via a Knowledge Graph-aware Autoencoder  [Vito2019ISWC.pdf](Vito2019ISWC.pdf)

  对每个用户用基于知识图谱的自编码器捕获潜在特征表示 找到与之相似的用户根据相似用户打分预测打分值

+ Knowledge-aware Autoencoders for Explainable Recommender Systems [Vito2018RecSys.pdf](Vito2018RecSys.pdf)    

  利用基于知识图谱自编码器构建用户特征

+ Knowledge-aware Recommender System for Software Development  [Phuong2018RecSys.pdf](Phuong2018RecSys.pdf)  

  任务：推荐调用的api函数   软件开发相关

+ Learning and Reasoning on Graph for Recommendation  [Wang2019CIKM.pdf](Wang2019CIKM.pdf)  

  利用图的推荐系统报告

+ KB4Rec: A Dataset for Linking Knowledge Bases with Recommender Systems  [Zhao2018CIKM.pdf](Zhao2018CIKM.pdf)

  提出为推荐系统构建的KB4Rec知识库  连接三个推荐数据集和一个知识图谱

## 异构信息网络 HIN

- Metapath-guided Heterogeneous Graph Neural Network for Intent Recommendation [Fan2019KDD.pdf](Fan2019KDD.pdf)

- IntentGC: A Scalable Graph Convolution Framework Fusing Heterogeneous Information for Recommendation  [Zhao2019KDD.pdf](Zhao2019KDD.pdf)

- An Attentional Recurrent Neural Network for Personalized Next Location Recommendation  [Guo2020AAAI.pdf](Guo2020AAAI.pdf)   

  基于路径的    任务：预测下一个位置   在图谱上随机游走发现基于异构信息元素的邻居坐标

- Motif Enhanced Recommendation over Heterogeneous Information Network [Zhou2019CIKM.pdf](Zhou2019CIKM.pdf)

- Relation-Aware Graph Convolutional Networks for Agent-Initiated Social E-Commerce Recommendation  [Xu2019CIKM.pdf](Xu2019CIKM.pdf)

