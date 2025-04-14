# 软件开发评审流程图

## 一、分阶段评审流程

```mermaid
graph LR
    classDef phaseBox fill:#f9f9f9,stroke:#333,stroke-width:2px
    classDef infoBox fill:#e6f7ff,stroke:#333,stroke-width:1px
    
    Start([开始]) --> PRD[PRD评审]
    PRD --> UI[UI设计评审]
    UI --> Tech[技术方案评审]
    Tech --> Test[测试用例评审]
    Test --> Launch[上线前评审]
    Launch --> End([结束])
    
    PRD -.-> PRD_Info
    UI -.-> UI_Info
    Tech -.-> Tech_Info
    Test -.-> Test_Info
    Launch -.-> Launch_Info
    
    subgraph PRDDetails[PRD评审阶段详情]
    PRD_Info["• 时间点: PRD文档完成后<br>• 参与人员: 产品经理、开发负责人、测试负责人、设计师<br>• 评审目标: 验证需求完整性、一致性、可行性"]
    end
    
    subgraph UIDetails[UI评审阶段详情]
    UI_Info["• 时间点: 交互与视觉设计完成后<br>• 参与人员: 设计师、产品经理、前端开发<br>• 评审目标: 确认UI设计与需求一致，交互流程完整"]
    end
    
    subgraph TechDetails[技术方案阶段详情]
    Tech_Info["• 时间点: 技术方案完成后，编码前<br>• 参与人员: 开发负责人、团队Leader、技术责任人、测试负责人<br>• 评审目标: 确认技术实现方案合理性，评估风险点"]
    end
    
    subgraph TestDetails[测试用例阶段详情]
    Test_Info["• 时间点: 开发完成前，测试开始前<br>• 参与人员: 测试负责人、开发负责人、产品经理<br>• 评审目标: 确认测试用例覆盖需求点"]
    end
    
    subgraph LaunchDetails[上线前阶段详情]
    Launch_Info["• 时间点: 测试完成后，上线前<br>• 参与人员: 产品经理、开发负责人、测试负责人<br>• 评审目标: 确认所有功能符合需求，无严重缺陷"]
    end
    
    class PRDDetails,UIDetails,TechDetails,TestDetails,LaunchDetails infoBox
    class PRD,UI,Tech,Test,Launch phaseBox
```

## 二、各阶段评审检查清单

### PRD评审检查清单

```mermaid
graph TB
    classDef mainNode fill:#f5f5f5,stroke:#333,stroke-width:2px,color:#333,font-weight:bold
    classDef subNode fill:#e6f7ff,stroke:#333,stroke-width:1px
    
    PRD_Check["PRD评审检查清单"]
    
    PRD_Check --> BusinessProcess["1. 业务流程完整性"]
    PRD_Check --> Features["2. 功能点覆盖率"]
    PRD_Check --> DataFields["3. 数据字段必要性评估"]
    PRD_Check --> Boundaries["4. 边界条件与异常处理"]
    PRD_Check --> Roles["5. 用户权限与角色定义"]
    PRD_Check --> NonFunc["6. 非功能性需求"]
    PRD_Check --> Loop["7. 功能闭环验证"]
    
    BusinessProcess --> BP1["• 主流程闭环<br>• 异常场景覆盖"]
    Features --> FT1["• 核心功能<br>• 辅助功能<br>• 增值功能"]
    DataFields --> DF1["• 字段用途明确<br>• 数据来源可靠"]
    Boundaries --> BN1["• 极限值处理<br>• 错误输入处理"]
    Roles --> RL1["• 角色清晰<br>• 权限划分合理"]
    NonFunc --> NF1["• 性能要求<br>• 安全要求<br>• 兼容性要求"]
    Loop --> LP1["• 无中断点<br>• 每个操作有响应"]
    
    class PRD_Check mainNode
    class BusinessProcess,Features,DataFields,Boundaries,Roles,NonFunc,Loop subNode
```

### UI设计评审检查清单

```mermaid
graph TB
    classDef mainNode fill:#f5f5f5,stroke:#333,stroke-width:2px,color:#333,font-weight:bold
    classDef subNode fill:#e6f7ff,stroke:#333,stroke-width:1px
    
    UI_Check["UI设计评审检查清单"]
    
    UI_Check --> Flow["1. 交互流程覆盖"]
    UI_Check --> PRDMatch["2. 设计与PRD一致性"]
    UI_Check --> UX["3. 用户体验一致性"]
    UI_Check --> States["4. 异常状态设计"]
    UI_Check --> Responsive["5. 响应式适配方案"]
    UI_Check --> Standards["6. 设计规范符合度"]
    
    Flow --> Flow1["• 主流程<br>• 异常流程<br>• 边界情况"]
    PRDMatch --> PRDMatch1["• 功能点对应<br>• 交互逻辑匹配"]
    UX --> UX1["• 视觉风格统一<br>• 操作模式统一"]
    States --> States1["• 空状态<br>• 加载状态<br>• 错误状态"]
    Responsive --> Resp1["• 桌面端<br>• 移动端<br>• 平板端"]
    Standards --> Std1["• 色彩规范<br>• 字体规范<br>• 组件规范"]
    
    class UI_Check mainNode
    class Flow,PRDMatch,UX,States,Responsive,Standards subNode
```

### 技术方案评审检查清单

```mermaid
graph TB
    classDef mainNode fill:#f5f5f5,stroke:#333,stroke-width:2px,color:#333,font-weight:bold
    classDef subNode fill:#e6f7ff,stroke:#333,stroke-width:1px
    
    Tech_Check["技术方案评审检查清单"]
    
    Tech_Check --> Arch["1. 技术架构设计合理性"]
    Tech_Check --> DataModel["2. 数据模型与流设计"]
    Tech_Check --> API["3. 接口定义完整性"]
    Tech_Check --> Risk["4. 技术风险评估与对策"]
    Tech_Check --> DataConsistency["5. 数据一致性保障措施"]
    
    Arch --> Arch1["• 架构选型<br>• 模块划分"]
    DataModel --> DataModel1["• 数据结构<br>• 数据关系<br>• 数据流转"]
    API --> API1["• 接口参数<br>• 返回值定义<br>• 错误码设计"]
    Risk --> Risk1["• 性能风险<br>• 安全风险<br>• 依赖风险"]
    DataConsistency --> DC1["• 事务机制<br>• 并发控制<br>• 灾备方案"]
    
    class Tech_Check mainNode
    class Arch,DataModel,API,Risk,DataConsistency subNode
```

### 测试用例评审检查清单

```mermaid
graph TB
    classDef mainNode fill:#f5f5f5,stroke:#333,stroke-width:2px,color:#333,font-weight:bold
    classDef subNode fill:#e6f7ff,stroke:#333,stroke-width:1px
    
    Test_Check["测试用例评审检查清单"]
    
    Test_Check --> Coverage["1. 测试用例覆盖率"]
    Test_Check --> Automation["2. 自动化测试方案"]
    Test_Check --> TestData["3. 测试数据准备情况"]
    Test_Check --> Regression["4. 回归测试范围"]
    
    Coverage --> Cov1["• 功能测试<br>• 边界测试<br>• 异常测试"]
    Automation --> Auto1["• 自动化脚本<br>• CI/CD集成"]
    TestData --> TD1["• 测试数据集<br>• 测试环境隔离"]
    Regression --> Reg1["• 核心功能回归<br>• 高风险功能回归"]
    
    class Test_Check mainNode
    class Coverage,Automation,TestData,Regression subNode
```

### 上线前评审检查清单

```mermaid
graph TB
    classDef mainNode fill:#f5f5f5,stroke:#333,stroke-width:2px,color:#333,font-weight:bold
    classDef subNode fill:#e6f7ff,stroke:#333,stroke-width:1px
    
    Launch_Check["上线前评审检查清单"]
    
    Launch_Check --> Completeness["1. 功能完整性验证"]
    Launch_Check --> Bugs["2. 缺陷修复验证"]
    Launch_Check --> Migration["3. 数据迁移验证"]
    Launch_Check --> Rollback["4. 回滚方案确认"]
    
    Completeness --> Comp1["• 全部需求点验收<br>• 功能闭环验证"]
    Bugs --> Bug1["• 重大缺陷清零<br>• 一般缺陷评估"]
    Migration --> Migr1["• 迁移方案测试<br>• 数据完整性校验"]
    Rollback --> Roll1["• 回滚流程<br>• 回滚时间评估<br>• 回滚责任人"]
    
    class Launch_Check mainNode
    class Completeness,Bugs,Migration,Rollback subNode
```

## 三、问题跟踪与状态流转

### 问题状态流转图

```mermaid
graph LR
    classDef stateNode fill:#f9f9f9,stroke:#333,stroke-width:2px,color:#333
    classDef eventArrow stroke:#666,stroke-width:1.5px
    classDef issueLevel fill:#e6f7ff,stroke:#333,stroke-width:1px
    
    Start((开始)) --> A[待解决]
    A -->|责任人接受任务| B[处理中]
    B -->|问题修复| C[待复核]
    C -->|评审通过| D[已解决]
    C -->|复核不通过| B
    A -->|P2/P3级别问题| E[延期处理]
    E -->|下阶段处理| B
    B -->|非问题/不修复| F[关闭]
    D --> End((结束))
    F --> End
    
    subgraph 问题分级
    P0["P0: 阻塞项<br>必须解决才能进入下一阶段"]
    P1["P1: 重要问题<br>需在当前阶段解决"]
    P2["P2: 次要问题<br>可在下一阶段解决"]
    P3["P3: 建议事项<br>可酌情处理"]
    end
    
    class A,B,C,D,E,F stateNode
    class P0,P1,P2,P3 issueLevel
```

### 评审结果状态流转

```mermaid
graph LR
    classDef stateNode fill:#f5f5f5,stroke:#333,stroke-width:2px,color:#333,font-weight:bold
    classDef milestone fill:#fffacd,stroke:#333,stroke-width:1.5px
    
    Start((开始)) --> A[评审中]
    A -->|无P0/P1问题| B[通过]
    A -->|有P1问题<br>但有解决方案| C[有条件通过]
    A -->|有P0问题| D[未通过]
    C -->|P1问题解决| B
    D -->|修改后<br>重新评审| A
    B --> End([进入下阶段])
    
    class A,B,C,D stateNode
    class Start,End milestone
```

## 四、角色与职责

```mermaid
graph TB
    classDef roleNode fill:#f9f9f9,stroke:#333,stroke-width:2px,color:#333,font-size:14px,font-weight:bold
    classDef docNode fill:#e6f7ff,stroke:#333,stroke-width:1px
    classDef reviewNode fill:#fff0f5,stroke:#333,stroke-width:1px
    
    PM["产品经理<br>Product Manager"] 
    Design["设计师<br>Designer"]
    Dev["开发负责人<br>Dev Lead"]
    TL["团队Leader<br>Team Leader"]
    TR["技术责任人<br>Tech Owner"]
    Test["测试负责人<br>QA Lead"]
    
    %% 产品经理职责
    PM -->|负责| PRD[PRD文档准备]
    PM -->|参与| UI_Review[UI评审]
    PM -->|参与| Test_Review[测试用例评审]
    PM -->|参与| Launch_Review[上线前评审]
    
    %% 设计师职责
    Design -->|负责| UI_Doc[UI设计文档]
    Design -->|参与| PRD_Review[PRD评审]
    
    %% 开发负责人职责
    Dev -->|负责| Tech_Doc[技术方案]
    Dev -->|参与| PRD_Review
    Dev -->|参与| UI_Review
    Dev -->|参与| Test_Review
    Dev -->|参与| Launch_Review
    
    %% 其他技术人员职责
    TL -->|参与| Tech_Review[技术方案评审]
    TR -->|参与| Tech_Review
    
    %% 测试负责人职责
    Test -->|负责| Test_Case[测试用例]
    Test -->|参与| PRD_Review
    Test -->|参与| Tech_Review
    Test -->|参与| Launch_Review
    
    class PM,Design,Dev,TL,TR,Test roleNode
    class PRD,UI_Doc,Tech_Doc,Test_Case docNode
    class PRD_Review,UI_Review,Tech_Review,Test_Review,Launch_Review reviewNode
```

## 五、变更管理流程

```mermaid
graph TD
    classDef processNode fill:#f5f5f5,stroke:#333,stroke-width:2px,color:#333
    classDef decisionNode fill:#fffacd,stroke:#333,stroke-width:1.5px
    classDef actionNode fill:#e6f7ff,stroke:#333,stroke-width:1px
    
    A["需求变更提出"] --> B["变更影响评估"]
    B --> C{"是否重大变更?"}
    C -->|是| D["变更评审委员会"]
    C -->|否| E["责任人评估"]
    D --> F{"决策结果"}
    E --> F
    F -->|通过| G["变更执行"]
    F -->|拒绝| H["反馈提出方"]
    
    G --> I["通知相关方"]
    G --> J["更新相关文档"]
    G --> K["更新项目计划"]
    
    class A,B,D,E,G,H,I,J,K processNode
    class C,F decisionNode
```

## 六、评审结果确认机制

```mermaid
sequenceDiagram
    participant Host as 评审主持人
    participant Member as 与会人员
    participant System as 问题跟踪系统
    
    Note over Host,Member: 评审会议开始
    
    Host->>Member: 1. 主持评审会议
    Member->>System: 2. 记录发现的问题
    System->>Host: 3. 生成问题清单
    Host->>Member: 4. 确认问题分级和责任人
    Member->>Host: 5. 确认评审结果
    
    alt 通过
        Host->>Member: 6a. 记录通过结论
    else 有条件通过
        Host->>Member: 6b. 记录有条件通过结论
        Host->>System: 7b. 记录P1问题解决方案和时间表
    else 未通过
        Host->>Member: 6c. 记录未通过结论
        Host->>System: 7c. 记录P0问题及重新评审时间
    end
    
    Host->>Member: 8. 各方确认评审结果
    
    Note over Host,Member: 评审会议结束
```
