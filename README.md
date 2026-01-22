# Some Practical Skills

实用的 AI 编码助手技能集合。

## 可用技能

### git_changelog_analyzer

自动分析 Git 变更并生成符合 Conventional Commits 规范的提交信息，特别针对 Python 项目进行了优化。

## 安装

### 前置要求

- **Node.js** 20.6+
- **Git**（用于克隆仓库）

### 安装步骤

#### 从 GitHub 仓库安装（推荐）

```bash
# 安装整个技能集合
npx openskills install <your-username>/some_practical_skills

# 或安装单个技能（从本地路径）
npx openskills install ./git_changelog_analyzer
```

#### 安装选项

```bash
# 项目本地安装（默认：./.claude/skills）
npx openskills install ./git_changelog_analyzer

# 全局安装（~/.claude/skills）
npx openskills install ./git_changelog_analyzer --global

# 通用模式安装（./.agent/skills，适用于多代理环境）
npx openskills install ./git_changelog_analyzer --universal
```

#### 同步 AGENTS.md

安装后，运行以下命令更新 `AGENTS.md`：

```bash
npx openskills sync
```

## 使用方法

安装并同步后，技能会自动出现在 `AGENTS.md` 的可用技能列表中。在 AI 编码助手中使用时，可以通过以下方式加载技能：

```bash
npx openskills read git_changelog_analyzer
```

## 管理技能

```bash
# 列出已安装的技能
npx openskills list

# 更新所有技能
npx openskills update

# 更新特定技能
npx openskills update git_changelog_analyzer

# 移除技能
npx openskills remove git_changelog_analyzer

# 交互式管理
npx openskills manage
```

## 参考

- [OpenSkills 官方文档](https://github.com/numman-ali/openskills)
