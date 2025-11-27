# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 项目概述

这是一个提示词模板库，专门用于存放大模型应用相关的优秀提示词、AI IDE规则等模板。项目采用分类管理方式，涵盖从基础通用模板到企业级专业应用的各种场景。

## 项目架构

### 模板分类体系
- **basic-prompts/**: 通用基础提示模板，适用于日常问题解答、信息获取等场景
- **specific-domains/**: 特定领域模板
  - **coding/**: 编程相关（代码生成、调试、优化等）
  - **ide-rules/**: AI辅助编程环境规则和代码审查标准
  - **writing/**: 写作相关（博客、报告、故事等）
  - **research/**: 研究相关（文献综述、假设验证等）
  - **design/**: 设计相关（界面设计、创意构思等）
  - **psychology/**: 心理学相关应用
- **advanced-prompts/**: 高级提示模板，用于多步骤推理任务
- **system-prompts/**: 系统级提示，定义AI助手角色和行为准则
- **美团/**: 企业级应用模板（交易退款、告警分析、工作流等）

### 工具集成系统
- **.catpaw/**: Catpaw工具集成
  - **rules/**: 提示词工程师规则和10种Prompt框架（ICIO、CRISPE、BROKE等）
  - **commands/**: speckit子命令集合（plan、analyze、implement等）
- **.specify/**: 规范驱动开发工作流
  - **memory/constitution.md**: 项目核心原则和质量标准
  - **scripts/bash/**: 自动化脚本（setup-plan.sh、create-new-feature.sh等）

## 开发工作流

### 模板创建流程
1. **需求识别**: 在相应分类目录下创建模板文件
2. **框架应用**: 使用.catpaw/rules/prompt-engineer.md中的10种Prompt框架
3. **质量检查**: 符合.specify/memory/constitution.md中的质量标准
4. **文档完善**: 包含使用说明、示例和边界情况处理

### 规范驱动开发
使用specify工具集进行规范化开发：
```bash
# 规划新功能
.catpaw/commands/speckit.plan.md

# 创建检查清单
.catpaw/commands/speckit.checklist.md

# 生成任务列表
.catpaw/commands/speckit.tasks.md
```

### 质量保证原则
- **模板优先设计**: 每个功能必须有明确的模板定义
- **质量优于数量**: 模板必须解决具体问题并通过验证
- **分类组织**: 严格按照用途和复杂度分类
- **文档驱动**: 每个模板包含完整的使用说明

## 常用命令

### 模板开发
```bash
# 查看项目结构
find . -name "*.md" -type f

# 验证模板格式
.catpaw/commands/speckit.checklist.md

# 创建新功能规范
.specify/scripts/bash/create-new-feature.sh
```

### 企业级模板
美团相关模板展示了复杂业务场景的应用：
- **交易TT退款助手**: 多层次信息提取和意图识别
- **告警分析助手**: 结构化数据提取和异常处理
- **Friday工作流**: 自动化工作流集成

## 模板标准

### 格式要求
- 使用Markdown格式，标题层次清晰
- 占位符使用花括号: {VARIABLE_NAME}
- 包含使用说明和示例
- 区分模板内容和注释说明

### 质量标准
- **清晰性**: 用途和用法立即可理解
- **具体性**: 解决明确的需求或问题
- **可测试性**: 可通过输入输出示例验证
- **适应性**: 跨多个AI模型和版本可用
- **可维护性**: 易于更新和改进

## 特殊注意事项

### 企业级应用
- 美团目录下的模板包含复杂的业务逻辑
- 涉及结构化数据提取（JSON格式输出）
- 需要处理边界情况和异常场景
- 严格遵循输出格式要求

### 提示词框架
.catpaw/rules/prompt-engineer.md定义了10种核心框架：
1. ICIO框架（指令-背景-输入-输出）
2. CRISPE框架（能力角色-洞察-声明-个性-实验）
3. BROKE框架（背景-角色-目标-关键结果-改进）
4. CREATE框架（清晰度-相关信息-实例-避免含糊-迭代）
5. TAG框架（任务-行动-目标）
6. RTF框架（角色-任务-格式）
7. ROSES框架（角色-目标-场景-解决方案-步骤）
8. APE框架（行动-目的-期望）
9. RACE框架（背景-行动-结果-示例）
10. TRACE框架（任务-请求-行动-语境-示例）

### 版本控制
- 模板版本遵循语义化版本控制（MAJOR.MINOR.PATCH）
- 重大变更需要更新版本号和变更日志
- 社区反馈应被整合到模板改进中