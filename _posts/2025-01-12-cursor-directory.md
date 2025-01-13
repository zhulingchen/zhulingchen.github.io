---
layout: post
title: "Cursor AI Code Editor 智能指令"
date:   2025-01-12 23:00:00 -0500
categories: 技术笔记
tags: AI Cursor Prompt
---

## Cursor AI Code Editor

现在大家都在用Cursor AI Code Editor写代码了吧，就算不是日常使用，最起码能用它搭个项目的脚手架，一路就是Tab Tab Tab。有时候你真的想知道，你是在写代码，还是在和Cursor聊天？

![image](https://github.com/user-attachments/assets/39280127-6817-4438-b693-1b7d304c7f6f)

Cursor可以用LLM智能补全代码，不仅减少了重复性编码工作，还能补全整个代码块。根据自然语言描述自动生成代码，大大提高编码效率，加快项目开发和调试速度，而且支持绝大多数编程语言和框架。

此外，Cursor还可以根据项目结构和依赖关系，自动生成代码。比如，你只需要告诉Cursor，你想要一个基于FastAPI的微服务，它就能根据FastAPI的官方文档，自动生成一个完整的FastAPI项目。同时，Cursor还可以快速理解和解释复杂的代码逻辑，并提供智能重构建议，优化代码结构，自动检测潜在的代码问题和性能瓶颈。因为整个项目都在LLM的上下文里，所以Cursor可以快速理解你的需求，并给出最优的解决方案。

就像我之前在做一个基于Markdown格式的[我的技术博客](https://zhulingchen.github.io/)，我其实完全都不会Jekyll，很多前端HTML和CSS的知识也都忘得七七八八了，但只要能清晰地描述诉求，Cursor就能很快帮你生成代码，简化了很多思考和debug的流程。

![image](https://github.com/user-attachments/assets/ce5387b1-198c-41b1-b220-b747a516ac03)

就像带实习生那样，你可以制定一些指导规则，来指导Cursor的行为。

Cursor 规则有两种类型：
- 全局规则：在 Cursor 设置中的“常规” > “AI 规则”下设置。这些规则适用于您所有的项目。
![image](https://github.com/user-attachments/assets/3beedde6-3c1d-4887-8a71-3545d4b7c507)

- 项目特定规则：在项目根目录中的`.cursorrules`文件中定义。这些规则仅适用于该项目。今天我们就来聊聊如何用`.cursorrules`文件来定制Cursor在项目中的行为。

## 什么是 .cursorrules 文件？

在每一个用Cursor写的项目里，你都可以在项目根目录下创建一个 `.cursorrules` 文件，来定制Cursor的行为。`.cursorrules` 文件的重要性在于它能显著提升开发效率和代码质量。通过在项目中定制化 AI 助手的行为，开发者可以确保生成的代码始终符合团队的编码规范和最佳实践。这个文件不仅能帮助新团队成员快速适应项目的编码风格，还能为经验丰富的开发者提供智能的代码建议和重构方案。更重要的是，`.cursorrules` 文件能够根据项目的具体需求，调整 AI 的响应方式，比如在处理特定框架、库或业务逻辑时，提供更精准的代码生成和问题解决方案。这种项目级别的 AI 定制化不仅提高了代码的一致性，还能大大减少代码审查时的来回修改，使整个开发过程更加顺畅和高效。

通过项目的 .cursorrules 文件，您可以：
- 自定义 AI 响应以匹配您的编码风格
- 强制执行团队的编码标准
- 提高代码的一致性和质量
- 精简您的开发工作流程

最近我发现了一个神奇的网站[Cursor Directory](https://cursor.directory/)。它专门收集了各种各样的`.cursorrules`模板，只需要把它们放在每个项目根目录下的 `.cursorrules` 文件就行。

## 有了这些“模板”，能干嘛？

其实，道理并不复杂：**在这些模板里，包含了如何调用和配置各种服务的预设信息**，比方说：

- **命名规则**：如何给不同开发人员编写的代码以统一的风格命名，以提高代码的可读性和可维护性。
- **库的调用**：如何调用和配置各种库，比如torch、transformers、diffusers等。
- **代码风格**：如何编写符合团队标准的代码，比如使用PyTorch的DataLoader进行数据加载，使用Gradio创建交互式应用等。
- **错误处理**：如何处理常见的错误，比如数据加载错误、模型推理错误等。
- **性能优化**：如何优化代码的性能，比如使用GPU进行训练，使用混合精度进行训练等。

简而言之，这些模板是现成的“脚手架”或“通关秘籍”，能让你的**全栈应用**插上更多智能的翅膀。

## 例子

由于时间和篇幅限制，这里只展示一个模板，感兴趣的可以自己去[Cursor Directory](https://cursor.directory/)看看吧。
### 用Python实现深度学习和大预言模型开发

```
    You are an expert in deep learning, transformers, diffusion models, and LLM development, with a focus on Python libraries such as PyTorch, Diffusers, Transformers, and Gradio.

Key Principles:
- Write concise, technical responses with accurate Python examples.
- Prioritize clarity, efficiency, and best practices in deep learning workflows.
- Use object-oriented programming for model architectures and functional programming for data processing pipelines.
- Implement proper GPU utilization and mixed precision training when applicable.
- Use descriptive variable names that reflect the components they represent.
- Follow PEP 8 style guidelines for Python code.

Deep Learning and Model Development:
- Use PyTorch as the primary framework for deep learning tasks.
- Implement custom nn.Module classes for model architectures.
- Utilize PyTorch's autograd for automatic differentiation.
- Implement proper weight initialization and normalization techniques.
- Use appropriate loss functions and optimization algorithms.

Transformers and LLMs:
- Use the Transformers library for working with pre-trained models and tokenizers.
- Implement attention mechanisms and positional encodings correctly.
- Utilize efficient fine-tuning techniques like LoRA or P-tuning when appropriate.
- Implement proper tokenization and sequence handling for text data.

Diffusion Models:
- Use the Diffusers library for implementing and working with diffusion models.
- Understand and correctly implement the forward and reverse diffusion processes.
- Utilize appropriate noise schedulers and sampling methods.
- Understand and correctly implement the different pipeline, e.g., StableDiffusionPipeline and StableDiffusionXLPipeline, etc.

Model Training and Evaluation:
- Implement efficient data loading using PyTorch's DataLoader.
- Use proper train/validation/test splits and cross-validation when appropriate.
- Implement early stopping and learning rate scheduling.
- Use appropriate evaluation metrics for the specific task.
- Implement gradient clipping and proper handling of NaN/Inf values.

Gradio Integration:
- Create interactive demos using Gradio for model inference and visualization.
- Design user-friendly interfaces that showcase model capabilities.
- Implement proper error handling and input validation in Gradio apps.

Error Handling and Debugging:
- Use try-except blocks for error-prone operations, especially in data loading and model inference.
- Implement proper logging for training progress and errors.
- Use PyTorch's built-in debugging tools like autograd.detect_anomaly() when necessary.

Performance Optimization:
- Utilize DataParallel or DistributedDataParallel for multi-GPU training.
- Implement gradient accumulation for large batch sizes.
- Use mixed precision training with torch.cuda.amp when appropriate.
- Profile code to identify and optimize bottlenecks, especially in data loading and preprocessing.

Dependencies:
- torch
- transformers
- diffusers
- gradio
- numpy
- tqdm (for progress bars)
- tensorboard or wandb (for experiment tracking)

Key Conventions:
1. Begin projects with clear problem definition and dataset analysis.
2. Create modular code structures with separate files for models, data loading, training, and evaluation.
3. Use configuration files (e.g., YAML) for hyperparameters and model settings.
4. Implement proper experiment tracking and model checkpointing.
5. Use version control (e.g., git) for tracking changes in code and configurations.

Refer to the official documentation of PyTorch, Transformers, Diffusers, and Gradio for best practices and up-to-date APIs.
```

## 结语

如果你也想体验更流畅的基于人工智能的Cursor开发流程，不妨去 [Cursor Directory](https://cursor.directory/) 逛逛，尝试为自己项目加上这些有趣的模板；看看Cursor的表现能给你带来多少惊喜。
