# MaxKB-AI-Agent 项目复刻与实战演练

该项目基于开源仓库 [1Panel-dev/MaxKB](https://github.com/1Panel-dev/MaxKB) 实现，本人完成了本地部署，并深入理解了其核心架构与业务逻辑。**本项目作为个人学习 AI Agent 结构与 RAG 架构的实战演练用途，非原创商用项目。**

---

## 💡 项目介绍

MaxKB 是一个支持知识库问答的企业级 AI 助手平台。它通过 RAG（Retrieval-Augmented Generation）架构，引入向量搜索与知识库管理，构建出灵活可扩展的私有问答系统。

我在本项目中完成了：

- ✅ 在本地环境完整部署后端服务与前端界面
- ✅ 熟悉向量检索流程、Embedding 与文档管理
- ✅ 理解了 Prompt 设计在不同场景下的作用
- ✅ 使用 Together.ai 模仿OpenAI接口，接入问答模块
- ✅ 使用 Docker 实现异步任务队列

---

## 🧠 项目核心概念

| 概念              | 理解与应用 |
|------------------|------------|
| **RAG 架构**       | Retrieval + Generation：通过向量检索增强模型上下文输入，提高准确性 |
| **向量数据库**     | Faiss / Weaviate / Qdrant 等；本项目默认使用 FAISS 本地构建 |
| **Embedding 模型** | 支持 OpenAI、BGE、text2vec 多种中文语义编码 |
| **Prompt 工程**    | 针对不同知识库和任务设计提示词模板，如客服问答、规则解析等 |
| **多 Agent 架构**  | 可配置不同“助手”角色，对应不同知识库与使用场景 |
| **Celery 任务队列**| 异步执行文档处理、Embedding 入库等操作，提高系统响应能力 |

---

## 🔍 示例界面截图

### 📘 登录与主界面

![image](https://github.com/user-attachments/assets/3af7bbe4-74e7-4a38-8a42-ad4446e08486)


### 📚 知识库配置界面

![image](https://github.com/user-attachments/assets/b8701ed2-aa9d-4ec6-bc10-7ee190032f70)


### 🤖 AI Agent 配置与问答测试

![image](https://github.com/user-attachments/assets/8c2c3d8c-c56c-4716-949a-fa7e5905bf97)


> 提示：截图来源于本地部署后的实际运行界面，所有页面可在 `localhost:3000` 访问。

---

## 🛠️ 技术栈

- `Python` + `FastAPI` + `Celery`
- `Vue3` + `Vite` + `ElementPlus`
- 向量数据库：`FAISS`
- LLM 接入：`OpenAI API`
- 容器部署：`Docker` + `docker-compose`
- 前后端通信：RESTful API + WebSocket
- 本地启动指令：

```bash
cd ui
pnpm install
pnpm run dev
