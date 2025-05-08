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

**市场数据**
- 历史上所有做过Onchain Quest的用户约74万人
- 其中约10万人在最近一个月(4月)有行为记录
- 这部分活跃用户是重要的种子用户，是新板块的核心受众

### 2. 产品愿景

根据需求文档的内容，可以提炼出以下产品愿景：

- **打造完整的Onchain用户生态**：构建一个能够让用户便捷参与各类链上活动的平台
- **建立精准推荐机制**：让运营能够精准定位用户群体，提供个性化的Onchain任务推荐
- **提高平台用户的链上活跃度**：通过多样化的链上活动和奖励机制，提高用户参与度
- **建立可持续的B端价值循环**：通过CPS模式，为B端提供精准的用户群体，实现投放效果最大化
- **形成闭环的Onchain运营体系**：从用户获取、活跃到变现，形成完整的运营链路

### 3. 用户故事

基于所有文档内容，可以总结出以下几类用户故事：

**C端用户故事**
- 作为一名链上用户，我希望通过简单的操作就能参与各类链上活动，以获得相应的奖励
- 作为一名持有特定代币的用户，我希望能够通过持币获得额外奖励，增加我持有代币的价值
- 作为一名新手用户，我希望能够通过教育任务了解区块链知识，并通过实际操作学习链上交互
- 作为一名活跃用户，我希望能够看到适合我的任务推荐，避免错过感兴趣的活动

**B端用户故事**
- 作为一个项目方，我希望能够创建自定义的链上活动，吸引用户参与并提高项目曝光度
- 作为一个DEX项目方，我希望能够设置特定的Swap活动，增加平台交易量并获取新用户
- 作为一个Bridge项目方，我希望吸引用户跨链交互，增加项目使用率
- 作为一个投放方，我希望能够实时查看活动数据，了解投放效果并进行调整

**运营方用户故事**
- 作为一名运营人员，我希望能够方便地创建和管理各类链上活动
- 作为一名运营人员，我希望能够设置精准的用户推荐规则，让内容触达目标用户
- 作为一名平台管理员，我希望能够审核B端创建的活动，确保内容符合平台规则
- 作为一名数据分析人员，我希望能够看到详细的活动数据，评估活动效果

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

### 2. 关键子流程图

**C端用户任务参与流程**

C端用户体验流程主要分为以下几个关键节点：
1. 用户进入Onchain板块（通过导航栏入口或首页展示模块）
2. 用户浏览可用Action列表
3. 用户选择参与特定Action（可能是Swap、Bridge或Hold Token等类型）
4. 用户完成Action步骤（可能包含教育内容、Quiz、链上操作等）
5. 用户领取奖励
6. 用户可能被推荐其他相关Action

其中，不同类型Action的具体流程有所不同：

**Swap/Bridge任务流程**
- 用户点击Start开始任务
- 用户进入详情页并完成操作
- 用户点击Verify验证操作
- 验证通过后用户领取奖励

**Hold Token任务流程**（带持有天数要求）
- 用户点击Start开始任务
- 系统检查用户是否持有足够代币
- 如果满足条件，开始记录持有时间
- 用户需要定期刷新以确认仍然持有代币
- 持有满指定天数后，用户可以领取奖励

**Hold Token任务流程**（不带持有天数要求）
- 用户点击Start开始任务
- 系统检查用户是否持有足够代币
- 如满足条件，用户可以直接领取奖励
- 不满足条件则引导用户通过Swap获得所需代币

**Action Collection参与流程**
- 用户点击Start开始Collection任务
- 用户依次完成Collection中的多个Action
- 每完成一个Action获得相应奖励
- 完成所有Action后标记Collection为完成状态

## 三、功能设计

### 1. 功能地图

根据所有文档内容，可以梳理出以下功能模块：

**C端功能模块**
- Onchain落地页
  - 导航栏入口
  - 首页推荐模块
  - Action列表
  - Action卡片展示
  - 教育板块
  - 统计数据展示

- Action详情页
  - 详情页框架
  - 教育UI
  - Quiz UI
  - 内嵌执行UI
  - 奖励展示/领取
  - Collection展示

- 执行功能
  - Bridge内嵌执行
  - Swap执行
  - Hold Token验证
  - 任务进度追踪

**B端功能模块**
- Onchain Boost
  - 入口和落地页
  - Request创建
  - Request列表
  - Request状态跟踪
  - 预算管理

**运营后台功能模块**
- Request管理
  - Request列表
  - Request详情
  - Request审批流程
  - Request状态管理

- Action管理
  - Action列表
  - Action创建
  - Action审批
  - Action状态管理
  - Action排序

- Collection管理
  - Collection列表
  - Collection创建
  - Collection展示控制

- 精准推荐
  - 用户标签创建
  - 投放触点设置
  - 用户筛选
  - 运营效果分析

### 2. 功能描述模板

按照核心功能模块和用户主流程，可整理出以下功能描述：

#### C端 Onchain 落地页

**功能概述**：
提供用户探索和参与各类链上活动的主要入口，展示可参与的Action列表，追踪用户获得的奖励和进度。

**主要组件**：
- 导航栏入口：在导航栏增加⚡️ Onchain入口
- 首页推荐模块：在首页Quest模块下方展示Top 3 Onchain Action
- 头部信息板块：包括功能介绍、Token奖励总值和用户黄金积分数量
- Action列表：展示可参与的Action和Collection
- In Progress快速筛选：显示用户正在参与的Action
- 教育板块：展示徽章墙和相关教育内容

**交互逻辑**：
- 点击导航栏Onchain入口或首页"View All"按钮进入Onchain主页
- 默认显示所有进行中的可见Action，支持下拉加载更多
- 点击Action卡片进入详情页
- 点击In Progress按钮筛选正在参与的Action
- 点击徽章可查看相关教育内容

**Action卡片展示规则**：
- 按照排序规则显示Action卡片
- 基于Action类型(Swap/Bridge/Hold Token/Collection)显示不同UI
- 根据用户参与状态展示不同交互界面

#### Action详情页

**功能概述**：
提供用户参与单个Action的完整流程界面，包括任务介绍、执行步骤、验证和奖励领取。

**主要组件**：
- Action标题区：展示Logo和标题
- Action信息区：包含时间、参与信息和用户进度
- 奖励展示区：显示可获得的奖励
- 主操作区：展示各种Step的UI和领奖界面

**交互逻辑**：
- 用户通过点击Action卡片进入详情页
- 根据Step类型展示不同的操作界面
- 完成所有Step后展示领奖界面
- 领取奖励后可能推荐其他Action

**特殊状态处理**：
- 未登录状态：显示登录提示
- 判定为机器人：提示进行POH认证
- 判定为新用户：引导POH认证

#### B端Onchain Boost

**功能概述**：
允许B端用户创建和管理Onchain任务，指定任务类型、目标和预算，追踪任务执行效果。

**主要流程**：
1. **创建Request**
   - 选择任务类型(Swap/Bridge/Hold Token)
   - 设置任务参数
   - 设置目标指标(Target Wallets/Volume/Transactions)
   - 配置预算和时间安排

2. **跟踪Request状态**
   - 查看Request列表
   - 监控任务进度和指标完成情况
   - 管理预算使用
  
3. **Request状态管理**
   - Pending：等待运营审核
   - Canceled：B端取消
   - Rejected：运营拒绝
   - Ongoing：进行中
   - Completed：已完成
   - Expired：已过期

#### 运营后台工具

**功能概述**：
提供运营团队创建、审核和管理所有Onchain活动的工具，包括B端Request管理、Action创建和推荐设置。

**主要组件**：
1. **Request管理**
   - Request列表：查看和筛选所有Request
   - Request详情：查看单个Request的完整信息
   - Request操作：接受/拒绝/管理Request

2. **Action管理**
   - Action创建：设置基本信息、步骤、奖励和资格条件
   - Action列表：管理所有Action
   - Action状态控制：Draft/Pending/Upcoming/Live/Expired

3. **Collection管理**
   - Collection创建：设置标题、布局和Action组合
   - Collection列表：管理所有Collection
   - 可见性控制：设置C端可见性

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

#### Request状态管理规则

**Request状态规则**：
- Pending：B端成功发起Request，B端和运营都没有进行处理的状态
- Canceled：B端主动取消发起的Request
- Rejected：运营拒绝B端发起的Request
- Ongoing：运营接受B端发起的Request
- Completed：运营标记B端发起的Request为完成状态
- Expired：时间结束时B端Request的核心指标未能完成

#### 奖励展示规则

**多种类型奖励的情况下显示优先级**：
奖励类型优先级: Token奖励 > Badge > Gold XP > XP

**主奖励展示规则**：
- Token：显示总共token奖励等值美元价值，右侧logo采用TaskOn设计的token logo
- Badge：显示badge名称，右侧logo采用badge图片
- Gold XP：显示总共奖励的gold xp数量，右侧logo采用gold xp logo
- XP：显示总共奖励的xp数量，右侧logo采用xp logo

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

**其他统计需求**：
- 导航栏按钮点击的PV和UV
- Home组件点击的PV和UV
- 各步骤完成/未完成比例
- 用户设备和钱包类型分布
- 用户参与时段分布

## 六、埋点需求

根据需求文档，以下是关键埋点需求点：

**页面浏览埋点**：
- Onchain落地页访问
- Action详情页访问
- Collection详情页访问
- 教育板块访问

**操作行为埋点**：
- 导航栏Onchain入口点击
- 首页Onchain模块卡片点击
- Action卡片点击
- In Progress快速筛选点击
- 教育板块徽章点击
- Action步骤操作
- 验证按钮点击
- 奖励领取操作
- 推荐Action点击

**任务进度埋点**：
- Hold Token任务注册
- Hold Token每日检查
- Swap/Bridge操作发起
- Quiz答题
- 教育内容阅读
- 任务完成情况

**性能指标埋点**：
- 页面加载时间
- 操作响应时间
- 验证处理时间
- 钱包连接时间

这些埋点将帮助分析用户行为路径、任务完成率、活动效果，并为后续优化提供数据支持。 