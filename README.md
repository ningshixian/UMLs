# UMLs
## 是什么是UMLS？
一体化医学语言系统。针对生物医学与健康领域的数据库系统、本体知识库

## UMLS的组成？
主要包含三个工具：超级叙词表、语义网络和专家词典
![](https://github.com/ningshixian/UMLs/blob/master/1.png)

1. 一个巨大的实体数据库：元数据词典（Metathesaurus）也叫超级叙词表？
概念名词知识库--  由许多不同的词典，分类，代码集，索引和编目生物医学文献组成，包括CPT®，ICD-10-CM，LOINC®，MeSH®，RxNorm和SNOMEDCT®
Meta 中分析的是概念含义， 目的是把表达相同概念的词串接起来，并在不同概念直接建立关系。
在Meta 中Metathesaurus包含超过五百万个术语或名称， 每一个概念都被指定一个概念识别码CUI， 数据存储在一系列关系表和文件中。Metathesaurus数据可以使用MetamorphoSys本地安装

2. 一个元数据词典中所有概念的关系集合：语义网络（Semantic Network）
语义网络由语义类型和语义关系组成。语义类型是广泛的科目类别，如疾病或综合征或临床药物。语义关系是语义类型之间存在的有用关系。例如：临床药物治疗疾病或综合征。语义网络用于帮助解释意义的应用程序。

3. 一个为自然语言处理系统提供的通用英语词典：专家词典（Specialist Lexicon）。
SPECIALIST词典是一个英文词典（词典），包括生物医学术语以及常见的英文单词。
SPECIALIST词汇和词汇工具一起使用户可以开发自然语言处理程序。

## UMLS 的支持性软件工具主要包括 
- MetamorphoSys、
- UMLS 知识源服务器 （the UMLS Knowledge Source Server，简称 UMLSKS）、
- UMLS 术语服务（UMLS  Terminology Services，简称 UTS）、
- 概念文本映射工具 MetaMap、
- 语义表达工具 SemRep 
- 词法变量生成程序（Lexical Variant Generation program，简称 lvg）。

# UMLS 的元数据词典(超级叙词表)介绍：

1. 超级叙词表的的概念表达的基本架构如图 2-1 所示采用了  概念(I 级)→术语 (II 级)→字符串(III 级)→原词（IV 级）四级结构模型。
![](https://github.com/ningshixian/UMLs/blob/master/2.png)
2. UMLS 的元数据词典是以概念为核心，依据概念（Concept, C）组织起来的。概念结构的设计方法是将同一概念的各种名称（同义词）和 变种形式（单复数、形容词等词性变体）联系在一起。一般来说，表达同一概念可以有多个术语（即同义词），而每一个术语又有 不同的词串表达方式，在超级叙词表中，多个术语体现为同义词，不同的词串 表达方式体现为词性变体。
3. 概念结构: CUI-LUI-SUI-AUI
（1）概念和概念标识符：每个概念被指定一个概念识别码（Concept Identifier, CUI），并给出了概念 类别和概念的描述文本。相同 CUI 代表概念的同义词集合。
（2）概念名称和字符串标识符：概念名称是指概念的术语表示形式；SUI
（3）来源术语和标识符：来源术语（Atom Identifier, AUI），相同的字符串AUI被连接到一个SUI
（4）原形化术语和标识符：（Lexical Identifier, LUI）每个字符串都要进行词汇的原形化处理，如复数转单数等，其目的是将同一术语的各种词汇变体形式连接到一起。

5. Metathesaurus数据文件
Metathesaurus 有40多个元数据和索引 数据文件。
下面列出的数据文件包含从源词汇获得的信息。概念唯一标识符（CUI）跨文件链接概念数据。下表说明了什么信息填充每个数据文件。
![](https://github.com/ningshixian/UMLs/blob/master/3.png)

6. MRCONSO.RRF 元数据项包括：
![](https://github.com/ningshixian/UMLs/blob/master/4.png)

7. MRREL.RRF      概念与词串的通用关系文档
     RB       广义关系
     RN       狭义关系
     PAR     直接上位关系     例如：CUI1|PAR|CUI2 表示第二个概念是第一个概念的直接上位词
     CHD     直接下位关系
     SIB       同位关系
     SY        同义关系
     RL        相似关系（无？）
     QA        限定关系
 共11种关系。
 
8. MRSTY.RRF      概念所属的语义类型文档
![](https://github.com/ningshixian/UMLs/blob/master/5.png)
![](https://github.com/ningshixian/UMLs/blob/master/6.png)
 
# 语义网络（Semantic Network）

语义网络提供了概念的一致性分类，即语义类型，以及更加详细的概念之间的语 义关系，其中语义类型具有树形层次等级结构特点，UMLS 以语义类型为点， 语义类型之间的语义关系为链构成了语义网络

1、133种语义类型以及54种语义关系
2、每个语义类型和语义关系都有唯 一的语义标识符(TUI)
3、语义类型采用了构思新 颖的树形等级结构，语义类型的最高层为实体（Entity）和事件（Event）两大 类
4、语义类型是网状结构中的节点，而语义关系则是将这些节点连接到一起的链
5、分为两大类：等级关系和相关关系
6、UMLS 语义网络中最常用的语义关系是 isa，它不仅确立了语义类型之间的 等级关系，而且也能被用来决定超级叙词表中的每个概念对应的具体语义类型
的分配。

# 专家词典（Specialist Lexicon）

专家词典提供了词汇相关信息 和很多用于自然语言处理的工具。

## UMLS 的支持性软件工具介绍
- UMLS 概念文本映射工具 MetaMap 与 MetaMap Transfer
可用来将生物医学 文本与 UMLS 中超级叙词表的概念间进行映射，标记文本中出现的超级叙词表 概念。

- UMLS 语义表达工具 SemRep
语义表达工具 SemRep 通过对 UMLS 专家词典的相关工具和自然语言处理 技术的应用，将生物医学文本进行词性上的标注和语句层次的切分，使用 MetaMap 对所获得的术语与 UMLS 超级叙词表概念之间进行映射，获得相应概念以及概念在语义网络中对应的语义类型和语义关系，并通过概念共现来获得此生物医学文本信息的主要论点，使用主语-谓词-对象语义表达形式将该文本主旨内容表现出来 。

----
# 词典利用
如何利用词典的知识用于生物医学实体识别和分类，包括以下几种方法：

## 实体表示学习
1. 从 PubMed 选择 在医学主题词（Medical Subject Headings, Mesh）中包含“疾病”（disease）、“基 因”（gene）和“药物”（drug）的文章，训练词向量；
2. 利用 UMLS 的元数据词典，学习生物医学实体表示。
    1. 利用词典中的概念描述文本和上述获得的词向量学习初始概念表示。采用 CBOW 模型/CNN 模型
    2. 利用词典的同一实体多种变体、不同实体同名、实体类型、上下位词等多方 面的语义相关性信息，利用自动编码机模型学习实体表示。

![](https://github.com/ningshixian/UMLs/blob/master/8.png)
    
## 将词典融入NN
为了解决OOV（Out-of-Vocabulary）问题，参考AAAI2018论文《Neural networks Incorporating Dictionaries for  Chinese Word Segmentation》

How to integrate dictionaries?
- We first define several feature templates to construct feature vectors for each character based on dictionaries and contexts.
- Then, two different methods that extend the Bi-LSTM-CRF are  proposed to introduce the feature vectors.

![](https://github.com/ningshixian/UMLs/blob/master/7.png)

