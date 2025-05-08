# new onchain需求结构化整理

## 一、产品概述

### 1. 产品背景

基于原有Onchain框架文档的内容，我们可以总结出Onchain新板块的主要背景：

**需求背景**

- 增加更多的Onchain用户
- 让现有Onchain用户做更多Onchain Action并获得直接奖励
- 激励现有的Offchain用户学习和转向Onchain
- 通过运营体系和邀请裂变，做新增的Onchain用户
- 跑通B端的CPS投放Onchain Task模式，增加收入

> 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)

**市场数据**

- 历史上所有做过Onchain Quest的用户约74万人
- 其中约10万人在最近一个月(4月)有行为记录
- 这部分活跃用户是重要的种子用户，是新板块的核心受众

> 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)

**Onchain任务分类**

- 优先级P0：Hold Token、Swap、Bridge
- 优先级P1：Hold NFT、Mint NFT、Stake、Smart Contract
- 优先级P2：Provide LP/Hold LP、Borrow/Supply

> 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)

### 2. 产品愿景

根据需求文档的内容，可以提炼出以下产品愿景：

- **打造完整的Onchain用户生态**：构建一个能够让用户便捷参与各类链上活动的平台
- **建立精准推荐机制**：让运营能够精准定位用户群体，提供个性化的Onchain任务推荐
- **提高平台用户的链上活跃度**：通过多样化的链上活动和奖励机制，提高用户参与度
- **建立可持续的B端价值循环**：通过CPS模式，为B端提供精准的用户群体，实现投放效果最大化
- **形成闭环的Onchain运营体系**：从用户获取、活跃到变现，形成完整的运营链路

> 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)、[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)

### 3. 用户故事

基于所有文档内容，可以总结出以下几类用户故事：

**C端用户故事**

- 作为一名链上用户，我希望通过简单的操作就能参与各类链上活动，以获得相应的奖励
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)、[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 作为一名持有特定代币的用户，我希望能够通过持币获得额外奖励，增加我持有代币的价值
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 作为一名新手用户，我希望能够通过教育任务了解区块链知识，并通过实际操作学习链上交互
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >
- 作为一名活跃用户，我希望能够看到适合我的任务推荐，避免错过感兴趣的活动
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 作为一名持有不同链钱包的用户，我希望能够使用相应的钱包参与不同链上的活动
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >

**B端用户故事**

- 作为一个项目方，我希望能够创建自定义的链上活动，吸引用户参与并提高项目曝光度
  > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
  >
- 作为一个DEX项目方，我希望能够设置特定的Swap活动，增加平台交易量并获取新用户
  > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
  >
- 作为一个Bridge项目方，我希望吸引用户跨链交互，增加项目使用率
  > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
  >
- 作为一个投放方，我希望能够实时查看活动数据，了解投放效果并进行调整
  > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
  >
- 作为一个项目方，我希望对投放活动有明确的预算控制和参与人数限制
  > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
  >

**运营方用户故事**

- 作为一名运营人员，我希望能够方便地创建和管理各类链上活动
  > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
  >
- 作为一名运营人员，我希望能够设置精准的用户推荐规则，让内容触达目标用户
  > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
  >
- 作为一名平台管理员，我希望能够审核B端创建的活动，确保内容符合平台规则
  > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
  >
- 作为一名数据分析人员，我希望能够看到详细的活动数据，评估活动效果
  > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
  >
- 作为一名运营人员，我希望能够管理活动的置顶和排序权重，实现精准运营
  > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
  >

## 二、业务流程

### 1. 全局业务流程图

根据文档内容，可以总结出两个主要的业务流程：

**Onchain Action推送工作流**

1. 运营在后台创建action
2. 创建action需要审批
3. 审批通过就会出现在新板块
4. 运营在后台设置推荐目标用户
5. C端目标用户会看到推荐弹窗
6. C端点击推荐弹窗，跳转到做action的页面
7. C端用户完成action，立刻获得奖励
8. 运营在后台能查看相关完成数据

> 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)

**B端投放task工作流**

1. B端用户在B端页面看到菜单入口，暂命名为Onchain Boost
2. B端创建一个Onchain Task，必须是Token奖励并Deposit
3. 运营在后台看到当前投放列表
4. 如果action涉及新合约，需要走合约审核流程
5. 如果action不涉及新合约，运营可以选择接受，之后这个接受行为要审批
6. 如果运营判断该action不合理无法完成，可以直接拒绝，拒绝也要审批，自动退款
7. 运营投放之后，能实时查看完成人数
8. B端也能实时查看完成人数
9. 如果到时间还完成不了，走手动退款流程

> 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)、[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)

### 2. 关键子流程图

**C端用户任务参与流程**

C端用户体验流程主要分为以下几个关键节点：

1. 用户进入Onchain板块（通过导航栏入口或首页展示模块）
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >
2. 用户浏览可用Action列表
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >
3. 用户选择参与特定Action（可能是Swap、Bridge或Hold Token等类型）
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >
4. 用户完成Action步骤（可能包含教育内容、Quiz、链上操作等）
   > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
   >
5. 用户领取奖励
   > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
   >
6. 用户可能被推荐其他相关Action
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >

其中，不同类型Action的具体流程有所不同：

**Swap/Bridge任务流程**

- 用户点击Start开始任务
- 用户进入详情页并完成操作
- 用户点击Verify验证操作
- 验证通过后用户领取奖励

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)、[任意Swap任务.md](./任意Swap任务.md)

**Hold Token任务流程**（带持有天数要求）

- 用户点击Start开始任务
- 系统检查用户是否持有足够代币
- 如果满足条件，开始记录持有时间
- 用户需要定期刷新以确认仍然持有代币
- 持有满指定天数后，用户可以领取奖励

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

**Hold Token任务流程**（不带持有天数要求）

- 用户点击Start开始任务
- 系统检查用户是否持有足够代币
- 如满足条件，用户可以直接领取奖励
- 不满足条件则引导用户通过Swap获得所需代币

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

**Action Collection参与流程**

- 用户点击Start开始Collection任务
- 用户依次完成Collection中的多个Action
- 每完成一个Action获得相应奖励
- 完成所有Action后标记Collection为完成状态

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

## 三、功能设计

### 1. 功能地图

根据所有文档内容，可以梳理出以下功能模块：

**C端功能模块**

- Onchain落地页

  - 导航栏入口
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
  - 首页推荐模块
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
  - Action列表
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
  - Action卡片展示
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
  - 教育板块
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
  - 统计数据展示
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
  - 工单入口
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
- Action详情页

  - 详情页框架
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
  - 教育UI
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
  - Quiz UI
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
  - 内嵌执行UI
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
  - 奖励展示/领取
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
  - Collection展示
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
- 执行功能

  - Bridge内嵌执行
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
  - Swap执行
    > 来源：[任意Swap任务.md](./任意Swap任务.md)
    >
  - Hold Token验证
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
  - 任务进度追踪
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >

**B端功能模块**

- Onchain Boost
  - 入口和落地页
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
  - Request创建
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
  - Request列表
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
  - Request状态跟踪
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
  - 预算管理
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >

**运营后台功能模块**

- Request管理

  - Request列表
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
  - Request详情
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
  - Request审批流程
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
  - Request状态管理
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
- Action管理

  - Action列表
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
  - Action创建
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
  - Action审批
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
  - Action状态管理
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
  - Action排序
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
- Collection管理

  - Collection列表
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
  - Collection创建
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
  - Collection展示控制
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
- 精准推荐

  - 用户标签创建
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
  - 投放触点设置
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
  - 用户筛选
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
  - 运营效果分析
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >

### 2. 功能描述模板

按照核心功能模块和用户主流程，可整理出以下功能描述：

#### C端 Onchain 落地页

**功能概述**：
提供用户探索和参与各类链上活动的主要入口，展示可参与的Action列表，追踪用户获得的奖励和进度。

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

**主要组件**：

- 导航栏入口：在导航栏增加⚡️ Onchain入口
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 首页推荐模块：在首页Quest模块下方展示Top 3 Onchain Action
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 头部信息板块：包括功能介绍、Token奖励总值和用户黄金积分数量
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- Action列表：展示可参与的Action和Collection
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- In Progress快速筛选：显示用户正在参与的Action
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 教育板块：展示徽章墙和相关教育内容
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >

**交互逻辑**：

- 点击导航栏Onchain入口或首页"View All"按钮进入Onchain主页
- 默认显示所有进行中的可见Action，支持下拉加载更多
- 点击Action卡片进入详情页
- 点击In Progress按钮筛选正在参与的Action
- 点击徽章可查看相关教育内容

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

**Action卡片展示规则**：

- 按照排序规则显示Action卡片
- 基于Action类型(Swap/Bridge/Hold Token/Collection)显示不同UI
- 根据用户参与状态展示不同交互界面

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

#### Action详情页

**功能概述**：
提供用户参与单个Action的完整流程界面，包括任务介绍、执行步骤、验证和奖励领取。

> 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)

**主要组件**：

- Action标题区：展示Logo和标题
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >
- Action信息区：包含时间、参与信息和用户进度
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >
- 奖励展示区：显示可获得的奖励
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >
- 主操作区：展示各种Step的UI和领奖界面
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >

**交互逻辑**：

- 用户通过点击Action卡片进入详情页
- 根据Step类型展示不同的操作界面
- 完成所有Step后展示领奖界面
- 领取奖励后可能推荐其他Action

> 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)

**特殊状态处理**：

- 未登录状态：显示登录提示
- 判定为机器人：提示进行POH认证
- 判定为新用户：引导POH认证

> 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)

#### B端Onchain Boost

**功能概述**：
允许B端用户创建和管理Onchain任务，指定任务类型、目标和预算，追踪任务执行效果。

> 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)

**主要流程**：

1. **创建Request**

   - 选择任务类型(Swap/Bridge/Hold Token)
   - 设置任务参数
   - 设置目标指标(Target Wallets/Volume/Transactions)
   - 配置预算和时间安排

   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
2. **跟踪Request状态**

   - 查看Request列表
   - 监控任务进度和指标完成情况
   - 管理预算使用

   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
3. **Request状态管理**

   - Pending：等待运营审核
   - Canceled：B端取消
   - Rejected：运营拒绝
   - Ongoing：进行中
   - Completed：已完成
   - Expired：已过期

   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
4. **数据分析**

   - 查看用户参与情况
   - 查看交易明细
   - 跟踪指标完成进度

   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >

#### 运营后台工具

**功能概述**：
提供运营团队创建、审核和管理所有Onchain活动的工具，包括B端Request管理、Action创建和推荐设置。

> 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)

**主要组件**：

1. **Request管理**

   - Request列表：查看和筛选所有Request
   - Request详情：查看单个Request的完整信息
   - Request操作：接受/拒绝/管理Request

   > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
   >
2. **Action管理**

   - Action创建：设置基本信息、步骤、奖励和资格条件
   - Action列表：管理所有Action
   - Action状态控制：Draft/Pending/Upcoming/Live/Expired

   > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
   >
3. **Collection管理**

   - Collection创建：设置标题、布局和Action组合
   - Collection列表：管理所有Collection
   - 可见性控制：设置C端可见性

   > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
   >

- 精准推荐
  - 用户标签创建
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
  - 投放触点设置
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
  - 用户筛选
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
  - 运营效果分析
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >

### 2. 功能描述模板

按照核心功能模块和用户主流程，可整理出以下功能描述：

#### C端 Onchain 落地页

**功能概述**：
提供用户探索和参与各类链上活动的主要入口，展示可参与的Action列表，追踪用户获得的奖励和进度。

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

**主要组件**：

- 导航栏入口：在导航栏增加⚡️ Onchain入口
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 首页推荐模块：在首页Quest模块下方展示Top 3 Onchain Action
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 头部信息板块：包括功能介绍、Token奖励总值和用户黄金积分数量
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- Action列表：展示可参与的Action和Collection
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- In Progress快速筛选：显示用户正在参与的Action
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 教育板块：展示徽章墙和相关教育内容
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >

**交互逻辑**：

- 点击导航栏Onchain入口或首页"View All"按钮进入Onchain主页
- 默认显示所有进行中的可见Action，支持下拉加载更多
- 点击Action卡片进入详情页
- 点击In Progress按钮筛选正在参与的Action
- 点击徽章可查看相关教育内容

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

**Action卡片展示规则**：

- 按照排序规则显示Action卡片
- 基于Action类型(Swap/Bridge/Hold Token/Collection)显示不同UI
- 根据用户参与状态展示不同交互界面

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

#### Action详情页

**功能概述**：
提供用户参与单个Action的完整流程界面，包括任务介绍、执行步骤、验证和奖励领取。

> 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)

**主要组件**：

- Action标题区：展示Logo和标题
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >
- Action信息区：包含时间、参与信息和用户进度
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >
- 奖励展示区：显示可获得的奖励
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >
- 主操作区：展示各种Step的UI和领奖界面
  > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
  >

**交互逻辑**：

- 用户通过点击Action卡片进入详情页
- 根据Step类型展示不同的操作界面
- 完成所有Step后展示领奖界面
- 领取奖励后可能推荐其他Action

> 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)

**特殊状态处理**：

- 未登录状态：显示登录提示
- 判定为机器人：提示进行POH认证
- 判定为新用户：引导POH认证

> 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)

#### B端Onchain Boost

**功能概述**：
允许B端用户创建和管理Onchain任务，指定任务类型、目标和预算，追踪任务执行效果。

> 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)

**主要流程**：

1. **创建Request**

   - 选择任务类型(Swap/Bridge/Hold Token)
   - 设置任务参数
   - 设置目标指标(Target Wallets/Volume/Transactions)
   - 配置预算和时间安排

   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
2. **跟踪Request状态**

   - 查看Request列表
   - 监控任务进度和指标完成情况
   - 管理预算使用

   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
3. **Request状态管理**

   - Pending：等待运营审核
   - Canceled：B端取消
   - Rejected：运营拒绝
   - Ongoing：进行中
   - Completed：已完成
   - Expired：已过期

   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
4. **数据分析**

   - 查看用户参与情况
   - 查看交易明细
   - 跟踪指标完成进度

   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >

#### 运营后台工具

**功能概述**：
提供运营团队创建、审核和管理所有Onchain活动的工具，包括B端Request管理、Action创建和推荐设置。

> 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)

**主要组件**：

1. **Request管理**

   - Request列表：查看和筛选所有Request
   - Request详情：查看单个Request的完整信息
   - Request操作：接受/拒绝/管理Request

   > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
   >
2. **Action管理**

   - Action创建：设置基本信息、步骤、奖励和资格条件
   - Action列表：管理所有Action
   - Action状态控制：Draft/Pending/Upcoming/Live/Expired

   > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
   >
3. **Collection管理**

   - Collection创建：设置标题、布局和Action组合
   - Collection列表：管理所有Collection
   - 可见性控制：设置C端可见性

   > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
   >

- 精准推荐
  - 用户标签创建
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
  - 投放触点设置
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
  - 用户筛选
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
  - 运营效果分析
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >

## 四、业务规则

### 1. 业务规则概述

Onchain模块业务规则主要涵盖以下几个方面：

- Action和Collection的创建、审批和管理规则
- 用户参与资格和验证规则
- 奖励发放和计算规则
- 排序和展示规则
- B端Request管理和预算规则

### 2. 业务规则列表模板

#### Action卡片排序规则

**排序规则分三层**：

**第一层：基础排序**

- 先把已结束的和用户已领取奖励的Action或Action集合排序靠后
- 所有被人工置顶的Action或Action集合统一排在列表最前面，置顶项内部保持人工设置的顺序

**第二层：奖励价值排序**

- 剩下的先按奖励价值进行排序，然后再根据排序系数进行排序

奖励价值排序逻辑:

1. 奖励Token美元总值（降序）- 数值越大越靠前
2. 若奖励Token为0，则按黄金积分总值降序排序
3. 若奖励黄金积分为0，则按积分总值降序排序

排序系数逻辑:

- 默认是1，即在奖励价值排序的基础上，不调整任何排序
- 系数值越低，排序越靠后

**第三层：相对排名计算**
计算公式：相对排名 = 奖励排名 / 排序系数
最终排名按相对排名进行升序排列

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

#### Hold Token任务规则

**Hold Token + 天数规则**：

- 用户需满足两个条件：持有指定数量的代币+持有指定的天数
- 系统会定期检查用户的代币余额，确保用户在整个持有期间都满足持币要求
- 如果在持有期间任何时候不满足持币要求，用户需要重新开始计时
- 满足持有天数要求后，用户方可领取奖励

**Hold Token不加天数规则**：

- 用户只需要满足持有指定数量的代币的条件
- 系统检查用户的代币余额，如满足条件即可领取奖励
- 不满足条件则引导用户通过Swap获得所需代币

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)、[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)

#### Action状态定义规则

**Action状态规则**：

- Draft：草稿状态
- Pending：运营创建完点击Apply后，且未被审核完成发布的状态
- Upcoming：Action已经Publish但是当前还未开始，C端不可见
- Live：Action已经Publish且当前已开始，C端可见
- Expired：Action过期，C端不可见

**Collection状态规则**：

- Draft：草稿状态
- Visible：C端可见
- Hidden：C端列表页不可见，使用链接访问页面不可交互且带有遮罩

> 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)

#### Request状态管理规则

**Request状态规则**：

- Pending：B端成功发起Request，B端和运营都没有进行处理的状态
- Canceled：B端主动取消发起的Request
- Rejected：运营拒绝B端发起的Request
- Ongoing：运营接受B端发起的Request
- Completed：运营标记B端发起的Request为完成状态
- Expired：时间结束时B端Request的核心指标未能完成

> 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)、[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)

#### 奖励展示规则

**多种类型奖励的情况下显示优先级**：
奖励类型优先级: Token奖励 > Badge > Gold XP > XP

**主奖励展示规则**：

- Token：显示总共token奖励等值美元价值，右侧logo采用TaskOn设计的token logo
- Badge：显示badge名称，右侧logo采用badge图片
- Gold XP：显示总共奖励的gold xp数量，右侧logo采用gold xp logo
- XP：显示总共奖励的xp数量，右侧logo采用xp logo

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)、[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)

#### 任意Swap任务规则

**任务特性**：

- 支持多个链上执行，包括EVM、Berachain(EVM)、Sonic(EVM)、Solana、SUI、TON、Aptos
- 可指定或不指定DEX，不指定时使用TaskOn聚合器
- Quest和GTC Task展示规则不同

**B端UI**：

- 任务模板名为"Swap Token"
- 基础字段与Swap一致
- 新增字段"Swap Through Specified DEX"，默认关闭
- 开启后出现DEX下拉选项

**C端展示**：

- 如果B端指定了DEX，展示与现有Swap一致
- 如果B端没有指定DEX，Quest和GTC Task中任务名最后的"on [DEX]"移除
- Quest中的Swap文案增加下划线，点击打开通用Swap组件

> 来源：[任意Swap任务.md](./任意Swap任务.md)

## 五、数据需求

### 数据流说明

根据文档中的数据统计需求，需要按Action_id和Action_collection_id粒度统计以下数据：

**Action_id粒度统计**：

- Action详情页查看人数：Action弹窗查看用户数
- Action参与人数：完成Action中至少1个step的用户数
- Action完成人数：完成Action中所有step的用户数
- Holding Action (包含天数) 参与人数：Holding天数至少1天的用户数
- Holding Action (包含天数) 完成人数：Holding天数完成要求的用户数
- Holding Action (包含天数) 领奖人数：Holding天数完成要求且完成领奖的用户数

**Action_collection_id粒度统计**：

- Action_collection详情页查看人数：Action_collection弹窗查看用户数
- Action_collection参与人数：完成Action_collection中至少1个Action的用户数
- Action_collection完成人数：完成Action_collection中所有Action的用户数

**B端数据统计**：

- 钱包地址统计
- 交易相关数据：链、代币、数量、时间、交易哈希
- Hold Token状态追踪
- 每日数据变化趋势图

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)、[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)

**其他统计需求**：

- 导航栏按钮点击的PV和UV
- Home组件点击的PV和UV
- 各步骤完成/未完成比例
- 用户设备和钱包类型分布
- 用户参与时段分布

> 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)

## 六、埋点需求

根据需求文档，以下是关键埋点需求点：

**页面浏览埋点**：

- Onchain落地页访问
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >

**操作行为埋点**：

- 导航栏Onchain入口点击
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- 首页Onchain模块卡片点击
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >

**数据统计需求**：

- 导航栏按钮点击的PV和UV
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >
- Home组件点击的PV和UV
  > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
  >

这些埋点将帮助分析用户行为路径、任务完成率、活动效果，并为后续优化提供数据支持。

> 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)

## 七、开发任务拆解

根据产品需求和业务优先级，以下是开发任务的拆解，按照业务重要性排序。

#### 前端任务

1. **Onchain导航栏入口与首页模块开发**

   - 实现导航栏Onchain入口
   - 开发首页推荐模块展示Top 3 Action

   > 依赖：无
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >
2. **C端Onchain落地页框架与Action列表**

   - 开发落地页整体框架
   - 实现Action列表展示及分页加载
   - 实现In Progress快速筛选功能

   > 依赖：API接口
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >
3. **Action卡片组件开发**

   - 基于不同类型Action(Swap/Bridge/Hold Token)开发卡片UI
   - 实现卡片状态展示和交互逻辑

   > 依赖：API接口
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >
4. **Action详情页框架与基础UI**

   - 开发Action详情弹窗框架
   - 实现标题区、信息区、奖励展示区UI

   > 依赖：API接口
   > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
   >
5. **Hold Token任务UI与交互实现**

   - 开发Hold Token验证UI
   - 实现持有验证逻辑
   - Hold Token天数要求的持有验证与倒计时

   > 依赖：验证API
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)、[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
6. **Swap任务UI与交互实现**

   - 开发Swap内嵌执行UI
   - 实现Swap操作流程和验证
   - 不指定DEX的通用Swap组件

   > 依赖：Swap接口
   > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)、[任意Swap任务.md](./任意Swap任务.md)
   >
7. **奖励领取UI与交互**

   - 开发奖励展示和领取界面
   - 实现奖励领取后的状态更新

   > 依赖：奖励API
   > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
   >
8. **B端Onchain Boost入口与列表页**

   - 实现B端Onchain Boost菜单入口
   - 开发Request列表展示

   > 依赖：API接口
   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
9. **B端创建Request流程（基础任务类型）**

   - 开发任务类型选择UI
   - 实现Swap/Bridge/Hold Token三种基础任务的创建表单

   > 依赖：API接口
   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
10. **埋点实现（前端）**

    - 实现用户行为埋点（页面访问、按钮点击）
    - 集成导航栏和首页按钮点击的PV/UV统计

    > 依赖：埋点API
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
11. **运营后台Request管理**

    - 开发Request列表与详情页
    - 实现审批流程UI

    > 依赖：API接口
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
12. **运营后台Action管理**

    - 开发Action创建与编辑界面
    - 实现Action排序与状态管理

    > 依赖：API接口
    > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
13. **Collection展示与管理**

    - 开发Collection卡片展示
    - 实现Collection详情页与进度展示

    > 依赖：API接口
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)、[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
    >
14. **Collection完成逻辑实现（前端）**

    - 开发多Action依序完成的交互流程
    - 实现Collection进度追踪与完成状态显示
    - 实现每个步骤完成后的奖励展示

    > 依赖：Collection API
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
15. **Bridge任务UI与交互实现**

    - 开发Bridge内嵌执行UI
    - 实现Bridge操作流程和验证

    > 依赖：Bridge接口
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)、[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
16. **B端数据统计页面**

    - 开发投放效果数据展示
    - 实现指标完成进度图表

    > 依赖：数据统计API
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
17. **教育UI与Quiz模块**

    - 开发教育内容展示UI
    - 实现Quiz答题交互

    > 依赖：API接口
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
18. **工单入口与创建流程**

    - 开发Onchain板块工单入口
    - 实现工单提交表单与流程

    > 依赖：工单系统API
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
19. **任意Swap任务高级功能**

    - 开发不指定DEX的高级功能
    - 实现多链支持UI（EVM、Berachain、Sonic、Solana、SUI、TON、Aptos）

    > 依赖：Swap接口
    > 来源：[任意Swap任务.md](./任意Swap任务.md)
    >
20. **用户精准推荐UI**

    - 开发推荐Action弹窗
    - 实现个性化推荐展示

    > 依赖：推荐API
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
21. **教育板块徽章墙**

    - 开发徽章墙UI
    - 实现徽章获取与展示逻辑

    > 依赖：徽章API
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
22. **C端数据展示与统计**

    - 开发用户奖励统计展示
    - 实现参与历史记录

    > 依赖：统计API
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
23. **B端预算管理功能**

    - 开发预算设置与管理UI
    - 实现预算消耗统计

    > 依赖：预算API
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
24. **多种钱包连接优化**

    - 优化钱包连接体验
    - 实现多链钱包支持

    > 依赖：钱包服务
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >

#### 后端任务

1. **Action数据模型与基础API**

   - 设计Action数据模型
   - 实现Action列表、详情API

   > 依赖：数据库
   > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)、[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >
2. **Hold Token验证服务**

   - 开发代币余额验证API
   - 实现持有时间跟踪服务

   > 依赖：区块链数据服务
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)、[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
3. **Swap交易验证服务**

   - 开发Swap交易验证API
   - 实现多链支持

   > 依赖：区块链数据服务
   > 来源：[任意Swap任务.md](./任意Swap任务.md)、[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
   >
4. **奖励发放服务**

   - 设计奖励数据模型
   - 实现奖励发放和领取API

   > 依赖：奖励系统
   > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
   >
5. **B端Request数据模型与API**

   - 设计Request数据模型
   - 实现Request创建、列表API

   > 依赖：数据库
   > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)、[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
   >
6. **用户任务进度跟踪服务**

   - 设计用户任务进度数据模型
   - 实现进度跟踪和状态更新API

   > 依赖：数据库
   > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)、[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >
7. **埋点系统实现（后端）**

   - 设计埋点数据模型与收集机制
   - 实现数据收集API及存储服务
   - 支持PV/UV统计及用户行为分析

   > 依赖：数据库、分析工具
   > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
   >
8. **运营审批流程服务（废弃，不排）**

   - 设计审批流程数据模型
   - 实现Request与Action审批API

   > 依赖：数据库
   > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)、[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
   >
9. **Collection服务**

   - 设计Collection数据模型
   - 实现Collection创建与管理API

   > 依赖：数据库、Action服务
   > 来源：[📌 2 0 运营工具后台 .md](./📌%202%200%20运营工具后台%20.md)
   >
10. **Collection完成逻辑实现（后端）**

    - 开发Collection中多Action完成状态追踪
    - 实现Collection完成判定服务
    - 实现Collection总体奖励发放逻辑

    > 依赖：数据库、Action服务、奖励系统
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
11. **Bridge交易验证服务**

    - 开发跨链Bridge交易验证API
    - 实现多链支持

    > 依赖：区块链数据服务
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
12. **数据统计服务**

    - 设计数据统计模型
    - 实现各项指标统计API

    > 依赖：数据库
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)、[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
13. **教育内容与Quiz服务**

    - 设计教育内容和Quiz数据模型
    - 实现内容管理和Quiz验证API

    > 依赖：数据库
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
14. **反作弊系统服务**

    - 设计反作弊规则和检测机制
    - 实现可配置的Anti-Bot开关和验证逻辑
    - 开发可疑账户标记和限制功能

    > 依赖：用户行为数据、区块链数据服务
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)、[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)
    >
15. **工单服务集成**

    - 设计Onchain相关工单类型和数据模型
    - 实现工单创建API与状态跟踪

    > 依赖：工单系统
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
16. **精准推荐服务**

    - 设计用户标签和推荐规则模型
    - 实现个性化推荐API

    > 依赖：数据库、用户行为数据
    > 来源：[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
17. **徽章系统**

    - 设计徽章与Action关联模型
    - 实现徽章发放与查询API

    > 依赖：徽章系统
    > 来源：[c端 On-chain 落地页.md](./c端%20On-chain%20落地页.md)
    >
18. **预算管理服务**

    - 设计预算管理数据模型
    - 实现预算控制与消耗计算API

    > 依赖：数据库
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)
    >
19. **多链钱包服务优化**

    - 优化钱包连接与管理服务
    - 实现多链支持的验证逻辑（包括非EVM链）

    > 依赖：钱包服务
    > 来源：[📌 2 0 Onchain模块.md](./📌%202%200%20Onchain模块.md)、[任意Swap任务.md](./任意Swap任务.md)
    >
20. **高级统计与分析**

    - 开发用户行为分析服务
    - 实现任务完成率和效果评估统计

    > 依赖：数据库、数据分析工具
    > 来源：[Onchain板块 B端 .md](./Onchain板块%20B端%20.md)、[Onchain新板块框架文档.md](./Onchain新板块框架文档.md)
    >
