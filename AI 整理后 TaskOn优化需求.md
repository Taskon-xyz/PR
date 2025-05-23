# 产品设计文档模板：TaskOn优化需求 (1.9.7)

## 一、产品概述

### 1. 产品背景

当前的 TaskOn B 端平台在某些功能（如智能合约任务设置、B 端装修、POH 流程等）上存在用户体验可以优化的地方。

### 2. 产品愿景

优化 TaskOn B 端平台的用户体验，简化配置流程，增强功能，提升平台易用性和效率。

### 3. 用户故事

作为项目方运营人员，我希望：

- 更简单地设置智能合约任务，减少不必要的字段。
- 在 Quest Eligibility 中能够根据项目方内部的用户等级进行筛选。
- 使用 Binance 钱包登录和操作。
- B 端装修功能更灵活，C 端展示更稳定、交互更友好。
- Swap 任务支持最新的 PancakeSwap V4 和 Raydium 交易所。
- 下载 Memberlist 时能包含用户等级信息。
- POH（Proof of Humanity）流程更清晰，支持更多验证方式。
- Quest 和 Task 配置页面在某些情况下能自动隐藏不必要的选项，界面更简洁。
- Discord 集成和授权流程更顺畅。

## 二、业务流程

*(注意：原始文档未提供明确的全局或关键子流程图，以下根据功能描述推断)*

### 1. 全局业务流程图 (概述)

项目方通过 TaskOn B 端平台创建和管理 Quest 和社区任务，配置任务细节（如智能合约交互、Swap、POH 等）、资格条件（Eligibility）、奖励（如 Discord Role）和社区页面装修。用户在 C 端参与 Quest 和任务，完成验证，获取奖励。

### 2. 关键子流程图 (参考功能描述中的 UI 和交互逻辑)

- **智能合约任务设置流程 (简化后)**：进入任务设置 -> 填写任务名 -> 配置时间 (默认 Quest 时间) -> 保存/发布。
- **添加 Member Level Eligibility 流程**：进入 Quest 设置 -> Eligibility -> 添加 Member Level -> 配置等级条件 -> 保存/发布。
- **B 端装修 (图片链接)**：进入装修 -> 添加图片模块 -> 上传图片 -> (可选) 填写跳转链接 -> 保存。
- **POH 验证流程 (C 端 zkMe 示例)**：进入 C 端 POH 页面 -> 点击 zkMe Verify -> (如需要) 选择钱包地址 -> 等待插件验证 -> 完成验证。
- **配置 POH 任务 (B 端)**：进入任务添加 -> 选择 POH 分类 (如 KYC User, BABT Holder) -> (部分任务) 编辑服务商 -> 保存/发布。

## 三、功能设计

### 1. 功能地图 (对应原始文档功能清单)

| 编号 | 功能模块                        | 简要描述                                                                |
| ---- | ------------------------------- | ----------------------------------------------------------------------- |
| 2.1  | Smart Contract任务设置简化      | 移除 Category/Preparation，新增任务名，时间默认勾选                     |
| 2.3  | Binance钱包接入                 | 支持 Binance Wallet 登录                                                |
| 2.4  | B端装修优化                     | 图片配置跳转链接，Announcement 优化，C 端加载优化                       |
| 2.5  | PancakeSwap增加V4               | Swap 任务支持 V4 路由校验                                               |
| 2.6  | Swap任务新增Raydium交易所       | Swap 任务支持 Raydium (Solana)                                          |
| 2.7  | Memberlist 下载新增字段用户等级 | Memberlist 展示和下载增加用户等级字段                                   |
| 2.8  | POH优化                         | C 端入口和页面优化，B 端设置UI强化，服务商优化，接入新验证 (zkMe, BABT) |
| 2.9  | B端Quest/Task配置页展示优化     | 单一 Platform 任务自动隐藏 Platform 模块                                |
| 2.10 | Discord配置优化                 | DC 授权流程优化，授权绑定项目                                           |
| 2.11 | GTC任务优化                     | 简化链上任务配置流程，提高用户操作效率，但作用范围相对有限             |
| 2.12 | API任务报错优化                 | 优化API任务的错误返回信息                                              |

### 2. 功能描述模板 (详细描述各项功能)

#### 2.1 Smart Contract任务设置简化

**功能点 (字段删减)**

| 编号  | 功能点           | 描述                                  |
| ----- | ---------------- | ------------------------------------- |
| 2.1.1 | 移除Category     | B 端创建不再需要选动作类别            |
| 2.1.2 | 移除Preparation  | B 端创建不再需要填写该信息            |
| 2.1.3 | 新增任务名       | B 端填写任务名，C 端展示              |
| 2.1.4 | 时间设置默认勾选 | 默认使用 Quest 时间，可取消勾选自定义 |

**UI**
![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image.png)

**交互逻辑**

1. **移除Category**: 新建任务无此选项，已发布任务不变。
2. **移除Preparation**: 新建任务无此字段，已发布任务不变。
3. **新增任务名**: 类似 POW 任务，B 端填写，C 端显示。已发布任务不变。
4. **时间设置默认勾选**: Quest 内创建时默认勾选并同步 Quest 时间。取消勾选后显示时间组件。社区任务无勾选项，默认显示时间组件。

#### 2.3 Binance钱包接入

**功能点**

| 编号  | 功能点                           | 描述                                   |
| ----- | -------------------------------- | -------------------------------------- |
| 2.3.1 | 链接钱包的弹窗新增Binance Wallet | 在钱包连接选项中加入 Binance Wallet    |
| 2.3.2 | 用户用BN钱包可以登陆             | 实现 Binance Wallet 的登录和链交互逻辑 |

#### 2.4 B端装修优化

**功能点**

1. **图片配置跳转链接**:
   - 上传图片时可同时配置跳转链接（选填）。
   - C 端带链接的图片在 Hover 时应有特殊 UI 效果以区分。
2. **Announcement**:
   - 配置链接的 UI 需要更明显。
   - C 端 Hover 时自动展开，鼠标移开自动收起。
3. **C 端加载异常**: 修复 C 端打开未付费 B 端的社区首页时闪现 Home tab 的问题。

**UI**
![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%202.png)

#### 2.5 PancakeSwap增加V4

**功能点**

1. Quest 和社区任务的 Swap 任务增加 PancakeSwap V4 路由的校验。

#### 2.6 Swap任务新增Raydium交易所

**功能点**

1. Quest 和社区任务的 Swap 任务增加 Raydium 交易所。
   - 链: Solana
   - 网址: [https://raydium.io/](https://raydium.io/)
2. 通用 Swap 组件需要支持 Raydium。
3. 支持的代币 (Solana):

| Token Symbol | Address                                      |
| ------------ | -------------------------------------------- |
| SOL          | (原生)                                       |
| USDT         | Es9vMFrzaCERmJfrF4H2FYD4KCoNkY11McCe8BenwNYB |
| USDC         | EPjFWdd5AufqSSqeM2qN1xzybapC8G4wEGGkZwyTDt1v |

#### 2.7 Memberlist下载新增用户等级

**功能点**

| 编号  | 功能点           | 描述                                      |
| ----- | ---------------- | ----------------------------------------- |
| 2.7.1 | 右边展示增加等级 | 用户信息卡片右上角显示用户等级            |
| 2.7.2 | 下载增加等级字段 | 下载的 CSV/Excel 文件增加 Member Level 列 |

**UI (信息卡片)**
![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%203.png)

**UI (下载表格)**
![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%204.png)
*(交互逻辑: 在下载表格的 User Name 和 Twitter 之间加入字段 Member Level)*

#### 2.8 POH优化

**功能点**

| 编号  | 功能点        |                               描述                               |
| ----- | ------------- | :---------------------------------------------------------------: |
| 2.8.1 | 新增C端入口   |                     个人中心增加 POH 页面入口                     |
| 2.8.2 | C端页面优化   | 未登录状态、分类展示 (ExchangeKYC, POH NFT Holder)、zkMe 交互优化 |
| 2.8.3 | B端设置UI强化 |              调整 POH 任务添加入口，简化部分任务配置              |
| 2.8.4 | POH服务商优化 |                       服务商选择页 UI 优化                       |
| 2.8.5 | 接入新验证    |     现有任务支持 zkMe，新增 BABT Holder, zkMe NFT Holder 任务     |

**2.8.1 C端新增入口**

- 个人中心增加 POH 入口，点击跳转至 `https://taskon.xyz/poh`。
- **UI**: ![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/f5949372-e5f9-4381-9c48-a9abc5f412ad.png)

**2.8.2 C端POH页面优化**

- **未登录状态**: 头像显示 "?"，提示文字改为 "Login to see your stamps!"。
- **分类**: 增加 ExchangeKYC 和 POH NFT Holder 分类。
- **新增 POH NFT**: BABT Holder, zkMe NFT Holder。
- **UI**: ![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%205.png)
- **zkMe 交互优化**:
  - 点击 Verify:
    - 未安装插件: 提示安装并提供链接。**UI**: ![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%206.png)
    - 多地址: 显示地址选择（优化 UI），选择后点 Next。**UI**: ![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%207.png)
    - 单地址/选择后: 等待验证弹窗。

**2.8.3 B端设置UI强化**

- **任务添加入口**: 移除顶层 New Task/Duplicated，将 Off chain/Onchain/API/Duplicated 改为主要分类选项。
- **新增任务**: 在 POH 分类下仅新增 BABT Holder, zkMe NFT Holder。
- **原 Proof of Humanity 任务变更**:
  - 任务名改为 "KYC User of a Centralized Exchange"。
  - 点击添加直接成功，默认配置为 "Any" 且全选服务商。
  - 编辑时打开服务商选择页。
- **UI**: ![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%208.png)

**2.8.4 服务商选择页优化**

- **卡片信息**: Logo、服务商 Logo (Hover 显示文案)、验证信息、描述信息、选择按钮 (区分选中/未选中)。
- 移除 Request list。
- **UI**: ![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%209.png)

**2.8.5 接入新验证**

- **涉及服务商**: zkPass, zkMe (新)。
- **现有任务扩展**: Binance KYC 验证新增 zkMe 服务商。
- **新任务列表**:

| 服务商  | 任务名[B端]                         | 任务名[C端]                         | 任务描述[B端]           | 任务描述[C端]       | 跳转链接[C端]                                           |
| ------- | ----------------------------------- | ----------------------------------- | ----------------------- | ------------------- | ------------------------------------------------------- |
| Binance | BABT（Binance Account Bond Token）Holder | BABT（Binance Account Bond Token）Holder | User need to own BABT NFT | How to get BABT     | [https://www.binance.com/en/BABT](https://www.binance.com/en/BABT) |
| zkMe    | zkMe NFT Holder                     | zkMe NFT Holder                     | User need to own zkMe NFT | How to get zkMe NFT | (zkMe 提供)                                             |

- **UI (BABT)**: ![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%2010.png)

#### 2.9 B端Quest/Task配置页展示优化

**功能点**

- 在 Quest 和 Task 配置页面，如果任务只有一个 Platform 选项（如 Custom API, POH 的部分任务），则自动隐藏 Platform 选择模块。

**UI (Quest 示例)**
![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%2011.png)

**UI (Task 示例)**
![image.png](1%209%207%20TaskOn%E4%BC%98%E5%8C%96%E9%9C%80%E6%B1%82%201c9c8690efc4809eb815e237416537f3/image%2012.png)

#### 2.10 Discord集成优化

**背景**: 当前不同功能模块对 Discord 的集成和授权方式不统一。

**目标**:

| 功能点         | 描述                            |
| -------------- | ------------------------------- |
| DC授权流程优化 | 统一各场景下的 Discord 授权流程 |
| 授权DC绑定项目 | 确保授权与特定项目/社区关联     |

**待优化场景**:

- 奖励发放 Role (Quest, Rewards Shop, Event)
- 任务: Invite Friends to Discord (Quest, Task)
- 任务: Chat on Discord (Task)
- Integration: Automatic Notification, Predefined Commands

*(注：具体的优化后流程未在原始文档中详述，需进一步设计)*

#### 2.11 GTC任务优化

**功能点**

| 编号  | 功能点                        | 描述                                   |
| ----- | ----------------------------- | -------------------------------------- |
| 2.11.1 | 链上任务金额属性简化         | 仅保留"at least"金额属性选项          |
| 2.11.2 | Extra Settings配置（P2）     | 根据产品提供的配置表进行设置           |

**UI**
*(注：原始文档未提供UI设计图)*

**交互逻辑**

- **金额属性简化**:
  - 当前属性有三种: at least, less than, in the range
  - 优化后只保留 at least 选项
  - 已发布任务不受影响，仅对新建任务生效
- **Extra Settings配置**:
  - 由产品提供配置表
  - 作为P2优先级功能实现

#### 2.12 API任务报错优化（技术）

**功能点**

| 编号  | 功能点           | 描述                               |
| ----- | ---------------- | ---------------------------------- |
| 2.12.1 | 返回信息优化     | 优化API任务的错误返回信息          |
| 2.12.2 | API格式兼容      | 使API格式兼容竞品gaxle             |
| 2.12.3 | 前端URL格式校验  | 实现前端对URL格式的校验            |

**交互逻辑**

- **返回信息优化**:
  - 使错误提示更明确、更友好
  - 针对常见错误提供解决建议
- **API格式兼容**:
  - 调整API接口与参数，使其与gaxle格式兼容
  - 确保现有功能正常运行的同时支持gaxle格式
- **前端URL格式校验**:
  - 在提交前对URL进行格式校验
  - 对不符合规范的URL给出明确提示

## 四、业务规则

### 1. 业务规则概述

- **付费墙规则**: Member Level Eligibility 是付费功能，用户需升级 Plan 解锁。
- **校验规则**:
  - Member Level 配置需校验等级有效性。
  - Swap 任务需根据配置校验 V4 路由 (PancakeSwap) 或 Raydium 交易。
  - POH 任务根据配置校验用户是否持有对应 NFT 或完成 KYC。
- **UI 规则**:
  - 带链接的装修图片 Hover 时需有区分。
  - Announcement Hover 自动展开/收起。
  - 单一 Platform 任务配置页隐藏 Platform 模块。
- **数据规则**: Memberlist 下载需包含 Member Level 字段。
- **POH 规则**:
  - 原 Proof of Humanity 任务默认选中 Any 和所有服务商。
  - 特定 POH NFT 任务 (BABT, zkMe) 单独添加。

### 2. 业务规则列表模板

| 规则ID | 规则名称                | 规则描述                                         | 规则类型 | 涉及功能 |
| ------ | ----------------------- | ------------------------------------------------ | -------- | -------- |
| R001   | Member Level 付费限制   | Member Level Eligibility 为付费功能，需升级 Plan | 强制性   | 2.3      |
| R002   | Member Level 有效性校验 | 发布 Quest 前校验配置的 Member Level 是否有效    | 强制性   | 2.3      |
| R003   | Swap V4 校验            | PancakeSwap 任务需校验 V4 路由                   | 强制性   | 2.5      |
| R004   | Swap Raydium 校验       | Raydium Swap 任务需校验 Raydium 交易             | 强制性   | 2.6      |
| R005   | POH 验证                | C 端需根据任务配置进行对应的 POH 验证            | 强制性   | 2.8      |
| R006   | Memberlist 下载字段     | 下载的 Memberlist 必须包含 Member Level 字段     | 强制性   | 2.7      |
| R007   | 单一 Platform 隐藏      | 若任务只有一个可用 Platform，配置页隐藏该模块    | 显示规则 | 2.9      |
| R008   | 装修图片链接区分        | C 端带链接的图片 Hover 效果需与无链接图片区分    | 显示规则 | 2.4      |

## 五、数据需求

### 数据流说明

- **用户等级数据**: 需要存储和管理项目方定义的用户等级，并与用户地址关联。
- **Eligibility 配置**: Quest 配置需存储 Member Level 条件。
- **装修配置**: 存储图片 URL 和可选的跳转链接。
- **Swap 配置**: 存储 Raydium 交易所信息及支持的 Token 地址 (Solana)。
- **Memberlist 数据**: 用户数据需包含 Member Level 字段。
- **POH 数据**: 存储用户通过各服务商 (包括 zkMe, BABT) 的验证状态。
- **任务配置**: 智能合约任务需存储任务名；POH 任务需存储选择的服务商或 NFT 类型。

## 六、需求开发优先级分析

为了确保资源合理分配，最大化产品价值交付，现对TaskOn优化需求(1.9.7)中的10项功能需求进行优先级评估。评估从业务价值、产品价值和用户价值三个维度考量，并给出综合优先级排序。

### 1. 优先级评估矩阵

| 需求ID | 功能名称                        | 业务价值 | 产品价值 | 用户价值 | 实现复杂度 | 综合优先级 |
| ------ | ------------------------------- | -------- | -------- | -------- | ---------- | ---------- |
| 2.8    | POH优化                         | 高       | 高       | 高       | 中         | P0         |
| 2.1    | Smart Contract任务设置简化       | 高       | 高       | 高       | 低         | P0         |
| 2.10   | Discord配置优化                 | 高       | 中       | 高       | 中         | P1         |
| 2.4    | B端装修优化                     | 中       | 高       | 高       | 低         | P1         |
| 2.11   | GTC任务优化                     | 中       | 高       | 高       | 低         | P1         |
| 2.6    | Swap任务新增Raydium交易所       | 中       | 中       | 高       | 高         | P2         |
| 2.5    | PancakeSwap增加V4               | 中       | 中       | 中       | 中         | P2         |
| 2.9    | B端Quest/Task配置页展示优化     | 低       | 中       | 高       | 低         | P2         |
| 2.12   | API任务报错优化                 | 中       | 中       | 高       | 中         | P2         |
| 2.7    | Memberlist下载新增用户等级      | 低       | 低       | 中       | 低         | P3         |
| 2.3    | Binance钱包接入（本期不做）     | 低       | 中       | 中       | 中         | P3         |

### 2. 优先级评估理由

#### P0级需求（必须实现）

**2.8 POH优化**

- **业务价值**：高 - 增强用户验证能力是平台安全性和可信度的基础，直接影响平台质量和可持续发展
- **产品价值**：高 - 完善的POH是Web3产品的核心差异化功能，对提升平台竞争力至关重要
- **用户价值**：高 - 更清晰的验证流程和多样的验证选项显著降低用户门槛，提升转化率
- **实现说明**：虽有多个子功能点，建议分批实现，优先实现C端入口优化和主要验证服务商对接

**2.1 Smart Contract任务设置简化**

- **业务价值**：高 - 降低项目方创建任务的门槛，提高任务创建成功率，增加平台活跃度
- **产品价值**：高 - 优化核心交互流程，提高产品易用性，减少用户困惑和支持成本
- **用户价值**：高 - 项目方可更高效地创建任务，减少不必要的配置负担
- **实现说明**：改动相对简单且影响广泛，移除冗余字段并优化默认设置可快速提升用户体验

#### P1级需求（高优先级）

**2.10 Discord配置优化**

- **业务价值**：高 - 改善与主流社交平台的集成能力，提高用户社区参与度和留存
- **产品价值**：中 - 统一授权流程提升产品一致性，但不是全新功能
- **用户价值**：高 - 简化Discord相关操作，降低用户使用障碍，提高社区参与积极性
- **实现说明**：关联多个功能模块，统一授权流程能解决多处用户痛点

**2.4 B端装修优化**

- **业务价值**：中 - 提升项目方品牌展示能力，间接提高平台吸引力
- **产品价值**：高 - 修复已知问题并增强功能，提高产品完成度
- **用户价值**：高 - 更灵活的装修功能和更稳定的展示效果显著提升用户体验
- **实现说明**：图片跳转链接等功能相对简单，可快速实现并获得明显体验提升

**2.11 GTC任务优化**

- **业务价值**：中 - 简化链上任务配置流程，提高用户操作效率，但作用范围相对有限
- **产品价值**：高 - 优化核心交互功能，减少冗余选项，提高产品一致性和易用性
- **用户价值**：高 - 显著降低项目方配置复杂度，减少出错可能性，提升配置体验
- **实现说明**：改动相对简单，主要是界面和逻辑优化，实现成本低但收益明显

#### P2级需求（中等优先级）

**2.6 Swap任务新增Raydium交易所**

- **业务价值**：中 - 扩展Solana生态支持，拓展平台业务边界，但受众相对有限
- **产品价值**：中 - 丰富交易所选择，增强多链支持，但非核心功能完善
- **用户价值**：高 - Solana用户可以使用平台完成Raydium相关任务，显著提升特定用户体验
- **实现说明**：需要适配不同链的交易逻辑，技术复杂度较高，建议在基础功能优化后实施

**2.5 PancakeSwap增加V4**

- **业务价值**：中 - 跟进生态发展，保持技术领先性，但影响范围有限
- **产品价值**：中 - 优化产品兼容性，支持最新协议，但属于功能更新而非新增
- **用户价值**：中 - 用户可使用最新交易路由，提高任务完成效率，但体验提升有限
- **实现说明**：技术实现相对直接，是对现有功能的延伸升级

**2.9 B端Quest/Task配置页展示优化**

- **业务价值**：低 - 主要影响界面体验，对核心业务指标影响有限
- **产品价值**：中 - 优化UI/UX，减少界面冗余，提高产品易用性
- **用户价值**：高 - 更简洁的配置界面明显减轻用户认知负担
- **实现说明**：显示逻辑调整相对简单，实现成本低，可在其他优先级更高的功能后实施

**2.12 API任务报错优化**

- **业务价值**：中 - 提高API任务的稳定性和兼容性，扩大平台支持范围，增强竞争力
- **产品价值**：中 - 改善技术基础设施，提高错误处理能力，但用户感知相对有限
- **用户价值**：高 - 更友好的错误提示和更广的兼容性直接提升开发者体验
- **实现说明**：涉及API层面改造和前端校验逻辑，技术复杂度适中，建议与其他API相关优化一并实施

#### P3级需求（低优先级）

**2.7 Memberlist下载新增用户等级**

- **业务价值**：低 - 仅提供额外数据展示，对平台业务增长贡献有限
- **产品价值**：低 - 完善数据导出功能，但非核心功能改进
- **用户价值**：中 - 项目方可获取更完整用户数据，但使用频率较低
- **实现说明**：实现复杂度低，可在资源充裕时实施，或与其他数据优化需求一并处理

**2.3 Binance钱包接入（本期不做）**

- **业务价值**：低 - 拓展用户覆盖面，吸引Binance生态用户，增强市场竞争力
- **产品价值**：中 - 增加钱包支持类型，提高兼容性，但非核心架构优化
- **用户价值**：中 - 为Binance用户提供便利，但对其他用户影响有限
- **实现说明**：与现有钱包集成逻辑相似，开发复杂度适中，能快速覆盖新用户群体

### 3. 阶段性交付建议

**第一阶段（核心体验提升）**

- 完成2.8 POH优化的关键部分（C端入口优化和主要验证服务商对接）
- 完成2.1 Smart Contract任务设置简化
- 完成2.10 Discord配置优化
- 完成2.4 B端装修优化

**第二阶段（功能扩展）**

- 完成2.11 GTC任务优化
- 完成2.8 POH优化的剩余部分
- 完成2.6 Swap任务新增Raydium交易所
- 完成2.5 PancakeSwap增加V4

**第三阶段（场景完善）**

- 完成2.9 B端Quest/Task配置页展示优化
- 完成2.12 API任务报错优化
- 完成2.7 Memberlist下载新增用户等级

### 4. 优先级决策依据

本次优先级排序遵循以下原则：

1. **用户痛点解决**：优先解决影响用户核心体验的问题，如复杂的任务配置流程和验证体验
2. **业务价值导向**：优先实现能带来明显业务增长或平台差异化的功能
3. **实现效益比**：在同等价值的功能中，优先选择实现复杂度低、见效快的需求
4. **功能完整性**：相互依赖或关联的功能尽量在同一阶段实现，保证功能的完整性

通过合理的优先级排序和分阶段交付，可以确保关键价值快速交付，并在有限资源下最大化产品改进成效。建议产品团队根据实际开发资源和业务发展情况灵活调整具体实施计划。
