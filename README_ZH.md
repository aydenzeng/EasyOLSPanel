# 📘 EasyOLSPanel - 一个简单轻量的 OpenLiteSpeed 管理面板

## 项目简介
**EasyOLSPanel** 是一个专为 **OpenLiteSpeed** 服务器打造的轻量级 Web 管理面板。  
使用 **Python (FastAPI)** 开发，旨在提供一个简洁、现代、易用的界面，帮助服务器管理员快速管理网站、SSL证书、服务器状态和配置，无需依赖笨重的第三方面板。

## 项目特性
- 🖥️ 管理 OpenLiteSpeed 虚拟主机（新增、编辑、删除）
- 🔒 SSL证书管理（计划集成 Let's Encrypt）
- 🚀 启动、停止、重启 OpenLiteSpeed 服务
- 📄 查看和编辑服务器配置文件
- 📊 监控服务器资源（CPU、内存、磁盘）
- 📑 查看服务器日志（访问日志和错误日志）
- 🛡️ 轻量级认证与安全保护
- ✨ 高性能、易扩展设计

## 技术栈
- 后端框架：**Python 3.9+**、**FastAPI**
- 系统交互：**subprocess**（调用系统命令），直接处理配置文件
- 数据存储（可选）：**SQLite** 或本地文件存储

## 项目目标
- 极简部署与使用
- 面向开发者，便于二次开发
- 最低的服务器资源消耗
- 针对 **OpenLiteSpeed** 深度优化

## 许可证
MIT License


# 📦 安装与开发指南

## 安装部署

1. **系统要求**
   - 系统：CentOS 7/8、Ubuntu 20.04+、Debian 10+
   - 必须安装 OpenLiteSpeed
   - Python 版本：3.9 或更高
   - pip、virtualenv 可用

2. **快速安装步骤**

```bash
# 安装必要依赖
sudo apt update && sudo apt install -y python3 python3-pip python3-venv

# 克隆 EasyOLSPanel 项目
git clone https://github.com/你的用户名/EasyOLSPanel.git
cd EasyOLSPanel

# 创建虚拟环境并激活
python3 -m venv venv
source venv/bin/activate

# 安装依赖
pip install -r requirements.txt

# 启动开发服务器
uvicorn app.main:app --host 0.0.0.0 --port 8000 --reload

注意：生产环境推荐使用 gunicorn + uvicorn workers 方式运行，并配置 Nginx 反向代理。

