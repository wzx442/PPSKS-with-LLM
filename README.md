# 隐私保护空间关键词搜索与大模型：2023—2026 文献综述

检索日期：2026-09-27。重点范围：2023-01 至 2026-09 的正式发表论文；少量近年预印本单列为前沿信号。本文把“空间关键词查询”定义为同时约束地理位置与文本条件的查询（范围、布尔、相似度或 top-k），把“加密语义检索”定义为在密文/受保护向量上检索语义近邻。后者是可迁移的技术邻域，不能自动算作前者的直接先例。

## 摘要与结论

近四年的主线从加密空间数据上的布尔范围查询，扩展到相似度、top-k、多维范围、可验证结果和访问/搜索/结果量模式保护。2025 年 SIGMOD 的 OBIR-tree 和 2026 年 ICDE 的 RISK 分别把“强泄露保护”和“多查询类型统一索引”推进到了数据库顶会。与此同时，2025 年 OSDI 的 Compass 证明，高质量语义检索可以与加密向量索引及 ORAM 协同设计。两条线在本次核验的 CCF A/B 正式论文中尚未形成一个成熟的“空间 + 语义/LLM + 可定义泄露”的统一系统。这是**基于本次覆盖范围的检索观察**，不是不存在相关论文或新颖性的证明。

对研究定位最重要的区分是：LLM 用于自然语言解析，只改善查询表达；嵌入模型用于语义匹配，改善召回；密码学协议和索引才决定云端能观察到什么。任何一层的性能或精度改进，都不能代替对其他层的安全论证。

## 论文速览

“CCF”按官网当前目录的场所类别标注；`—` 表示未以 A/B 身份纳入主线，或仅作为预印本观察。期刊按正式卷期年而非 online-first 年计。论文类型均依据摘要、正式页面或可用全文分类。

| 编号 | 论文与链接 | 场所/年份 | 类型 | 与课题的关系及阅读重点 |
| --- | --- | --- | --- | --- |
| S1 | [Efficient and Privacy-Preserving Spatial Keyword Similarity Query Over Encrypted Data](https://doi.org/10.1109/TDSC.2022.3227141) | TDSC 2023，CCF A | 纯方法 | PPSKS/PPSKS+；关键词集合相似度与访问模式保护。这里的“similarity”是集合相似度，不是 LLM 语义相似度。[作者稿](https://www.cs.unb.ca/~rlu1/paper/ZhangRLGZS22A.pdf)。 |
| S2 | [Privacy-Preserving Ranked Spatial Keyword Query in Mobile Cloud-Assisted Fog Computing](https://doi.org/10.1109/TMC.2021.3134711) | TMC 2023，CCF A | 纯方法 | 将空间范围与文本相关性结合做排序，并考虑多用户授权；注意“排序”并未引入现代文本嵌入。[机构记录](https://ink.library.smu.edu.sg/sis_research/8653/)。 |
| S3 | [RASK: Range Spatial Keyword Queries on Massive Encrypted Geo-Textual Data](https://doi.org/10.1109/TSC.2023.3289654) | TSC 2023，CCF A | 纯方法 | 对称 kd-tree 路径与倒排索引组合，强调大规模范围查询的检索成本。2026 年 RISK 直接拿它作为范围查询基线。[DBLP](https://dblp.org/rec/journals/tsc/LvSHLPWT23.html)。 |
| S4 | [Beyond Result Verification: Efficient Privacy-Preserving Spatial Keyword Query With Suppressed Leakage](https://doi.org/10.1109/TIFS.2024.3354414) | TIFS 2024，CCF A | 纯方法 | 布尔范围查询同时处理访问/搜索模式泄露和结果完整性；分布式点函数、Cuckoo hashing 与轻量验证。[机构全文记录](https://smusg.elsevierpure.com/en/publications/beyond-result-verification-efficient-privacy-preserving-spatial-k/)。 |
| S5 | [Performance Enhanced Secure Spatial Keyword Similarity Query With Arbitrary Spatial Ranges](https://doi.org/10.1109/TIFS.2024.3396384) | TIFS 2024，CCF A | 纯方法 | 延伸 S1 到任意空间范围，改进同态计算与分组式访问模式保护。阅读时比较其关键词相似度定义和安全/成本边界。[机构记录](https://commons.emich.edu/fac_sch2024/148/)。 |
| S6 | [PMRK: Privacy-Preserving Multidimensional Range Query With Keyword Search Over Spatial Data](https://doi.org/10.1109/JIOT.2023.3326004) | IEEE IoT Journal 2024 | 纯方法 | 多维范围与关键词匹配的统一查询表达；R-tree、编码、谓词加密。适合研究“自然语言谓词编译”的目标语言，而非 LLM 先例。[机构记录](https://scholars.hkbu.edu.hk/en/publications/pmrk-privacy-preserving-multidimensional-range-query-with-keyword/)。 |
| S7 | [Privacy-preserving Boolean range query with verifiability and forward security over spatio-textual data](https://doi.org/10.1016/j.ins.2024.120929) | Information Sciences 2024 | 纯方法 | 动态更新的前向安全与可验证性；用作动态场景补充，不与 A 类主线混同。[出版社](https://www.sciencedirect.com/science/article/abs/pii/S0020025524008430)。 |
| S8 | [OBIR-tree: An Efficient Oblivious Index for Spatial Keyword Queries on Secure Enclaves](https://doi.org/10.1145/3709708) | PACMMOD/SIGMOD 2025，CCF A 会议 | 纯方法 | IR-tree 与 PathORAM 协同，目标是 top-k 空间关键词查询时隐藏搜索、访问和结果量模式；SGX 是加速扩展。论文报告相对基线 25–723 倍加速，但这是其指定实验条件。[SIGMOD 页面](https://2025.sigmod.org/toc-3-1.html)。 |
| S9 | [RISK: Efficiently Processing Rich Spatial-Keyword Queries on Encrypted Geo-Textual Data](https://doi.org/10.1109/ICDE65706.2026.00173) | ICDE 2026，CCF A | 纯方法 | 用统一 kQ-tree 支持加密范围和 kNN 空间关键词查询；对“仅统一两类空间查询”的新工作构成直接先例。[DBLP](https://dblp.org/rec/conf/icde/LvCHCPLL26.html)、[可读作者稿](https://arxiv.org/abs/2602.20952)。 |
| V1 | [Compass: Encrypted Semantic Search with High Accuracy](https://www.usenix.org/conference/osdi25/presentation/zhu-jinhao) | OSDI 2025，CCF A | 系统/工具 | 加密文本嵌入、图索引遍历与 ORAM 协同设计，兼顾语义准确率与访问模式隐藏。它没有空间谓词，是“语义检索层”的最强近邻之一。[论文 PDF](https://www.usenix.org/system/files/osdi25-zhu-jinhao.pdf)。 |
| V2 | [Enabling efficient and accurate semantic search over encrypted cloud data](https://doi.org/10.1016/j.ins.2025.122437) | Information Sciences 2025 | 纯方法 | CESSE：上下文增强表示、ASPE 变换及近似近邻索引；直接贴近“嵌入 + 可检索变换”，但不是空间查询，也不是 LLM 安全保证。[出版社](https://www.sciencedirect.com/science/article/pii/S0020025525005699)。 |
| A1 | [Text Embeddings Reveal (Almost) As Much As Text](https://aclanthology.org/2023.emnlp-main.765/) | EMNLP 2023，CCF B | 纯方法（攻击） | 从文本嵌入反演原文；论文在其特定短文本设置中报告 32-token 输入有 92% 的精确恢复率，不能外推为所有模型/语料。是“嵌入不等于加密”的关键证据。 |
| A2 | [Found in Translation: A Generative Language Modeling Approach to Memory Access Pattern Attacks](https://www.usenix.org/conference/usenixsecurity25/presentation/jia-grace) | USENIX Security 2025，CCF A | 纯方法（攻击） | 生成式序列模型由页访问恢复对象访问；实验覆盖语义搜索服务。其威胁模型是机密计算页访问侧信道，不能直接等同普通 SSE 云端泄露，但提醒索引访问序列需要单独分析。 |

### 交叉方向的较弱/尚未定型证据

- [One multi-receiver certificateless searchable public key encryption scheme for IoMT assisted by LLM](https://doi.org/10.1016/j.jisa.2025.104011)，*Journal of Information Security and Applications*，2025：LLM 是医疗物联网应用场景，核心贡献是多接收方可搜索公钥加密/代理重加密；不支持把它表述为“LLM 实现空间语义检索”。
- [Enhancing Leakage Attacks on Searchable Symmetric Encryption Using LLM-Based Synthetic Data Generation](https://arxiv.org/abs/2504.20414)，2025 预印本：LLM 为关键词推断攻击生成辅助文档。它把 LLM 放在攻击者一侧，启示语义扩展可能改变频率和共现泄露；尚未核实正式 A/B 发表。
- [Efficient Privacy-Preserving Retrieval Augmented Generation with Distance-Preserving Encryption](https://arxiv.org/abs/2601.12331)，2026 预印本：与“距离保持的嵌入变换”高度贴近，但尚未核实正式发表及其安全主张。应作为对比与攻击评估对象。
- [Pointing the Way, Hiding the Destination: Practical Private Dense Retrieval at Scale](https://arxiv.org/abs/2608.25735)，2026-08 预印本：学习式候选过滤、加密重排序与不经意交付。对大规模私有稠密检索有参考价值，当前仅按预印本处理。

## 研究线索的合成

### 1. 空间词检索的安全目标已从“数据加密”走向“查询过程泄露”

S1 把关键词相似度与访问模式隐私纳入同一问题；S4 进一步连同搜索模式、结果验证讨论；S8 聚焦搜索、访问、结果量三类模式同时隐藏。因而新系统不能只写“坐标和词向量已加密”，还须明确服务器看到的路径、候选规模、结果标识、重复查询关系和更新轨迹。不同论文声称的安全性依赖其各自泄露函数、服务器模型和查询语义，不能直接按“IND-CKA2”“安全”字样横向排序。[S1](https://www.cs.unb.ca/~rlu1/paper/ZhangRLGZS22A.pdf)、[S4](https://smusg.elsevierpure.com/en/publications/beyond-result-verification-efficient-privacy-preserving-spatial-k/)、[S8](https://2025.sigmod.org/toc-3-1.html)。

### 2. 现有“相似度”不等于语义理解

S1/S5 的相似度围绕关键词集合；S2 是文本相关性排序；这些方法没有解决“安静、适合轮椅的咖啡馆”与对象描述之间的语义推断。V1/V2 引入文本向量近邻，解决语义匹配，却没有同时处理地理范围约束、空间拓扑及位置查询的泄露。因此可研究的连接点应是**带硬空间约束的安全语义排序**，并给出准确率、空间正确性、安全泄露和代价的联合评价，而不是把两套索引并排放置。[S1](https://doi.org/10.1109/TDSC.2022.3227141)、[S5](https://doi.org/10.1109/TIFS.2024.3396384)、[V1](https://www.usenix.org/conference/osdi25/presentation/zhu-jinhao)、[V2](https://doi.org/10.1016/j.ins.2025.122437)。

### 3. LLM 作为查询转换器：价值在可用性与可验证编译

可以让端侧 LLM 将自然语言编译成受约束的查询 AST，例如 `location ∈ polygon ∧ category=restaurant ∧ wheelchair_accessible=true ∧ semantic_score(description,q)≥τ`，再由确定性校验器检查地理单位、范围、多义地名、授权和谓词组合，最后生成加密 trapdoor。此设计可能减少**人工查询表达错误**；它本身不会自动减少云端泄露。若 LLM 把一个意图扩成多个同义词 trapdoor，搜索模式和共现信息可能反而增加。若调用外部 LLM，原始位置和意图在 LLM 服务方形成新的披露边界。上述是从系统模型推导的研究假设，不是现有论文已证明的结果。S6 提供复杂谓词目标，S4/S8 提供泄露对照。[S6](https://doi.org/10.1109/JIOT.2023.3326004)、[S4](https://doi.org/10.1109/TIFS.2024.3354414)、[S8](https://2025.sigmod.org/toc-3-1.html)。

### 4. “同构变换保护嵌入”的安全边界

若同构变换是正交矩阵 `Q`，则 `⟨Qx,Qy⟩=⟨x,y⟩`，欧氏距离也保持；服务器若能访问全部变换后向量，就能得到完整相似度矩阵、聚类和近邻图。它可隐藏坐标基，但不能单靠“矩阵保密”声称语义、成员或查询隐私。一般可逆线性变换也需要在辅助样本、已知明文和重复查询下做恢复攻击。A1 已表明原始文本嵌入具备可反演风险，V1 则把隐藏访问模式作为独立系统问题。这里的数学结论是直接推导；具体攻击成功率仍需实验。[A1](https://aclanthology.org/2023.emnlp-main.765/)、[V1](https://www.usenix.org/conference/osdi25/presentation/zhu-jinhao)。

## 可检验的研究空隙（推断，不作新颖性保证）

| 方向 | 已有覆盖 | 可检验的问题 | 必须比较的先例 |
| --- | --- | --- | --- |
| 带位置约束的私有语义 top-k | S8 强隐私空间 top-k；V1 强隐私语义检索 | 在空间范围是硬约束时，能否以一个联合索引控制候选和访问泄露，同时保持语义检索质量？ | S8、V1、S5、RISK；纯文本 BM25/稠密检索与明文空间过滤。 |
| 自然语言到安全谓词 | S6 有多维加密谓词；A2 展示侧信道攻击 | 端侧 LLM 编译查询能否提高组合查询表达正确率，并保证查询语义不扩大授权？错误/歧义怎样被拒绝？ | S6、S4；规则解析器、小模型、无 LLM 手工谓词。 |
| 变换向量的泄露测量与防御 | V2/ppRAG 类方案保留距离；A1 揭示反演风险 | 在已知少量地标/POI、已知查询和频率背景知识下，位置+语义向量还能被恢复多少？ | V2、A1、V1；正交变换、ASPE、ORAM/MPC/FHE 参照。 |

## 阅读次序与记录模板

1. **建立空间基线**：S1 → S5 → S4，逐篇记录查询语义、相似度定义、数据/查询/结果隐私和泄露函数。
2. **看数据库系统极限**：S8 → S9，比较“强模式隐藏”与“统一查询索引”的不同目标，抄录实验数据集、规模、基线和硬件假设。
3. **接上语义层**：V1 → V2 → A1，再读 A2；区分高质量检索、变换向量、反演和访问侧信道。
4. **做交叉问题表**：每一候选设计填五列：用户输入与地理语义、端/云信任边界、可观察泄露、Recall/nDCG/空间约束正确率、延迟/通信/内存。缺任一列，方向目前只是技术组合。

建议固定的单篇阅读卡：`问题与查询语义｜威胁模型｜密码学原语与索引｜泄露函数｜正确性/安全性证明｜数据集与规模｜基线与指标｜局限及能否迁移到 LLM 语义查询`。对“LLM 降低查询泄露”尤其应把“端侧/云侧推理”作为第一行条件写明。

## 检索与证据边界

本次使用公开关键词的交叉检索：`encrypted spatial keyword / geo-textual / spatial-textual`，`privacy-preserving range/top-k/similarity`，`encrypted semantic search / vector search / embedding inversion`，以及 `LLM + searchable encryption / spatial keyword / private RAG`。候选经 IEEE/ACM/SIGMOD/USENIX/ACL/出版社页、作者稿、机构库或 DBLP 核对。主要文献集中在 2023—2026，2026-09 之后才正式刊出的卷期未作为已发表成果纳入。检索服务的 OpenAlex/Semantic Scholar 匿名接口曾限流，因而“未找到直接 A/B 工作”仅限上述关键词和可核验来源，后续应补查引用链与新接收论文。文中未将搜索摘要单独作为正式论文存在性依据；无法确认的预印本已单列。

CCF 分类依据：[网络与信息安全](https://www.ccf.org.cn/Academic_Evaluation/NIS/)、[数据库/数据挖掘/内容检索](https://www.ccf.org.cn/Academic_Evaluation/DM_CS/)、[软件工程/系统软件](https://www.ccf.org.cn/Academic_Evaluation/TCSE_SS_PDL/)、[计算机网络](https://www.ccf.org.cn/Academic_Evaluation/CN/)、[人工智能](https://www.ccf.org.cn/Academic_Evaluation/AI/)。不同学校对 PACMMOD/SIGMOD 长文的认定可能有本校细则，应以培养单位规则为准。
