# UI交互各角色检查清单

## 产品经理检查清单

### 用户体验检查

- [ ] 操作流程是否符合用户习惯与预期
- [ ] 是否满足所有用户需求与业务场景
- [ ] 重要信息是否易于获取
- [ ] 操作步骤是否足够简单直观
- [ ] 是否有清晰的引导流程帮助用户完成任务

### 功能完整性检查

- [ ] 所有规划的功能是否都已实现
- [ ] 异常场景是否有合理的处理机制
- [ ] 错误提示是否清晰易懂且提供解决方案
- [ ] 操作响应与状态反馈是否及时明确

### 一致性检查

- [ ] 交互方式是否在整个产品中保持一致
- [ ] 术语使用是否统一
- [ ] 各页面之间的功能组织结构是否一致

## UI设计师检查清单

### 视觉设计检查

- [ ] 视觉元素(颜色、排版、图标)是否保持一致性
- [ ] 界面是否遵循品牌设计规范
- [ ] 页面视觉层次是否清晰，重要内容是否突出
- [ ] 信息呈现是否简洁，避免过度设计与视觉噪音

### 交互设计检查

- [ ] 弹窗/模态框焦点管理是否合理
- [ ] 表单焦点管理是否符合自然阅读顺序
- [ ] 所有操作是否有即时明确的视觉反馈
- [ ] 状态变化是否平滑，有适当的过渡动画

### 布局设计检查

- [ ] 页面元素对齐是否统一规范
- [ ] 相关元素之间是否保持合适间距
- [ ] 重要内容是否放在用户视线易于到达的位置
- [ ] 页面结构是否清晰，层次分明
- [ ] 是否考虑了响应式设计，适应不同设备与屏幕

## 前端开发检查清单

### 功能实现检查

- [ ] 所有功能是否按照设计要求实现
- [ ] 输入控件状态是否清晰可见(普通、焦点、禁用、错误等状态)
- [ ] 特殊控件(如图片上传)是否有明确的限制提示
- [ ] 错误状态是否有醒目的视觉效果提示

### 交互实现检查

- [ ] 弹窗内焦点是否被锁定，不允许Tab键将焦点移出
- [ ] 弹窗关闭时焦点是否返回到触发元素上
- [ ] 表单Tab键导航顺序是否符合自然阅读顺序
- [ ] 是否实现了所有状态下的视觉反馈效果

### 性能优化检查

- [ ] 页面加载时间是否控制在3秒以内
- [ ] 交互响应时间是否不超过100ms
- [ ] 动画帧率是否保持在60fps以上
- [ ] 图片资源是否进行了优化压缩
- [ ] 是否合理使用了缓存机制
- [ ] 代码是否进行了压缩和合并

### 适配性检查

- [ ] 界面是否支持不同尺寸的屏幕
- [ ] 关键功能在各种尺寸下是否都能正常使用
- [ ] 文字和图片是否能自适应屏幕宽度

## 测试人员检查清单

### 功能测试

- [ ] 所有交互功能是否能正常工作
- [ ] 键盘操作是否完全可用(Tab键导航等)
- [ ] 各种状态下的视觉反馈是否正确
- [ ] 错误处理机制是否完善

### 边界条件测试

- [ ] 各类输入是否有合理的边界限制
- [ ] 当输入达到边界时是否有明确提示
- [ ] 异常输入是否有恰当的处理机制

### 错误处理测试

- [ ] 所有错误提示是否清晰易懂
- [ ] 错误提示位置是否醒目
- [ ] 是否提供了错误的解决方法
- [ ] 系统是否能从错误中恢复
