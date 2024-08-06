# WebFingerCat

![WebFingerCat Icon](<your-icon-url>)

WebFingerCat 是一款使用 Golang 研发的主动指纹探测、敏感信息和漏洞识别、收集工具，用于帮助安全工作人员开展工作。项目还在开发中。

## 功能特点

- **使用 Golang**：采用最轻便、最快速的爬虫框架 Colly。
- **高拓展性**：支持多层级配置的 `config.ini` 文件，方便定制化设置。
- **智能代理轮训**：多层级轮训代理结构，有效避免封禁和检测 IP。
- **反爬虫机制**：加入了多种反爬虫策略，提升爬取效率和隐蔽性。
- **指纹识别**：使用 Ehole 的指纹识别规则，确保高准确率的指纹检测。
- **支持 PoC**：目前支持 Xray PoC。

## 安装与使用

### 前提条件

- Go 1.18+
- Colly 爬虫框架

### 安装

```bash
go get -u github.com/gocolly/colly
go get -u gopkg.in/ini.v1
