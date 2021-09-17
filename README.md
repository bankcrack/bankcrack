# 网银爬虫 BankCrack Project

自动通过网银抓取银行卡余额、流水信息，以及配套的管理工具。

用例：
- 导出银行卡的流水记录，用于账本制作
- 实时抓取银行卡流水变动，实现银行卡收款系统

## 特性

- 动态配置账号信息
- 抓取完后保存浏览器状态，登录信息未过期的情况下无需重新登录，防止频繁登录导致风控
- 登录信息过期后，支持自动重新登录
- 使用 Selenium，使用真实的浏览器绕过检测
- 使用虚拟键盘内核驱动，模拟真实键盘操作，绕过控件检测
- WebHook 异步通知
- REST API 同步查询数据
- 检测填写图形验证码
- 通知、等待并自动填写短信验证码
- 支持异常状态通知
- 支持配置代理IP

## 支持的银行

| ID   | 银行             | 浏览器 | 需安装控件 | 需要内核驱动 | 图形验证码 | 短信验证码 |
| ---- | ---------------- | ------ | ---------- | ------------ | ---------- | ---------- |
| ABC  | 中国农业银行     | IE     | 独立程序   | ✔            | ✔          | ⭕          |
| BOC  | 中国银行         | Chrome |            |              | ✔          |            |
| CCB  | 中国建设银行     | Chrome |            |              | ⭕          | ⭕          |
| CMB  | 招商银行         | IE     | ActiveX    | ✔            |            | ⭕          |
| ICBC | 中国工商银行     | IE     | ActiveX    | ✔            | ✔          |            |
| PSBC | 中国邮政储蓄银行 | Chrome | 独立程序   | ✔            | ✔          |            |

> ✔: 必需的
> ⭕: 可能出现的、可选的

## 技术栈

1. 爬虫: Python + Selenium + Chrome/IE Driver
2. MITM: Golang
3. 虚拟键盘内核驱动: C语言 + WDK
    - 支持 Windows 10
4. Android 短信监听 (未完成): Kotlin
5. Web 控制面板 (未完成)
    1. API Server: Golang
    2. Web UI: Vue / React

## 项目状态

项目此前为内部使用，目前整理中，暂未公开。

- 需要获取早期试用版本的
- 需要获取项目源代码的
- 需要新增银行支持的
- 需要定制修改的

请联系我们：bankcrack@protonmail.com
