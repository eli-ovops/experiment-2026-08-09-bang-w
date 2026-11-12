# 家具行业中英翻译启动包

本包用于搭建“开源翻译软件 + 本地或在线大模型 + 家具行业术语表”的起步环境。

## 推荐软件

首选 [Supervertaler Workbench](https://github.com/Supervertaler/Supervertaler-Workbench)（MIT）：支持 Windows 独立包、Apple Silicon macOS 安装包、Ollama、本地/OpenAI 兼容模型、术语表、翻译记忆以及 DOCX、PDF、Markdown、TXT 等文档。

日常网页划词可选 [Pot](https://github.com/pot-app/pot-desktop)（GPL-3.0）：中文界面更友好，支持 Windows/macOS/Linux、划词、OCR 和离线 Ollama，但它不适合作为严格的家具术语库管理工具。

## 导入术语表

1. 在 Supervertaler 新建 English → Chinese 项目和术语库。
2. 选择 Import from TSV。
3. 导入 `furniture_glossary_en_zh.tsv`。
4. 将项目术语库设为 Project，翻译前抽查术语识别结果。
5. 做中译英项目时，新建 Chinese → English 术语库，再使用软件的 Reverse source/target 功能复制或反转该术语库；反转后必须人工抽查多义词。

## 接入模型

- 完全离线：安装 Ollama，下载适合机器内存的 Qwen 系列指令模型；在 Supervertaler 中选择 Ollama，默认地址为 `http://localhost:11434`。
- 接入在线大模型：选择 Custom (OpenAI-compatible) 或软件内置供应商。使用在线服务时，文档会发送给所选供应商，不适合未经授权的保密资料。
- 将 `furniture_translation_prompt_zh.txt` 保存为项目翻译提示词，并启用项目术语库。

## 重要边界

这是通用启动术语库，不是国家标准、客户标准或可直接签发的最终术语库。`veneer`、`laminate`、`upholstery`、`recliner` 等词会随产品结构和客户习惯变化。正式使用前，应以企业既有产品目录、报价单、BOM、说明书及客户确认译法为权威来源。

建议先选取一份 1–3 页的真实文件做双向试译，由熟悉产品的人逐项确认；确认后的译法再写回术语库和翻译记忆。

## 许可

本启动包中的原创术语整理、提示词和说明以 CC0 1.0 方式提供，可自由复制、修改和商用。第三方软件和模型分别遵守各自许可证；本包不包含第三方程序、模型权重或第三方文档内容。
