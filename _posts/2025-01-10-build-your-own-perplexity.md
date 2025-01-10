---
layout: post
title: "打造自己的Perplexity — 本地部署 Gemini Search前端"
date:   2025-01-10 11:00:00 -0500
categories: 技术笔记
tags: Gemini AI LLM github
---

## 欢迎来到我的公众号

大家好！这是我的第一篇公众号文章。这个公众号叫**「猫哥的技术杂货铺」**，本意就是分享一下在各处（例如 medium, dev.to, X/推特，还有 GitHub，等等等等）看到的各种有趣的技术介绍和开源项目。希望大家能够喜欢。

## 前言

最近，很多人可能更喜欢用 Perplexity 去代替 Google 当搜索引擎，因为它不仅界面简洁，可以包含真实出处链接的准确答案，而不是 hallucination，让人觉得更加真实可信。

与此同时，Google 推出的 Gemini 2.0 Flash 模型引起了广泛关注 —— 但 Perplexity 还没有支持。

今天，我将介绍一个名为 **Gemini-Search** 的开源项目，它允许你在本地部署一个基于 **Gemini 2.0 Flash 模型**的搜索引擎前端。本文将详细介绍如何使用 Node.js 在本地搭建这个平台。该项目主要用 TypeScript 开发。


## 什么是 Gemini-Search？

**Gemini-Search** 是一个使用 Node.js 构建的简单易用的本地搜索引擎。它利用 Google 的 Gemini 模型进行文本理解和搜索，允许你通过类似于 Perplexity 的用户界面进行查询。这个项目的优点在于：

- **本地部署**：你可以在自己的电脑上运行，无需依赖云服务，保护个人隐私。  
- **简单易用**：通过简洁的界面进行搜索，操作简单直观。  
- **高度可定制**：你可以根据自己的需求进行修改和扩展。  
- **开源免费**：任何人都可以免费使用和贡献。


## 准备工作

在开始部署之前，你需要准备以下环境：

1. **Node.js 和 npm**  
   确保你的电脑上已经安装了 Node.js 和 npm（Node.js 包管理器）。你可以从 [Node.js 官网](https://nodejs.org/) 下载安装。  
   > **注意：** 个人亲测需要 Node.js v18 版本以上才能成功运行。

2. **Git**  
   用于从 GitHub 下载项目代码。

3. **Google AI Studio API密钥**  
   可以从 [https://aistudio.google.com/apikey](https://aistudio.google.com/apikey) 获取。


## 部署步骤

### 1. 克隆代码

首先，打开你的终端（Windows 用户可以使用 cmd, PowerShell 或者 Git Bash），并执行以下命令来克隆 Gemini-Search 项目的代码：

```bash
git clone https://github.com/ammaarreshi/Gemini-Search.git
cd Gemini-Search
```

这会将项目代码下载到你的本地电脑，并进入项目文件夹。

（然而，这个哥们把node_modules/目录也push进repo了，手动狗头……所以clone的时候可能需要多等几分钟；repo上好几个PR都在吐槽这个事情……）

![tfugj4n3l6ez](https://github.com/user-attachments/assets/4e1d61b3-eb1a-452c-83d9-f737faf3bbe3)

### 2. 安装依赖

在项目文件夹中，运行以下命令来安装项目所需的依赖：

```bash
npm install
```

这个命令会读取 package.json 文件，并安装所有必要的 Node.js 模块。

### 3. 配置环境变量

你需要创建一个 .env 文件，并在其中配置你的 Google Cloud API 密钥。在项目根目录下创建一个名为 .env 的文件，内容如下：

GOOGLE_API_KEY=<你的Google AI Studio API密钥>

将 "<你的Google AI Studio API密钥>" 替换为你实际的 API 密钥。

### 4. 运行项目

完成以上步骤后，你就可以运行项目了。在终端中执行以下命令：

```bash
npm run dev
```

如果一切顺利，你将看到终端输出类似 "serving on port 3000" 的信息。

![image](https://github.com/user-attachments/assets/6484be0c-7f7d-4944-ac5b-ebf181016574)

### 5. 访问应用

打开你的浏览器，输入 http://localhost:3000，你就可以看到 Gemini-Search 的用户界面了。现在你就可以开始使用 Gemini 2.0 模型进行本地搜索了。

以下为运行截图。

![image](https://github.com/user-attachments/assets/f5b39b96-14e4-4897-a461-6f33efeef010)

![image](https://github.com/user-attachments/assets/60ce4041-ad47-453a-99f6-4d7d95e8a2bb)

### 6. 产品部署

如果自己有服务器的话，还可以运行以下命令后直接部署上线：

```bash
npm run build
npm run start
```

## 深入了解

### 代码结构
你可以查看项目中的 index.js 文件，了解项目是如何使用 Node.js 和 Google Gemini API 进行搜索的。

### 自定义修改
你可以根据自己的需求，修改前端页面 (例如 index.html) 或者后端代码 (例如 index.js)，实现更多功能。

### 安全性
请注意，将 API 密钥直接存放在 .env 文件中可能存在安全风险，请务必在生产环境中考虑更安全的存储方式。

## 后记

这是我第一次写微信公众号文章。为了更方便地排版，我采用了 Markdown 格式，然后用[https://doocs.github.io/md](https://doocs.github.io/md)渲染成微信图文。这个网站本身也是一个很不错的开源项目：[https://github.com/doocs/md](https://github.com/doocs/md)，值得 star！
