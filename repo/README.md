# 🏯 寺庙修缮募捐功德纪要系统

基于AI的寺庙修缮募捐会议全栈管理系统，集成语音转写、说话人标记、智能摘要生成等功能。

## ✨ 功能特性

### 🎙️ 智能语音处理
- **Whisper AI 转写**: 自动将住持与工匠的对话转为文字
- **pyannote 说话人标记**: 自动区分寺方与设计方发言
- **AI 角色识别**: 智能识别说话人身份（住持、监院、工匠、设计师等）

### 📜 智能文案生成
- **会议纪要生成**: 自动提炼会议要点，形成专业纪要
- **募捐文案撰写**: 根据殿堂情况生成感人至深的募捐倡议
- **功德回向清单**: 自动生成不同布施金额对应的功德回向

### 🌐 古风界面展示
- 典雅的古风UI设计
- 殿堂病害详情可视化
- 修缮方案图文展示
- 响应式布局，支持移动端

### 📧 信众通知
- Markdown格式功德纪要
- 一键发送邮件给信众
- 精美的HTML邮件模板

## 🏗️ 技术栈

### 后端
- **FastAPI**: 高性能Python Web框架
- **SQLAlchemy**: ORM数据库操作
- **OpenAI API**: Whisper转写 + GPT摘要
- **pyannote.audio**: 说话人分离
- **SQLite**: 轻量级数据库

### 前端
- **Vue 3**: 渐进式JavaScript框架
- **Element Plus**: UI组件库
- **Vite**: 下一代前端构建工具
- **Noto Serif SC / Ma Shan Zheng**: 古风字体

## 📦 项目结构

```
auto115/
├── backend/                    # 后端服务
│   ├── api/                    # API路由
│   │   ├── temples.py          # 寺庙管理
│   │   ├── meetings.py         # 会议管理
│   │   └── donors.py           # 功德主管理
│   ├── services/               # 业务服务
│   │   ├── ai_service.py       # AI服务（转写、摘要）
│   │   └── document_service.py # 文档与邮件服务
│   ├── config.py               # 配置文件
│   ├── database.py             # 数据库连接
│   ├── models.py               # 数据模型
│   ├── schemas.py              # Pydantic模式
│   └── main.py                 # 应用入口
├── frontend/                   # 前端应用
│   ├── src/
│   │   ├── views/              # 页面组件
│   │   │   ├── Home.vue        # 首页
│   │   │   ├── Temples.vue     # 寺庙列表
│   │   │   ├── TempleDetail.vue# 寺庙详情
│   │   │   ├── HallDetail.vue  # 殿堂详情
│   │   │   ├── Meetings.vue    # 会议列表
│   │   │   ├── MeetingDetail.vue # 会议详情
│   │   │   └── Donors.vue      # 功德主列表
│   │   ├── api/                # API调用
│   │   ├── router/             # 路由配置
│   │   └── assets/styles/      # 全局样式
│   └── package.json
├── requirements.txt            # Python依赖
├── .env.example                # 环境变量示例
├── start-backend.bat           # 后端启动脚本
└── start-frontend.bat          # 前端启动脚本
```

## 🚀 快速开始

### 环境要求
- Python 3.10+
- Node.js 18+
- FFmpeg（音频处理）

### 1. 配置环境变量

复制 `.env.example` 为 `.env` 并填写配置：

```env
OPENAI_API_KEY=your_openai_api_key_here
OPENAI_BASE_URL=https://api.openai.com/v1
PYANNOTE_AUTH_TOKEN=your_huggingface_token_here
SMTP_HOST=smtp.example.com
SMTP_PORT=465
SMTP_USER=your_email@example.com
SMTP_PASSWORD=your_email_password
```

### 2. 启动后端服务

```bash
# Windows
start-backend.bat

# 或手动执行
cd backend
python -m venv venv
venv\Scripts\activate
pip install -r ../requirements.txt
uvicorn main:app --reload --port 8000
```

### 3. 启动前端服务

```bash
# Windows
start-frontend.bat

# 或手动执行
cd frontend
npm install
npm run dev
```

### 4. 访问应用

- 前端地址: http://localhost:5173
- 后端API: http://localhost:8000
- API文档: http://localhost:8000/docs

## 📖 使用流程

### 1. 登记寺庙与殿堂
1. 在"寺庙殿堂"页面登记寺庙信息
2. 添加殿堂信息，包括名称、描述
3. 录入殿堂病害详情（木构腐朽、彩绘剥落等）
4. 制定修缮方案（木构替换、彩绘重绘等）

### 2. 创建会议并上传音频
1. 在殿堂详情页创建修缮会议
2. 上传会议录音文件
3. 点击"AI处理会议"开始分析

### 3. 查看处理结果
系统自动完成以下处理：
- 🎙️ Whisper语音转写
- 👥 pyannote说话人标记
- ✨ AI识别说话人角色
- 📋 生成会议纪要
- 💰 生成募捐文案
- 🙏 生成功德回向清单

### 4. 邮寄给信众
1. 查看生成的Markdown纪要
2. 添加信众邮箱
3. 一键发送功德纪要邮件

## 🧘 功德回向

```
愿以此功德，普及于一切
我等与众生，皆共成佛道

若人发心造塔寺，其人所得功德利
假使劫石可消磨，此福无边不可尽
```

---

*南无阿弥陀佛* 🙏
