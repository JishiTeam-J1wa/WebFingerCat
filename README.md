# WebFingerCat

![WebFingerCat Icon](<your-icon-url>)

WebFingerCat 是一款使用 Golang 研发的主动指纹探测、敏感信息和漏洞识别、收集工具，用于帮助安全工作人员开展工作。项目还在开发中。

## 🎯 功能特点

- **使用 Golang**：采用最轻便、最快速的爬虫框架 Colly。
- **高拓展性**：支持多层级配置的 `config.ini` 文件，方便定制化设置。
- **智能代理轮训**：多层级轮训代理结构，有效避免封禁和检测 IP。
- **反爬虫机制**：加入了多种反爬虫策略，提升爬取效率和隐蔽性。
- **指纹识别**：使用 Ehole 的指纹识别规则，确保高准确率的指纹检测。
- **支持 PoC**：目前支持 Xray PoC。

## 🚀 安装与使用

### 前提条件

- Go 1.18+
- Colly 爬虫框架

### 安装

```bash
go get -u github.com/gocolly/colly
go get -u gopkg.in/ini.v1
```

### 配置文件

创建 `config.ini` 文件，并进行如下配置：

```ini
[settings]
int = 10
max_response_size = 20MB
async = yes
ua = pc
fprox = yes
fproxyhttp = proxy.txt
inproxy = "http://127.0.0.1:7897"
baidutest = "https://baidu.com"

[UserAgents]
pc = Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3, Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Firefox/54.0
ios = Mozilla/5.0 (iPhone; CPU iPhone OS 10_3_1 like Mac OS X) AppleWebKit/603.1.30 (KHTML, like Gecko) Version/10.0 Mobile/14E304 Safari/602.1
android = Mozilla/5.0 (Linux; Android 7.0; Nexus 6P Build/NRD90M) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Mobile Safari/537.36, Mozilla/5.0 (Linux; Android 8.0; Pixel 2 Build/OPD1.170816.004) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.3202.94 Mobile Safari/537.36
mac = Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/602.3.12 (KHTML, like Gecko) Version/10.0.3 Safari/602.3.12, Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/11.1.2 Safari/605.1.15
```

### 使用

```bash
go run main.go -u <URL>        # 扫描单个 Web 应用
go run main.go -f <file.txt>   # 从 txt 文档中读取 URL 进行扫描
```

### 示例

```bash
go run main.go -u https://example.com
```

```bash
go run main.go -f targets.txt
```

### 输出

```plaintext
你好,big hack: 测试用户
线程数数量： 10
爬虫深度为： 1
没有提供代理，将不使用代理。
[+]http://example.com    [Example Domain] [200] [394.26KB] [识别失败]
扫描完成。
```

## 🤝 贡献

欢迎提交 Issue 和 Pull Request 来参与项目开发。谢谢！

## 📜 许可证

本项目基于 [MIT 许可证](LICENSE)。

## 📧 联系

如有任何问题或建议，请通过邮箱联系：example@example.com

## 📁 项目结构

```
WebFingerCat
├── finder
│   ├── finderscan.go
├── main.go
├── config.ini
├── README.md
└── LICENSE
```

## 🙏 感谢

感谢所有为 WebFingerCat 做出贡献的开发者和社区成员。

---

WebFingerCat is a Golang-based tool for proactive fingerprint detection, sensitive information and vulnerability identification, and collection, designed to assist security professionals in their work. The project is still under development.

## Features

- **Golang**: Built with the lightweight and fast Colly crawler framework.
- **High Extensibility**: Supports multi-level configuration through `config.ini` for easy customization.
- **Smart Proxy Rotation**: Multi-level proxy rotation structure to effectively avoid IP bans and detection.
- **Anti-Crawling Mechanisms**: Includes various anti-crawling strategies to enhance crawling efficiency and stealth.
- **Fingerprint Recognition**: Utilizes Ehole's fingerprint recognition rules for high-accuracy fingerprint detection.
- **PoC Support**: Currently supports Xray PoC.

## Installation and Usage

### Prerequisites

- Go 1.18+
- Colly Crawler Framework

### Installation

```bash
go get -u github.com/gocolly/colly
go get -u gopkg.in/ini.v1
```

### Configuration File

Create `config.ini` file and configure as follows:

```ini
[settings]
int = 10
max_response_size = 20MB
async = yes
ua = pc
fprox = yes
fproxyhttp = proxy.txt
inproxy = "http://127.0.0.1:7897"
baidutest = "https://baidu.com"

[UserAgents]
pc = Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/58.0.3029.110 Safari/537.3, Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Firefox/54.0
ios = Mozilla/5.0 (iPhone; CPU iPhone OS 10_3_1 like Mac OS X) AppleWebKit/603.1.30 (KHTML, like Gecko) Version/10.0 Mobile/14E304 Safari/602.1
android = Mozilla/5.0 (Linux; Android 7.0; Nexus 6P Build/NRD90M) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/56.0.2924.87 Mobile Safari/537.36, Mozilla/5.0 (Linux; Android 8.0; Pixel 2 Build/OPD1.170816.004) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.3202.94 Mobile Safari/537.36
mac = Mozilla/5.0 (Macintosh; Intel Mac OS X 10_12_6) AppleWebKit/602.3.12 (KHTML, like Gecko) Version/10.0.3 Safari/602.3.12, Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_6) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/11.1.2 Safari/605.1.15
```

### Usage

```bash
go run main.go -u <URL>        # Scan a single web application
go run main.go -f <file.txt>   # Scan web applications listed in a text file
```

### Examples

```bash
go run main.go -u https://example.com
```

```bash
go run main.go -f targets.txt
```

### Output

```plaintext
你好,big hack: 测试用户
线程数数量： 10
爬虫深度为： 1
没有提供代理，将不使用代理。
[+]http://example.com    [Example Domain] [200] [394.26KB] [识别失败]
扫描完成。
```

## Contributions

We welcome issues and pull requests for project development. Thank you!

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any questions or suggestions, please contact us via email: example@example.com

## Project Structure

```
WebFingerCat
├── finder
│   ├── finderscan.go
├── main.go
├── config.ini
├── README.md
└── LICENSE
```

## Acknowledgements

We would like to thank all the developers and community members who contributed to WebFingerCat.
