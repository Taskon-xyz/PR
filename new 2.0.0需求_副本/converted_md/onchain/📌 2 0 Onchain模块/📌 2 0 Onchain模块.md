# 📌 2.0 Onchain模块

---

## 1️⃣ 需求概览

### 1.1 功能目标

- 运营后台
    - 能够快速创建符合B端需求或是TaskOn自身运营体系所需要的Action
    - 能够管理Request进度
- C端页面
    - 用户能够尽可能多的参与Onchain各类行为
    - 提高平台用户的Onchain日活
    - 建立可观用户基数满足B端CPS需求

### 1.2 设计思路

1. 用户进入详情页后通过页面关键元素形成执行决策
2. 通过限制用户对区域可操作的范围引导用户执行下一步
3. 在用户执行完操作后能够给予奖励正反馈
4. 让用户形成一直操作一直执行的闭环

### 1.3 核心页面

| 优先级 | 页面 | 描述 |
| --- | --- | --- |
|  | C端Onchain Action执行弹窗 |  |
|  | 运营端管理后台 |  |
|  | Action内嵌 |  |
|  | Hold任务增加Swap功能 |  |
|  | GTC社区支持POH |  |
|  | 系统改为用钱包作为默认登陆 |  |

### 1.4 核心用户旅程

- 页面进入来源
    - 通过C端落地页直接访问
    - 通过推荐模块进入页面
    - 通过各种渠道的分享直接进入该页面
- 不同用户的细分角色
    - 未登录状态
    - 已登录状态
- 具体流程在子功能点列出

---

## 2️⃣ 功能清单

| 编号 | 优先级 | 功能模块 | 描述 |
| --- | --- | --- | --- |
| 2.1 |  | C端Action详情页 |  |
| 2.2 |  | Bridge内嵌执行 |  |
| 2.3 |  | Hold任务增加Swap功能 |  |
| 2.4 |  | **登陆默认选项变为钱包** |  |

### **2.1** C端Action详情页

### 功能点

| 编号 | 功能点 | 描述 |
| --- | --- | --- |
| 2.1.1 | 详情页框架 |  |
| 2.1.2 | 教育 UI |  |
| 2.1.3 | Quiz UI |  |
| 2.1.4 | 内嵌执行 UI |  |
| **2.1.5** | 奖励展示/领取 |  |
| **2.1.6** | Collection 展示 |  |

### 用户主流程

1. 用户点击Action/Collection卡片
2. 页面出现Action详情弹窗
3. 用户查看详情弹窗
4. 用户依据分支执行Step
    1. 教育类内容
    2. Quiz
    3. 内嵌执行
5. 全部执行完后用户进入奖励领取页
    1. Token领取
    2. NFT徽章领取
    3. XP领取
    4. Gold XP领取
6. 用户领取完成后看到对应的推荐信息
    1. 推荐逻辑
        1. 推荐Action List中下一个用户没有完成的Action
            1. 如果没有则不显示推荐模块

![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image.png)

### 交互逻辑

1. 2.1.1 详情页
    1. 页面入口
        1. 直接通过链接访问
        2. 用户通过C端落地页点击卡片进入
    2. 整体页面布局
        - Action标题区
            1. 配置的Logo
                1. 默认为关联项目方的Logo
                2. 运营可以替换
            2. Action标题
                1. 运营端配置内容
                2. 字体样式等不可修改
        - Action信息区
            1. 时间组件
                1. 展示开始和结束时间
                2. 结束时间强化展示
                3. 最终样式UI定
            2. 参与信息
                1. 参与用户头像
                    1. 展示1-3个即可（UI定数量）
                    2. 参与人数
                        1. 如果奖励无限
                            1. 展示实际参与用户
                                
                                ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%201.png)
                                
                        2. 如果奖励有限
                            1. 展示已经完成用户数/总参数与上限
                                
                                ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%202.png)
                                
            3. 用户进度区
                
                ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%203.png)
                
                1. 模块展示用户当前完成的进度
                    1. UI能有分步骤的感觉
                    2. 有文案提示用户当前的步骤/Action总步骤数
                        1. 最小当前步骤为1
                        2. 未登录也显示1
        - 奖励展示区
            1. 
                1. 单奖励
                    
                    ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%204.png)
                    
                
                1. 固定区域文案
                    1. Rewards
                2. 奖励主体
                    1. Token
                        1. 图片
                        2. 金额
                    2. NFT Badges
                        1. 图片
                        2. 徽章信息
                            1. 徽章Logo
                            2. 徽章名
                            3. 
                    3. XP
                        1. 图片
                        2. 数值
                    4. Golden XP
                        1. 图片
                        2. 数值
                1. 多奖励
                    1. 规则
                        1. 每种奖励只能添加一种
                            1. 例如不能有多个token多个徽章
                            2. 可以同时有Token徽章积分等奖励
                    2. 在单奖励展示的基础上新增
                        
                        ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%205.png)
                        
                        1. 轮播切换（细节UI定）
                        2. 进入页面时首先展示的是优先级最高的奖励
                            1. 奖励优先级
                                1. Token
                                2. NFT
                                3. Golden XP
                                4. XP
                        3. 然后定时切换成下一个奖励的UI
                        4. 循环播放
                2. 人数限定
                    1. 前提
                        1. 当前Action的参与人数是有上限的
                    2. UI新增
                        
                        ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%206.png)
                        
                        1. 剩余的Spot（即可参与人数，文案用Spot）
                        2. 剩余Spot进度条（建议环形）
                        3. 依据不同的剩余Spot 百分比展示不同颜色增加紧迫感
                            1. 剩余＞60%+展示绿色
                            2. 剩余20%-60%展示黄色
                            3. 剩余＜20%展示*橙色
        - 主页面
            1. 主页面为用户操作Action中各Step和领奖的主区域
            2. Step类
                1. 展示各种Step的UI
                    
                    
                    | 类别 | Action | 操作 |  |
                    | --- | --- | --- | --- |
                    | Off | 教育类UI | Back
                    Next |  |
                    | Off | Quiz UI | Back |  |
                    | On | Hold | Back
                    Verify |  |
                    | On | Swap | Back
                    Verify |  |
                    | On | Bridge | Back
                    Verify |  |
                    
                    ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%207.png)
                    
                    ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%208.png)
                    
                    ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%209.png)
                    
                
                ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2010.png)
                
            3. 领奖类
                1. 奖励类型
                    1. 固定中奖文案
                        1. Congrats
                        2. You Have Won
                    2. Token
                        
                        ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2011.png)
                        
                        1. 
                        2. 代币图片
                        3. 代币名称
                        4. 发奖网路
                    3. NFT Badges
                    
                    ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2012.png)
                    
                    1. 
                    2. Golden XP&xp
                    
                    ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2013.png)
                    
        1. 关闭逻辑
            1. 用户点击弹窗的关闭按钮会关闭弹窗
                1. 弹窗缩小到对应卡片
                2. 有特效提示用户刚才关闭的是哪一个Action
                3. 需要定位到Action卡片所在为止
- 未登录状态
    1. UI
        
        ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2014.png)
        
    2. 页面显示Login遮罩
    3. 用户不能点击除了关闭、login以外的操作
    4. 已登录状态
        1. 已登录但是被系统判定为机器人
            1. 判定规则需要讨论后最终确定
                1. 倾向方案为第三方钱包地址信息作为判断依据
            2. 页面提示用户使用常见钱包操作，或者进行POH认证
                1. 页面和新手用户一样只是文案区别
                    1. Please connect with your common used wallet
            3. 用户在通过验证前不能再页面进行其他操作
        2. 判定为新用户
            1. UI
                
                ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2015.png)
                
            2. 页面提醒用户进行POH认证
                1. POH由Action创建时配置（*如果后续定完同一标准则不需要运营后台配置）
                2. 点击刷新按钮
                    1. 刷新状态
                3. 点击Start
                    1. 类似quest中的POH验证把对应的POH参数带到通用的用户POH执行页
            3. 用户在通过验证前不能在页面进行其他操作
- Elibility UI
    
    ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2016.png)
    
    - 单Eligibility样式
        - Anti-Bot
            1. X account Verification（同quest）
            2. On-chain Verification（同quest）
            3. POH（新增）
        - Target User Selection
            1. Action Completion（新增）
                
                ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2017.png)
                
                1. 显示Action Title
                2. 添加修改按钮
                    1. 没有选中action的时候文案add
                    2. 有选中action的时候文案change
                    3. 点击按钮后打开选择Action弹窗
                        
                        ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2018.png)
                        
                    4. 弹窗内容和Collection添加一致
                    5. 左侧栏的多选变成单选
                        1. 点击select后弹窗关闭小弹窗显示已选中的action
                    6. 用户可以点击Complete会变成Uncomplete
                        1. 这里的交互和eligibility中的Task一致
            2. Eligible Wallet Addresses（同quest）
            3. ？Discord Role（同quest）
            4. TaskOn Level（同quest）
            5. Specific NFT Holder（同quest）
            6. Minimum Token Balance（同quest）
            7. Resident of Specific Countries/Regions（同quest）
            8. ？Discord duration（同quest）
        - **Community Hub User Selection**
            1. member level（同quest）
            2. user points（同quest）
            3. Task（同quest）
- 2.1.2 教育UI
    1. UI
        
        ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2019.png)
        
    2. 页面元素
        1. 标题
            1. 运营端配置
        2. 主体
            1. 运营端配置的富文本
            2. 需要支持图片和视频
    3. 交互
        1. 用户查看图片文案
            1. 用户只能阅读
            2. 可能有外链（复用访问外链二次确认弹窗）
        2. 用户查看视频
            1. 用户播放暂停视频
            2. 可以全屏播放
        3. 通用交互
            1. 返回上一步
            2. 进入下一步
            3. 出现在最后一步的处理
                1. 用户需要点击next进入领奖环节
    4. 2.1.3 Quiz UI
        1. UI
            
            ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2020.png)
            
        2. 页面元素
            1. Quiz标题
                1. 运营端配置
            2. 主体
                1. Quiz选项
                2. 复用Community Task分支，可以包含图片选项
        3. 交互
            1. 用户选择
                1. 选对
                    1. 动效告知用户选择正确
                    2. 动画过渡到下一步
                    3. 用户不需要选择 Next
                2. 选错
                    1. 出现选错特效（抖动等）
                    2. 页面出现冷却时间文案
                        1. Please Retry in 3s
                        2. 冷却时间定为3秒（需要可修改）
                        3. 异常情况
                            1. 单选类别
                                1. 用户点击次数达到选项上限
                                2. 冷却时间定为10分钟（需要可修改）
                            2. 多选类别
                                1. 暂时按只有正常冷却时间处理
                    3. 每次选错后都需要对选项位置进行随机排序
- 2.1.4 Swap UI
    1. UI
        
        ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2021.png)
        
    2. 页面元素
        1. 内嵌展示
            1. 展示规则和其他内嵌模式一致
    3. 交互
        1. 用户对内嵌板块进行Swap交易
            1. 交易完成后用户点击Verify
            2. *是否有可能自动校验？
- 2.1.5 奖励展示/领取 UI
    1. Token领奖
        1. UI
            
            ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2022.png)
            
        2. 页面元素
            1. 中奖固定文案
                1. Congrats!
                2. You Have Won
            2. Token 图片
            3. Token 数量
                1. *非稳定币需要增加Token对应的U奖励价值
                2. *参考
                3. 稳定展示数量即可
                4. 精度采用通用方案
            4. Token所发放的链
                1. 固定文案
                    1. Distributed on
                2. 链Logo
                3. 链名称
            5. 奖励查看/领取提示
                1. 状态1
                    1. 文案
                        1. **Automatically added to your Assets**
                    2. 图片
                        1. 用户个人中心资产页的相关截图
                2. 状态2
                    1. 收起变成跳转按钮Check Now
                    2. 点击跳转至个人中心Asset Tab
        3. 交互
            1. 用户进入页面后看到3种状
                1. 状态1
                    1. 用户看到固定文文奖励信息
                2. 状态2
                    1. 浮现奖励查看/领取的提示
                3. 状态3
                    1. 固定文案和奖励信息收起
                    2. 浮现奖励查看/领取的提示变成Check Now按钮
                    3. 出现推荐模块
                        1. 展示推荐的其他Action等
    2. NFT Badge领奖
    3. Golden XP/XP
        1. *Golden XP和XP区别
            1. 流程一致只有UI上做出差异
            2. 后续版本增加用户运营体系后可能出现用户升级等差异性展示
        2. UI
            
            ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2022.png)
            
        3. 页面元素
            1. 中奖固定文案
                1. Congrats!
                2. You Have Won
            2. Token 图片
            3. Token 数量
                1. *非稳定币需要增加Token对应的U奖励价值
                2. 稳定展示数量即可
                3. 精度采用通用方案
            4. Token所发放的链
                1. 固定文案
                    1. Distributed on
                2. 链Logo
                3. 链名称
            5. 奖励查看/领取提示
                1. 状态1
                    1. 文案
                        1. **Automatically added to your Assets**
                    2. 图片
                        1. 用户个人中心资产页的相关截图
                2. 状态2
                    1. 收起变成跳转按钮Check Now
                    2. 点击跳转至个人中心Asset Tab
        4. 交互
            1. 用户进入页面后看到3种状
                1. 状态1
                    1. 用户看到固定文文奖励信息
                2. 状态2
                    1. 浮现奖励查看/领取的提示
                3. 状态3
                    1. 固定文案和奖励信息收起
                    2. 浮现奖励查看/领取的提示变成Check Now按钮
                    3. 出现推荐模块
                        1. 展示推荐的其他Action等
    4. 多奖励
        1. 多奖励情况下的展示会分为主奖励和次奖励
        2. 奖励重要度排序
            1. Token
            2. Badge
            3. Golden XP
            4. XP
        3. UI
            
            ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2023.png)
            
            ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2024.png)
            
            ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2025.png)
            
        4. 页面元素
            1. 页面元素为单奖励展示元素的累加
            2. 次奖励的展示优先级需要明显小于主奖励
- 2.1.6 Collection
    1. UI
    2. 卡片样式查看一均需求
    3. 详情页展示
        1. 两种样式
            1. Seamless
                
                ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2026.png)
                
                1. 无缝模式会按运营配置的顺序把action的step和领奖拼接起来
                2. 用户只有在最后一个step完成后的领奖页面才会展示对应额外推荐的action
                3. 页面右上角或者右下角需要增加类似里程碑的UI（参考游戏和layer3）
                    1. 里程碑为每个action的奖励
                    2. 里程碑之间的连接为用户需要做的step数量
                    3. 最终样式由UI定
                    4. 用户获奖时的样式里程碑需要有ui特效
            2. Separate
                
                ![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2027.png)
                
                1. 交互复用现在Epic下的quest展示
                2. 列表理论上可以一直下滑
                3. UI上进行微调（增加一些选中特效）
                    1. 展示信息为
                        1. Action logo
                        2. action title
                    2. 考虑增加每一个action的进度展示
                    3. 每个action的完成样式需要ui强化

### **2.2 Bridge 内嵌执行**

### 功能点

| 编号 | 功能点 | 描述 |
| --- | --- | --- |
| 2.3.1 | 内嵌OO bridge |  |
| 2.3.2 | 非EVM钱包处理 |  |

### UI

![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2028.png)

### 交互逻辑

1. 2.3.1 内嵌Openocean bridge组件
    1. Bridge和Swap交互逻辑几乎一致，按Swap逻辑处理各种分支即可
2. 2.3.2 非EVM钱包处理
    1. 由于用户可能会进行跨异构链操作，此类场景下的标准做法如下
        1. 需要用户连接两次钱包
        2. 连接的钱包状态分开管理
            1. 管理逻辑复用evm地址管理
        3. *本期限制用户可以bridge的范围
            1. 只能支持我们当前能够验证和用户能够绑定钱包的链
    2. 新增下拉选项中出现用户当前所有EVM地址
        1. 用户在连接evm地址的分支下，如果用户有其他绑定evm地址下拉选项中会自动出现对应地址
            1. 用户点击对应地址
                1. 如果用户当前未连接会唤起钱包让用户连接
                2. 如果用户已连接则会出现之前的单账号多地址切换的提示弹窗

### **2.3 Hold任务增加Swap功能**

### 功能点

| 编号 | 优先级 | 功能模块 | 描述 |
| --- | --- | --- | --- |
| 2.4.1 |  | Hold任务**增加Swap功能** |  |

### UI

复用现在SWAP任务相关的UI，但任务卡片本身需要增加按钮

### 交互逻辑

1. Quest
    1. 在Verify左边增加一个常驻按钮Swap
        1. 点击后打开swap浮窗
    2. 用户点击Verify校验失败后
        1. 提示用户可以用Swap
            1. 可以高亮swap按钮或者出现指引的手等
2. 社区task
    1. 在Verify上方增加一个常驻按钮Swap
        1. 点击后打开swap浮窗
    2. 点击卡片详情
        1. 样式和swap一样左边任务明细右边swap组件
    3. 用户点击Verify校验失败后
        1. 提示用户可以用Swap
            1. 可以高亮swap按钮或者出现指引的手等

### **2.4 登陆默认选项变为钱包**

### 功能点

| 编号 | 优先级 | 功能模块 | 描述 |
| --- | --- | --- | --- |
| 2.4.1 |  | **登陆默认选项变为钱包** |  |

### UI

![image.png](%F0%9F%93%8C%202%200%20Onchain%E6%A8%A1%E5%9D%97%201edc8690efc4805f9acfdd065060709e/image%2029.png)

### 交互逻辑

1. 先简单调换位置，钱包的展开需要在钱包选项下面而不是其他登陆方式的下面
2. 暂时不做优化（后续需要分链和钱包）
3. 非钱包类展示可以适当弱化（仅考虑视觉）