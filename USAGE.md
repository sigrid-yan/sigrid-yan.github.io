# Hexo 博客使用文档

## 快速开始

### 安装依赖

首次克隆仓库后，需要安装依赖：

```bash
npm install
```

### 本地预览

启动本地服务器，实时预览博客：

```bash
npx hexo server
# 或简写
npx hexo s
```

访问：http://localhost:4000

按 `Ctrl + C` 停止服务器

## 文章管理

### 创建新文章

```bash
npx hexo new "文章标题"
# 或简写
npx hexo n "文章标题"
```

这会在 `source/_posts/` 目录下创建一个新的 Markdown 文件。

### 创建草稿

```bash
npx hexo new draft "草稿标题"
```

草稿保存在 `source/_drafts/` 目录，不会被发布。

### 发布草稿

```bash
npx hexo publish "草稿标题"
```

草稿会从 `_drafts` 移动到 `_posts` 目录。

### 文章格式

每篇文章都是 Markdown 文件，开头包含 Front Matter：

```markdown
---
title: 文章标题
date: 2025-10-09 22:40:00
tags: [标签1, 标签2, 标签3]
categories: 分类名称
---

这里开始写正文内容...

## 一级标题

### 二级标题

- 列表项 1
- 列表项 2

**粗体文字**

*斜体文字*

`代码`

\```cpp
// 代码块
#include <iostream>
int main() {
    std::cout << "Hello World!" << std::endl;
    return 0;
}
\```
```

### Front Matter 常用字段

- `title`: 文章标题
- `date`: 发布日期
- `updated`: 更新日期（可选）
- `tags`: 标签（可以有多个）
- `categories`: 分类（可以有多个）
- `description`: 文章描述（可选）
- `comments`: 是否开启评论（可选）

## 页面管理

### 创建新页面

```bash
npx hexo new page "页面名称"
```

例如创建"关于"页面：

```bash
npx hexo new page about
```

这会在 `source/about/` 创建 `index.md` 文件。

## 构建与部署

### 清理缓存

```bash
npx hexo clean
```

清理生成的静态文件和缓存。

### 生成静态文件

```bash
npx hexo generate
# 或简写
npx hexo g
```

生成的文件在 `public/` 目录。

### 生成并启动服务器

```bash
npx hexo generate
npx hexo server
# 或一条命令
npx hexo s -g
```

### 部署到 GitHub Pages

本项目配置了 GitHub Actions 自动部署：

```bash
# 1. 添加修改
git add .

# 2. 提交更改
git commit -m "添加新文章"

# 3. 推送到 GitHub
git push origin main
```

推送后，GitHub Actions 会自动构建和部署。

## 常用命令速查

| 命令 | 简写 | 说明 |
|------|------|------|
| `hexo new "title"` | `hexo n "title"` | 创建新文章 |
| `hexo new page "name"` | - | 创建新页面 |
| `hexo new draft "title"` | - | 创建草稿 |
| `hexo publish "title"` | `hexo p "title"` | 发布草稿 |
| `hexo generate` | `hexo g` | 生成静态文件 |
| `hexo server` | `hexo s` | 启动本地服务器 |
| `hexo deploy` | `hexo d` | 部署网站 |
| `hexo clean` | - | 清理缓存文件 |
| `hexo version` | - | 查看版本信息 |
| `hexo --help` | - | 查看帮助 |

## 配置文件

### 站点配置：`_config.yml`

主要配置项：

```yaml
# 站点信息
title: 网站标题
subtitle: 副标题
description: 网站描述
author: 作者名

# URL
url: https://sigrid-yan.github.io
root: /

# 文章
new_post_name: :title.md
default_layout: post
per_page: 10

# 主题
theme: landscape
```

修改配置后需要重启服务器。

### 主题配置：`_config.landscape.yml`

主题特定的配置文件。

## 目录结构

```
.
├── .github/
│   └── workflows/
│       └── pages.yml        # GitHub Actions 配置
├── node_modules/            # npm 依赖（不提交）
├── public/                  # 生成的静态文件（不提交）
├── scaffolds/               # 文章模板
│   ├── draft.md            # 草稿模板
│   ├── page.md             # 页面模板
│   └── post.md             # 文章模板
├── source/                  # 源文件
│   └── _posts/             # 文章目录
├── themes/                  # 主题目录
├── _config.yml             # 站点配置
├── _config.landscape.yml   # 主题配置
├── package.json            # 项目依赖
└── README.md               # 项目说明
```

## 写作技巧

### 1. 使用标签和分类

标签用于描述文章内容的关键词：

```yaml
tags: [C++, 学习笔记, 指针]
```

分类用于组织文章结构：

```yaml
categories:
  - 编程语言
  - C++
```

### 2. 插入图片

将图片放在 `source/images/` 目录：

```markdown
![图片描述](/images/picture.jpg)
```

### 3. 引用代码

使用三个反引号标记代码块：

\```cpp
#include <iostream>
int main() {
    std::cout << "Hello!" << std::endl;
}
\```

### 4. 插入链接

```markdown
[链接文字](https://example.com)
```

### 5. 文章摘要

使用 `<!-- more -->` 标记，前面的内容会作为摘要：

```markdown
这是文章摘要部分...

<!-- more -->

这是文章详细内容...
```

## 主题定制

### 安装新主题

```bash
# 克隆主题到 themes 目录
git clone https://github.com/theme-name themes/theme-name

# 修改 _config.yml
theme: theme-name

# 安装主题依赖
npm install
```

### 常用主题推荐

- **NexT**: https://github.com/next-theme/hexo-theme-next
- **Butterfly**: https://github.com/jerryc127/hexo-theme-butterfly
- **Fluid**: https://github.com/fluid-dev/hexo-theme-fluid
- **Icarus**: https://github.com/ppoffice/hexo-theme-icarus

## 插件扩展

### 安装插件

```bash
npm install <plugin-name> --save
```

### 常用插件

- **hexo-generator-feed**: RSS 订阅
- **hexo-generator-sitemap**: 生成站点地图
- **hexo-generator-search**: 本地搜索
- **hexo-deployer-git**: Git 部署

安装示例：

```bash
npm install hexo-generator-feed --save
npm install hexo-generator-sitemap --save
```

## 故障排除

### 清理重建

遇到问题时，先尝试清理缓存：

```bash
npx hexo clean
rm -rf node_modules
npm install
npx hexo generate
```

### 常见问题

**问题 1**: 文章不显示

- 检查 Front Matter 格式是否正确
- 确认日期格式：`YYYY-MM-DD HH:mm:ss`
- 运行 `hexo clean` 清理缓存

**问题 2**: 本地预览正常但部署后样式错误

- 检查 `_config.yml` 中的 `url` 和 `root` 配置
- 确认静态资源路径正确

**问题 3**: 推送到 GitHub 后没有自动部署

- 检查 GitHub Actions 是否启用
- 查看 Actions 标签页的错误日志
- 确认 GitHub Pages 设置为 GitHub Actions

## 更多资源

- **Hexo 官方文档**: https://hexo.io/zh-cn/docs/
- **Hexo 主题列表**: https://hexo.io/themes/
- **Hexo 插件列表**: https://hexo.io/plugins/
- **Markdown 语法**: https://markdown.com.cn/

## 工作流程示例

### 日常写作流程

1. 创建新文章
```bash
npx hexo new "今日学习：C++ 智能指针"
```

2. 编辑文章
```bash
# 使用你喜欢的编辑器打开
# source/_posts/今日学习：C++-智能指针.md
```

3. 本地预览
```bash
npx hexo s
```

4. 提交发布
```bash
git add .
git commit -m "添加文章：C++ 智能指针"
git push origin main
```

5. 等待自动部署完成，访问网站查看效果

---

**祝写作愉快！** 🎉
