**Onchain板块 B端**

## 需求背景

新增加的Onchain板块，需要在B端可以创建onchain任务，同时我们内部需要有一个管理后台可以发布和管理这些onchain任务。

## 工作流程

<div style="margin-left: 20px;">
- B端用户在B端页面看到菜单入口，暂命名为Onchain Boost
- Onchain Boost，B端创建一个Onchain Task，必须是Token奖励并Deposit
- 运营在后台看到当前投放列表
- 分支一是action涉及新合约，需要走合约审核流程，由Donald审批
- 分支二是action不涉及新合约，可以选择接受，接受之后B端状态变更为Live
- 分支三是判断该action不合理无法完成，可以直接拒绝，自动退款
- 运营投放之后，能实时查看完成人数
- B端也能实时查看完成人数
- 如果到时间还完成不了，走手动退款流程
</div>

## Onchain任务分类

<div style="margin-left: 20px;">
- Hold Token（P0）
- Hold NFT（P1）
- Swap（P0）
- Bridge（P0）
- Mint NFT（P1）
- Stake（P1）
- Smart Contract（P1）
- Provide LP/Hold LP（P2）
- Borrow/Supply（P2）
</div>

## 功能清单

<div style="margin-left: 20px;">
- Onchain Boost创建流程
- Hold Token
- Swap
- Bridge
- Swap集成
</div>

## 功能详情

### 1. **Onchain Boost-入口和落地页**

#### 1.1 **左侧栏**

在图中红色位置，增加新功能的tab，名字暂定：Onchain Boost

![](media/image1.png)

#### 1.2 **落地页**

<div style="margin-left: 20px;">
<strong>进入条件</strong>

没有创建过boost

<strong>页面布局</strong>

![](media/image2.png)

<strong>交互逻辑</strong>

点击3个action任意一个，直接带参数进入Create流程；

下面的action都不可点击，鼠标悬浮显示coming soon
</div>

#### 1.3 **列表页**

<div style="margin-left: 20px;">
<strong>进入条件</strong>

创建过Onchain Boost

<strong>页面布局</strong>

展示Boost列表页，Target加文案Volume

![](media/image3.png)

<strong>Boost状态规则</strong>

<ul>
<li><strong>Draft</strong>：可以编辑、删除</li>

<li><strong>Pending</strong>：可以Cancel、Contact
<br>文案：The boost is under review. Please wait patiently for the staff to
contact you. If you want to contact us proactively, you can click the
Contact button.</li>

<li><strong>Canceled</strong>：引导用户查看退款、其他与draft相同
<br>文案：The refund has been automatically made. Please check the balance
in Assets.</li>

<li><strong>Rejected</strong>：运营Reject变为Rejected，引导用户查看退款、联系我们、其他与draft相同
<br><del>文案：Your Boost has been rejected by the reviewer because it does not
meet the platform boost specifications, and the budget has been returned
to your assets. If you want further information, please contact us</del>
<br>改为<strong>Your Boost has been rejected, please check this Feedback before
trying reapply</strong>
<br>用户点击Feedback出现弹窗里面位运营填写的拒绝理由
<blockquote>
![](media/image4.png)
<br>
![](media/image5.png)
</blockquote>
</li>

<li><strong>Live</strong>：运营Accept后变为Live，无法编辑、删除，能看数据</li>

<li><strong>Completed</strong>：达成项目方需要的target，能看数据</li>

<li><strong>Expired</strong>：到了时间，但没达成项目方需要的target，能看数据、联系我们
<br>文案：Your boost has expired. We are sorry that you have not reached
your target. Please contact us for a partial refund.</li>
</ul>

<strong>数据字段</strong>

<ul>
<li><strong>Name</strong>：直接用B端选择的Action作为名字</li>
<li><strong>时间</strong>：展示为时间段，前面是创建时间，后面是结束时间，定义为Publish时间+Schedule填写的天数</li>
<li><strong>Budget</strong>：总预算，数量+代币名称</li>
<li><strong>Target</strong>：这里列出所有的目标，并且展示目标的进度，比如200/3000
Wallets，代表目标3000个，已完成200个</li>
</ul>

<strong>交互逻辑</strong>

<ul>
<li>点击Cancel&Refund，状态变更为Canceled，从运营后台撤回这个申请，并自动执行退款，退回到用户Assets</li>
<li>点击Data，跳转到Boost的数据分析页面</li>
<li>点击Contact，跳转到一个Telegram链接，链接后面给出</li>
<li>点击Check assets，跳转到B端的assets页面</li>
<li>点击Edit（如果处于可以Edit的状态），进入与Create流程一样的编辑页面，所有字段都可以编辑</li>
</ul>

这里要注意Budget的处理流程：
<ul>
<li>用户Create流程之中，都不会真正的从Balance中扣掉Budget，只有点击Publish，才扣掉Budget</li>
<li>用户取消/被拒绝，会自动执行退款，退回Assets</li>
<li>取消/被拒绝后，用户重新编辑，点Publish之后，才会再次扣掉Budget</li>
<li>点击删除，需要弹窗二次确认</li>
</ul>

点击右上角New Boost，右侧划出

![](media/image6.png)
</div>

### 2. **Onchain Boost创建流程**

<div style="margin-left: 20px;">
<strong>进入条件</strong>

在落地页/Create New弹窗，点击任意action；

<strong>页面布局</strong>

<ul>
<li>顶端是3个步骤的切换，沿用我们的步骤切换通用组件</li>
<li>Action，Target&Budget，Publish</li>
<li>下面是变化区域</li>
<li>底部是按钮区域</li>
<li>Step 1是Save as Draft，Next</li>
<li>Step 2是Back，Save as Draft，Next</li>
<li>Step 3是Back，Save as Draft，Publish</li>
</ul>

<strong>交互逻辑</strong>

切换顶部的步骤，保留现有组件功能；

#### 2.1 **Swap流程**

##### 2.1.1 **Action**

![](media/image7.png)

<strong>数据字段：</strong>

<strong>Swap on specific Dex</strong>
<div style="margin-left: 20px;">
<ul>
<li>这是一个开关</li>
<li>如果关掉，就用taskon aggregator</li>
<li>如果打开，则展示一个下拉框（我们支持的dex列表），可以选择Dex（如果B端是一个Dex，要默认打开）</li>
<li>如果B端是一个Dex，则默认选中他的Dex</li>
<li>如果B端不是Dex，则默认选中Taskon Aggregator</li>
</ul>
</div>

<strong>Network</strong>：下拉框，选择网络（筛选该Dex支持的网络），默认不填

<strong>Swap from</strong>：下拉框，选择来源代币（筛选该Dex在该chain的支持代币），默认是Any Token

<strong>Swap to</strong>：下拉框，默认是Any Token

<strong>Swap At Least</strong>：后面是输入框+下拉框，输入框是输入数字（默认写入1），下拉框包括：
<div style="margin-left: 20px;">
<ul>
<li>USD Equivalent（默认填入）</li>
<li>Token Name：如果上面Swap to选择了代币，才会出现这个选项，如果选择了Any Token，则没有该选项</li>
</ul>
</div>

##### 2.1.2 **Target & Budget**

<strong>数据字段：</strong>

<strong>Target部分</strong>

> ![](media/image8.png)

<strong>Target Wallets</strong>：前面是一个开关，默认打开，后面是输入框Target的wallets数量

<strong>Target Volume</strong>：前面是一个开关，默认关闭，如果打开则展示输入框，是Target的总交易金额

<strong>Target Transactions</strong>：前面是一个开关，默认关闭，如果打开则展示输入框，是Target的总交易数量

<strong>More about your request</strong>：前面一个开关，默认关闭，如果打开是一个文本输入区域，可以输入具体要求

<strong>Anti-Bot</strong>：是一个开关，默认打开，旁边有文案介绍：Smart filtering of suspected robot wallets

前面三个Target，只能选择一个作为Key Target，并且有文案介绍我们会优先考虑完成Key Target

<strong>Budget部分</strong>

> ![](media/image9.png)

<strong>Token</strong>：第一个下拉框是Network，第二个下拉框是Token name

第二个下拉框，要使用下面这个版本，需要能添加token

> ![](media/image10.png)

奖励代币，需要符合"Onchain奖励代币白名单列表"（Billy提供规则），这里只展示用户的代币列表中符合这个白名单的代币。白名单规则:
<div style="margin-left: 20px;">
<ul>
<li>先把Quest Token Reward 里支持的 token 导入进来, 后续如果有新增 token需求, 走线下人工添加逻辑</li>
<li>如果用户要<del>Add New Token</del>搜索代币，搜索的是不符合白名单列表的代币，要提示用户：Sorry, this token is not currently supported as a reward. We recommend using USDT or other mainstream currencies.</li>
</ul>
</div>

<strong>Total Budget</strong>：一个输入框，需要填写总预算金额
<div style="margin-left: 20px;">
<ul>
<li>展示估算的USD价值</li>
<li>文案提示用户，总Budget不能低于500USD，单个wallet不能低于0.1USD（用英文）</li>
<li>给用户展示计算出来的单wallet成本</li>
<li>如果用户关闭wallet目标，不验证0.1U</li>
</ul>
</div>

<strong>Schedule</strong>：可以从publish开始，持续的时间天数
<div style="margin-left: 20px;">
<ul>
<li>默认填60天</li>
<li>文案：The schedule must last at least 30 days, and the unfinished part will be refunded by the end time.</li>
</ul>
</div>

##### 2.1.3 **Publish**

![](media/image11.png)

<strong>数据字段：</strong>
<div style="margin-left: 20px;">
<ul>
<li><strong>Total budget</strong>：总预算，不可更改</li>
<li><strong>Network</strong>：不可更改</li>
<li><strong>Token</strong>：不可更改</li>
<li><strong>Your Balance</strong>：我的余额，旁边有一个刷新图标</li>
<li>如果余额不足，展示：Insufficient balance, please deposit. 旁边是Deposit按钮</li>
</ul>
</div>

#### 2.2 **Bridge流程**

##### 2.2.1 **Action**

![](media/image12.png)

<strong>数据字段：</strong>

<strong>Bridge on specific Bridge</strong>
<div style="margin-left: 20px;">
<ul>
<li>这是一个开关</li>
<li>如果打开，则展示一个下拉框，可以选择Bridge（如果B端是一个Bridge，要默认打开）</li>
<li>如果B端是一个Bridge，则默认选中他的Bridge</li>
<li>如果B端不是Bridge，则默认选中Taskon Aggregator（如果先不针对Bridge项目方，则全部都选择这个）</li>
</ul>
</div>

<strong>From Network</strong>：下拉框，选择网络，默认Any Network

<strong>To Network</strong>：下拉框，选择网络，默认Any Network

<strong>Token</strong>：下拉框，默认Any Token

<strong>Bridge At Least</strong>：后面是输入框+下拉框，输入框是输入数字，默认填入1，下拉框包括：
<div style="margin-left: 20px;">
<ul>
<li>USD Equivalent（默认填入）</li>
<li>Token Name：如果上面Swap to选择了代币，才会出现这个选项，如果选择了Any Token，则没有该选项</li>
</ul>
</div>

##### 2.2.2 **Target & Budget**

![](media/image13.png)

<strong>数据字段：</strong>

<strong>Target部分</strong>

<strong>Target Wallets</strong>：前面是一个开关，默认打开，后面是两个输入框，一个是Target的wallets数量，另一个是该Target的权重（按百分比）

<strong>Target Volume</strong>：前面是一个开关，默认关闭，如果打开则展示两个输入框，一个是Target的总交易金额，另一个是该Target的权重
<div style="margin-left: 20px;">
<ul>
<li>默认选中USD Equivalent</li>
<li>如果上一步的swap币对中选择了具体token，那这里下拉列表展示上一步出现的token（包括swap from和to）</li>
</ul>
</div>

<strong>Target Transactions</strong>：前面是一个开关，默认关闭，如果打开则展示两个输入框，一个是Target的总交易数量，另一个是该Target的权重

<strong>Anti-Bot</strong>：是一个开关，默认打开，旁边有文案介绍：Smart filtering of suspected robot wallets

Budget部分，同上

第三步，Publish，同上

#### 2.3 **Hold Token**

##### 2.3.1 **Action**

![](media/image14.png)

<strong>数据字段：</strong>
<div style="margin-left: 20px;">
<ul>
<li><strong>Network</strong></li>
<li><strong>Token</strong></li>
<li><strong>Amount</strong>：默认填入1（限制最小值是合约精度最小值）</li>
<li><strong>Reward Type</strong>
  <ul>
    <li>选项A：用户只要hold就直接领取奖励（默认选中）</li>
    <li>选项B：用户需要hold目标天数才能领取，限制10天最长</li>
  </ul>
</li>
</ul>
</div>

##### 2.3.2 **Target&Budget**

<strong>数据字段：</strong>

<strong>Target部分</strong>

<strong>Target Wallets</strong>：前面是一个开关，默认打开（不可关闭），后面是两个输入框，一个是Target的wallets数量，另一个是该Target的权重（按百分比）

<strong>Anti-Bot</strong>：是一个开关，默认打开，旁边有文案介绍：Smart filtering of suspected robot wallets

Budget部分，同上

第三步，Publish，同上

#### 2.4 **Data**

<strong>页面布局</strong>

上面是汇总数据

> ![](media/image15.png)

Target的完成情况，Target可能是一到三个，三个是：Target Wallets、Target Volume、Target Txns

展示目标数值和完成数值，比如 Target Wallets：200/3000

展示一个图，上面画着每一个指标的每日数量

下面是列表

有一个Export按钮，点击可以把下面的表格下载为Excel

<strong>数据字段（Swap/Bridge）</strong>
<div style="margin-left: 20px;">
<ul>
<li><strong>Wallet</strong>：做任务的钱包地址</li>
<li><strong>Action</strong>：Swap/Bridge</li>
<li><strong>Chain</strong>：交易发生的链</li>
<li><strong>From</strong>：数量+币种，比如100USDT（分两列）</li>
<li><strong>To</strong>：数量+币种</li>
<li><strong>Time</strong>：交易时间</li>
<li><strong>Hash</strong>：交易hash</li>
</ul>
</div>

<strong>数据字段（Hold Token）</strong>
<div style="margin-left: 20px;">
<ul>
<li><strong>Wallet</strong></li>
<li><strong>Chain</strong></li>
<li><strong>Start Date</strong>：用户首次注册开始Hold的时间</li>
<li><strong>Day 1</strong>：第一天余额，数量+币种</li>
<li><strong>Day 2</strong></li>
<li>依次类推，有几天就展示几列</li>
</ul>
</div>
</div>

### 3. **Swap集成（Bridge也希望执行如下过程，但是优先级低于Swap）**

#### 3.1 **Dex映射表**

<div style="margin-left: 20px;">
维护字段：（仅限于所有OO支持的Dex）

<ul>
<li>Dex name</li>
<li>Twitter handle</li>
<li>Project ID（如果有的话）</li>
<li>支持的chain：一个列表</li>
<li>每个chain支持代币列表</li>
</ul>
</div>

#### 3.2 **集成swap验证**

<div style="margin-left: 20px;">
对于上述的Dex，与OO沟通，快速支持所有Dex在所有Chain上的Swap验证
</div>
