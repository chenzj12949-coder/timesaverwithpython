# Manner 兼职班次自动监控系统

## 项目简介

本项目用于自动监控 Manner 咖啡兼职招聘班次信息，并根据预设条件自动筛选符合要求的门店岗位。当检测到目标门店出现新的可报名班次时，系统会自动发送提醒通知，帮助用户第一时间获取兼职机会。

## 主要功能

### 自动获取岗位数据
- 定时请求 Manner 招聘接口
- 自动解析返回的岗位信息
- 支持持续轮询监控

### 门店筛选
- 支持配置指定门店名称
- 仅关注目标门店岗位
- 自动忽略其他门店信息

### 新岗位检测
- 自动记录已发现岗位
- 识别新增班次
- 避免重复提醒

### 消息推送
支持以下通知方式：

- 企业微信机器人
- Telegram Bot
- 邮件通知
- Bark 推送
- Server酱
- 钉钉机器人

可根据实际需求自行扩展。

---

## 项目结构

text project/ │ ├── main.py                # 主程序 ├── config.py              # 配置文件 ├── stores.txt             # 目标门店列表 ├── cache.json             # 已检测岗位缓存 ├── requirements.txt       # 依赖库 └── README.md 

## 环境要求

- Python 3.10+
- macOS / Windows / Linux

## 安装依赖

bash pip install -r requirements.txt 

或单独安装：

bash pip install requests 

## 配置说明

### 设置目标门店

在 stores.txt 中填写需要监控的门店名称：

text 武汉光谷天地店 武汉群光广场店 武汉天地店 

### 设置推送参数

在 config.py 中填写对应配置：

python TELEGRAM_BOT_TOKEN = "xxxxx" TELEGRAM_CHAT_ID = "xxxxx" 

## 运行程序

bash python main.py 

## 工作流程

text 启动程序     ↓ 获取岗位数据     ↓ 解析岗位信息     ↓ 筛选目标门店     ↓ 发现新班次     ↓ 发送通知     ↓ 等待下一轮检查 

## 示例提醒

text 发现新的兼职班次  门店：武汉光谷天地店 日期：2026-05-20 时间：09:00-18:00  请及时报名 

## 常见问题

### No module named 'requests'

安装依赖：

bash pip install requests 

### 请求接口失败

检查：

- 网络是否正常
- 接口地址是否变更
- 请求头是否失效

### 收不到通知

检查：

- Bot Token 是否正确
- Chat ID 是否正确
- 推送服务是否可用

## 后续优化方向

- Web 管理界面
- 多城市门店监控
- 关键词过滤
- 自动报名功能
- 数据统计分析
- Docker 部署
- 云服务器 24 小时运行

## 声明

本项目仅用于学习 Python 自动化、接口请求及消息推送技术，请遵守相关平台规则和法律法规。
