# Workspace Startup

Workspace Startup 用来在开始项目工作之前，先找到或初始化一个可复用的 Workspace。

仓库地址：[HouNextItem/workspace-startup](https://github.com/HouNextItem/workspace-startup)

## 它会做什么

- 查找已有的 Workspace 根目录
- 读取 `Agents.md` 和全局 Workspace 文档
- 在需要时创建标准 Workspace 文件
- 建议使用英文文件名和 `Project_###_ProjectName` 目录

## 标准 Workspace 文件

- `Agents.md`
- `Global_Workbench.md`
- `Compound_Learning_and_Pitfalls_Log.md`
- `New_Project_SOP.md`

## 说明

- `Agents.md` 是稳定入口
- 尽量不要使用带空格的文件名
- Workspace 根目录和项目目录都尽量使用英文
- 找到或创建 Workspace 后，要告诉用户
- 创建项目文件夹后，也要告诉用户项目目录名称
