# Flask 个人技术博客

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)

[![Redis](https://img.shields.io/badge/Redis-7.0-red.svg)](https://redis.io)

[![Flask](https://img.shields.io/badge/Flask-3.0-000.svg?style=flat&logo=flask)](https://flask.palletsprojects.com)

[![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-2.0-d71f00.svg?style=flat&logo=sqlalchemy)](https://www.sqlalchemy.org)

[![Prism.js](https://img.shields.io/badge/Prism.js-1.29-258DCF.svg?style=flat&logo=prism)](https://prismjs.com)

## 📋 项目概述

- **简述**：搭建了一个个人博客类似一个随身笔记本，遇到不懂的疑难杂症或者值得记录的经验就放上去。

- **线上地址**:http://43.139.56.65:8000/

- **视频演示**：
  
  - **个人技术博客**
  
    [下载 Project4.mp4](https://github.com/s19m3nug-boop/Project_Description/raw/main/videos/Project4.mp4)
  
    <details>
        <summary>📺 核心功能演示（点击展开，加载慢请稍等/下载）</summary>
        <video src="https://raw.githubusercontent.com/s19m3nug-boop/Project_Description/main/videos/Project4.mp4" width="800" controls="controls" preload="metadata">
       你的浏览器不支持视频播放，请点击上方链接下载查看 </video>
    </details>
  
  ​          

## 📋 核心定位

独立开发的轻量化个人技术博客系统，聚焦【后端性能优化】与【开发者前端体验优化】，兼顾功能完整性与易用性，已通过 Gunicorn+Nginx 部署上线，支持长期稳定运行。

## 🚀 技术栈

- **后端框架**：Flask 2.3 + SQLAlchemy 2.0
- **数据存储**：SQLite/MySQL + Redis 7.0
- **前端技术**：Prism.js 1.29、Clipboard.js 2.0、CSS 变量、Markdown2
- **部署运维**：Gunicorn 21.0 + Nginx 1.24
- **性能优化**：Redis 缓存、限流、阅读量防刷
- **内容渲染**：Markdown2 转 HTML，适配 Prism.js 代码高亮格式

## 🎯 核心功能

### 后端核心功能

- **内容管理**：实现文章发布 / 编辑 / 删除、分类管理、关键词搜索等完整业务流程，基于 SQLAlchemy 完成数据库 CRUD 操作
- **阅读量防刷**：基于 Redis + IP+UA 哈希校验，规避恶意刷取文章阅读量的行为，保证数据真实性
- **热门文章排行**：利用 Redis ZSet（有序集合）实现热门文章实时排序，按阅读量动态更新榜单
- **接口限流**：通过 Redis 实现接口访问频次控制，防止恶意请求攻击，提升系统稳定性
- **缓存优化**：Redis 缓存热门文章与分类数据，减少数据库查询压力，大幅提升接口响应速度

### 前端开发者体验优化

- **代码高亮**：集成 Prism.js 实现 Python/Shell/JSON 等多语言语法高亮，支持代码行号显示，完美适配暗黑 / 浅色双主题
- **一键复制**：基于 Clipboard.js 实现代码块一键复制功能，附带成功 / 失败文字反馈，无需手动选中代码，提升使用效率
- **暗黑模式**：通过 CSS 变量统一管理主题样式，支持浅色 / 暗黑模式一键切换，借助 localStorage 持久化主题配置，刷新页面保留用户设置
- **响应式布局**：优化文章排版与页面布局，兼容移动端与桌面端，保证多设备下的良好阅读体验

### 部署与工程化保障

- **生产部署**：采用 Gunicorn（WSGI 服务器）+ Nginx（反向代理）架构，实现静态资源分离与请求转发，支持高并发访问
- **仓库优化**：通过 .gitignore 忽略虚拟环境、Python 编译文件、本地数据库文件，保证仓库轻量化
- **依赖管理**：生成 requirements.txt 依赖清单，方便快速部署、环境迁移与他人二次开发