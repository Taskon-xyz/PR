# 需求开发评审流程图

## 一、分阶段评审验收流程

```mermaid
flowchart LR
    Start([开始]) --> PRD[PRD评审]
    PRD --> UI[UI设计评审]
    UI --> Tech[技术方案评审]
    Tech --> Test[测试用例评审]
    Test --> Launch[上线前产品/UI交互验收]
    Launch --> Online[线上验收]
    Online --> End([结束])
  
  
    PRD --- PRD_Info["时间点: PRD文档完成后
    参与人员: 产品经理/技术开发/测试
    评审目标: 验证需求完整性"]
  
    UI --- UI_Info["时间点: 设计完成后
    参与人员: 设计师/技术开发/测试
    评审目标: 符合前端用户交互UI设计&验收标准"]
  
    Tech --- Tech_Info["时间点: 技术方案完成后
    参与人员: 技术开发
    评审目标: 确认方案合理性"]
  
    Test --- Test_Info["时间点: 开发完成前
    参与人员: 测试/产品
    评审目标: 确认测试覆盖"]
  
    Launch --- Launch_Info["时间点: 测试完成后
    参与人员: 产品经理等
    评审目标: 确认功能完整/符合前端用户交互UI设计&验收标准"]
  
    Online --- Online_Info["时间点: 上线后
    参与人员: 产品经理、测试
    评审目标: 验证线上效果是否和预期一致"]
```

## 二、各阶段评审检查清单

### PRD评审检查清单

[PRD评审表](https://github.com/Taskon-xyz/PR/edit/main/PRD%E8%AF%84%E5%AE%A1%E8%A1%A8.md)

### UI设计评审检查清单

[前端用户交互UI设计&验收标准](https://github.com/Taskon-xyz/PR/blob/main/%E5%89%8D%E7%AB%AF%E7%94%A8%E6%88%B7%E4%BA%A4%E4%BA%92UI%E8%AE%BE%E8%AE%A1%26%E9%AA%8C%E6%94%B6%E6%A0%87%E5%87%86.md)

### 技术方案评审检查清单

[技术方案评审表](https://github.com/Taskon-xyz/PR/blob/main/%E6%8A%80%E6%9C%AF%E6%96%B9%E6%A1%88%E8%AF%84%E5%AE%A1%E8%A1%A8.md)

### 测试准入标准检查清单

[测试准入标准（开发联调输出质量）](测试准入标准（开发联调输出质量）.md)

### 测试准出标准检查清单

[测试准出标准（可发生产）](测试准出标准.md)

### 测试用例评审检查清单

[测试计划评审表](https://github.com/Taskon-xyz/PR/blob/main/%E6%B5%8B%E8%AF%95%E8%AE%A1%E5%88%92%E8%AF%84%E5%AE%A1%E8%A1%A8.md)



## 三、问题跟踪与状态流转

### 问题状态流转图

```mermaid
flowchart LR
    Start([开始]) --> A[待解决]
    A -->|责任人接受任务| B[处理中]
    B -->|问题修复| C[待复核]
    C -->|评审通过| D[已解决]
    C -->|复核不通过| B
    A -->|P2/P3级别问题| E[延期处理]
    E -->|下阶段处理| B
    B -->|非问题/不修复| F[关闭]
    D --> End([结束])
    F --> End
  
    subgraph 问题分级
    P0[P0: 阻塞项]
    P1[P1: 重要问题]
    P2[P2: 次要问题]
    P3[P3: 建议事项]
    end
```

### 评审结果状态流转

```mermaid
flowchart LR
    Start([开始]) --> A[评审中]
    A -->|无P0/P1问题| B[通过]
    A -->|有P1问题但有方案| C[有条件通过]
    A -->|有P0问题| D[未通过]
    C -->|P1问题解决| B
    D -->|修改后重新评审| A
    B --> End([结束/进入下阶段])
```

## 四、角色与职责

```mermaid
flowchart TB
    PM[产品经理] -->|负责| PRD[PRD文档准备]
    PM -->|参与| UI_Review[UI评审]
    PM -->|参与| Test_Review[测试用例评审]
    PM -->|参与| Launch_Review[上线前评审]
    PM -->|负责| Online_Review[线上验收]
  
    Design[设计师] -->|负责| UI_Doc[UI设计文档]
    Design -->|参与| PRD_Review[PRD评审]
  
    Dev[开发负责人] -->|负责| Tech_Doc[技术方案]
    Dev -->|参与| PRD_Review
    Dev -->|参与| UI_Review
    Dev -->|参与| Test_Review
    Dev -->|参与| Launch_Review
    Dev -->|参与| Online_Review
  
    TL[团队Leader] -->|参与| Tech_Review[技术方案评审]
    TR[技术责任人] -->|参与| Tech_Review
  
    Test[测试负责人] -->|负责| Test_Case[测试用例]
    Test -->|参与| PRD_Review
    Test -->|参与| Tech_Review
    Test -->|参与| Launch_Review
  
    Biz[业务负责人] -->|参与| PRD_Review
    Biz -->|负责| Online_Review
```

## 五、变更管理流程

```mermaid
flowchart TD
    A[需求变更提出] --> B[变更影响评估]
    B --> C{是否重大变更?}
    C -->|是| D[变更评审]
    C -->|否| E[开发责任人评估]
    D --> F{决策结果}
    E --> F
    F -->|通过| G[变更执行]
    F -->|拒绝| H[反馈提出方]
  
    G --> I[通知相关方]
    G --> J[更新相关文档]
    G --> K[更新项目开发计划]
```

## 六、评审结果确认机制

```mermaid
sequenceDiagram
    participant A as 评审主持人
    participant B as 与会人员
    participant C as 问题跟踪系统
  
    A->>B: 主持评审会议
    B->>C: jira记录发现的问题
    C->>A: 生成问jira题清单
    A->>B: 确认问题分级和责任人
    B->>A: 确认评审结果
  
    alt 通过
        A->>B: 记录通过结论
    else 有条件通过
        A->>B: 记录有条件通过结论
        A->>C: jira记录P1问题解决方案和时间表
    else 未通过
        A->>B: 记录未通过结论
        A->>C: jira记录P0问题及重新评审时间
    end
  
    A->>B: 各方确认评审结果
```
