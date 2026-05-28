---
name: image-text-extractor
description: |
  Extracts text from images by executing a local Java OCR script. 
  Use when the user wants to recognize text in an image, convert screenshots to text, 
  or asks "what is written in this picture".
---

# Image Text Extraction Skill

## 1. 触发条件 (Triggers)
当用户的意图包含以下场景时自动激活：
- 要求识别、提取、读取图片或截图中的文字/内容。
- 询问“这张图里写了什么”、“帮我转成文本”等类似指令。
- 明确提供了图片路径并要求进行文字解析。

## 2. 执行参数 (Parameters)
- **image_path** (必填): 待处理图片的绝对路径或相对路径（例如: `/path/to/image.png`）。

## 3. 执行流程 (Execution Workflow)

### Step 1: 验证与准备
- 检查用户是否提供了有效的 `image_path`。若未提供，需主动询问用户补充图片路径。
- 确认本地环境存在 `scripts/Air-Agents.jar` 文件。

### Step 2: 执行命令
- 在终端/Shell 中执行以下命令：
  ```bash
  java -jar scripts/Air-Agents.jar {image_path}