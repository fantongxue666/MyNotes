**Git 提交写的好，省的同事老来找。**



Git 提交模板如下：

```properties
# 1. Type of change:

# feat - A new feature | 新功能
# fix A bug fix | Bug 修复
# docs - Documentation only changes | 仅文档修改
# style - Changes that do not affect the meaning of the code  | 格式化代码
# refactor - A code change that a neither fixes a bug nor adds a feature | 既不修复错误也不添加功能的代码更改
# perf - A code change that improves performance | 提高性能的代码更改
# test - Adding missing tests or correcting existing tests | 添加缺失的测试或更正现有测试用例
# build Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
# ci - Changes to our Cl configuration files and scripts | 对Cl配置文件和脚本的更改
# chore - Other changes that don't modify src or test files | 不修改src或 test 文件的其他更改
# revert Reverts a previous commit | 还原提交

# 2. Scope of this of change | 影响范围

# 3. Short description | 简述

# 4. Long description | 详细描述

# 5. Closed issues | 关闭的问题

-----------------------------------

example :

feat: Model模块增加基础配置

1. 全局 ignore 文件
2. 增加 local 配置
3. 增加单元测试
4. 增加模型相关初始化脚本；

Closes xxx xxx xxx 
```



如果使用 IDEA 作为开发工具，建议使用插件  Git Commit Template 。

[Git Commit Template](https://plugins.jetbrains.com/plugin/9861-git-commit-template)