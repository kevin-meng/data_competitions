# ATEC_Fraud_Detection


### 引言
   最近年底在整理资料，发现2018年的ATEC参赛记录总结 脱稿至今。当初说要写却迟迟未曾动笔，如今只能凭借依稀的记忆进行整理。

**赛题官网**：https://dc.cloud.alipay.com/index#/topic/data?id=4

- 初赛阶段，特征含义全部隐掉，不少毒特征。主要考验特征选择，与特征组合，业务经验难以发挥，整个过程上分艰难。
            庆幸队友给力，以初赛B榜Top7的成绩进了复赛。
- 复赛时期，基于主办方给35个初始交易信息，需要基于此进行特征挖掘识别欺诈交易。特征主要是通过写SQL, 模型训练平台 PAI。
            本次开源的是所有特征工程代码，其他数据模型均在PAI平台无法导出。


### 特征工程方面

- **1.特征编码**   
- **2.历史类特征** ：过去时间各类信息占比。
- **3.交叉熵特征** ：基于历史类特征，反映交易双方的概率分布差异。
- **4.当前小时特征** ：反映超短期集中性，针对集中性风险
- **5.滑窗类特征** ：窗口大小：1d、3d、5d，7d 针对短期集中性
- **6.做差特征** ：基于当前小时特征与滑窗特征衍射，计算交易金额的波动，反映客户交易习惯。
- **7.评分特征** ：将已判断的客户评分，作为先验知识，纳入模型特征，效果极佳
- **8.抽取特征** ：入模特征


开源代码中有段python脚本，它极大的提高了特征制作效率，配合官方的代码格式化，非常爽！


### 后记
因为失误，导致B榜最后一次提交时几个核心特征为空。最终成绩Top10；
在这里要感谢蚂蚁金服的@远水和@艾珈两位老师，帮忙重跑了修正特征后的模型结果（0.7692，Top6），虽然仍旧无缘决赛，但也算给大赛画上圆满句号. 

### 教训
参加大赛，在建模能力提高的同时，还收获了一个重要教训：

**时间再赶，也要做code review！**  
