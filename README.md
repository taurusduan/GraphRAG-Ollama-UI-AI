# GraphRAG-Ollama-UI + GraphRAG4OpenWebUI 融合版

## 部署&使用

### 0. 环境
python 3.10.10  

### 1. 下载代码
```
git clone https://github.com/Ikaros-521/GraphRAG-Ollama-UI.git
```

### 2. 安装依赖
```
pip install -r requirements.txt
```

### 3. 运行

#### gradio webui

ragtest\settings.yaml 完成相应配置（llm，embedding等） 更多参考：[https://microsoft.github.io/graphrag/posts/config/json_yaml/](https://microsoft.github.io/graphrag/posts/config/json_yaml/)
ragtest\.env 配置密钥

运行gradio webui
```
python app.py
```

#### api

api_config.json 完成配置（INPUT_RAG_DIR这个RAG完成后输出的路径下的artifacts，以及llm，embedding等）

运行api.py
```
python api.py
```

### 4. 访问

#### webui
打开浏览器，访问 http://127.0.0.1:7860 即可使用。

#### api文档

http://127.0.0.1:8012/docs


# GraphRAG-Ollama-UI

#  🕸️ GraphRAG Local with Ollama and Gradio UI

Welcome to **GraphRAG Local with Ollama and Interactive UI**! This is an adaptation of Microsoft's [GraphRAG](https://github.com/microsoft/graphrag), tailored to support local models using Ollama and featuring a new interactive user interface.

*NOTE: The app gained traction much quicker than I anticipated so I am working to get any found bugs fixed and suggested improvements integrated. Right now it is fully functional, tested only on my Mac Studio M2 though. I am trying to be fluid with the adjustments and so will try to update at least every few hours when possible. 

Changes being made right now:

- LLM agnostic: Use Ollama or set your own base URL and local model for LLM and Embedder
- Launch your own GraphRAG API server so you can use the functions in your own external app
- Dockerfile for easier deployment
- Experimental: Mixture of Agents for Indexing/Query of knowledge graph
- More graph visual options

Feel free to open an Issue if you run into an error and I will try to address it ASAP so you don't run into any downtime*

## 📄 Research Paper

For more details on the original GraphRAG implementation, please refer to the [GraphRAG paper](https://arxiv.org/pdf/2404.16130).

## 🌟 Features

- **Local Model Support:** Leverage local models with Ollama for LLM and embeddings.
- **Cost-Effective:** Eliminate dependency on costly OpenAI models.
- **Interactive UI:** User-friendly interface for managing data, running queries, and visualizing results.
- **Real-time Graph Visualization:** Visualize your knowledge graph in 3D using Plotly.
- **File Management:** Upload, view, edit, and delete input files directly from the UI.
- **Settings Management:** Easily update and manage your GraphRAG settings through the UI.
- **Output Exploration:** Browse and view indexing outputs and artifacts.
- **Logging:** Real-time logging for better debugging and monitoring.

![GraphRAG UI](ui.png)

## 📦 Installation and Setup

Follow these steps to set up and run GraphRAG Local with Ollama and Interactive UI:

1. **Create and activate a new conda environment:**
    ```bash
    conda create -n graphrag-ollama -y
    conda activate graphrag-ollama
    ```

2. **Install Ollama:**
    Visit [Ollama's website](https://ollama.com/) for installation instructions.

4. **Install the required packages:**
    ```bash
    pip install -r requirements.txt
    ```

4. **Launch the interactive UI:**
    ```bash
    gradio app.py
    ```
    or

    ```bash
    python app.py
    ```

6. **Using the UI:**
    - Once the UI is launched, you can perform all necessary operations through the interface.
    - This includes initializing the project, managing settings, uploading files, running indexing, and executing queries.
    - The UI provides a user-friendly way to interact with GraphRAG without needing to run command-line operations.

Note: The UI now handles all the operations that were previously done through command-line instructions, making the process more streamlined and user-friendly.

## 🛠️ Customization

Users can experiment by changing the models in the `settings.yaml` file. The LLM model expects language models like llama3, mistral, phi3, etc., and the embedding model section expects embedding models like mxbai-embed-large, nomic-embed-text, etc., which are provided by Ollama. You can find the complete list of models provided by Ollama [here](https://ollama.com/library).

## 📊 Visualization

The UI now includes a 3D graph visualization feature. To use it:

1. Run indexing on your data
2. Go to the "Indexing Outputs" tab
3. Select the latest output folder and navigate to the GraphML file
4. Click the "Visualize Graph" button

## 📚 Citations

- Original GraphRAG repository by Microsoft: [GraphRAG](https://github.com/microsoft/graphrag)
- Ollama: [Ollama](https://ollama.com/)

---

# GraphRAG4OpenWebUI

### 🔥🔥🔥如有问题请联系我的微信 stoeng
### 🔥🔥🔥项目对应的视频演示请看 https://youtu.be/z4Si6O5NQ4c

# GraphRAG4OpenWebUI
<div align="center">
  <p><strong>将微软的 GraphRAG 技术集成到 Open WebUI 中，实现高级信息检索</strong></p>
  <a href="README.md">English</a> | 简体中文
</div>

GraphRAG4OpenWebUI 是一个专为 Open WebUI 设计的 API 接口，旨在集成微软研究院的 GraphRAG（基于图的检索增强生成）技术。该项目提供了一个强大的信息检索系统，支持多种搜索模型，特别适合在开放式 Web 用户界面中使用。

## 项目概述

本项目的主要目标是为 Open WebUI 提供一个便捷的接口，以利用 GraphRAG 的强大功能。它集成了三种主要的检索方法，并提供了一个综合搜索选项，使用户能够获得全面而精确的搜索结果。

### 主要检索功能

1. **本地搜索（Local Search）**
   - 利用 GraphRAG 技术在本地知识库中进行高效检索
   - 适用于快速访问预先定义的结构化信息
   - 利用图结构提高检索的准确性和相关性

2. **全局搜索（Global Search）**
   - 在更广泛的范围内搜索信息，超越本地知识库的限制
   - 适用于需要更全面信息的查询
   - 利用 GraphRAG 的全局上下文理解能力，提供更丰富的搜索结果

3. **Tavily 搜索**
   - 集成外部 Tavily 搜索 API
   - 提供额外的互联网搜索能力，扩展信息源
   - 适用于需要最新或广泛网络信息的查询

4. **全模型搜索（Full Model Search）**
   - 综合上述三种搜索方法
   - 提供最全面的搜索结果，满足复杂的信息需求
   - 自动整合和排序来自不同来源的信息

### 本地LLM和Embedding模型支持

GraphRAG4OpenWebUI 现在支持使用本地的语言模型（LLM）和嵌入模型，增加了项目的灵活性和隐私性。特别地，我们支持以下本地模型：

1. **Ollama**
   - 支持使用 Ollama 运行的各种开源 LLM，如 Llama 2、Mistral 等
   - 可以通过设置 `API_BASE` 环境变量来指向 Ollama 的 API 端点

2. **LM Studio**
   - 兼容 LM Studio 运行的模型
   - 通过配置 `API_BASE` 环境变量连接到 LM Studio 的服务

3. **本地 Embedding 模型**
   - 支持使用本地运行的嵌入模型，如 SentenceTransformers
   - 通过设置 `GRAPHRAG_EMBEDDING_MODEL` 环境变量来指定使用的嵌入模型

这些本地模型的支持使得 GraphRAG4OpenWebUI 能够在不依赖外部API的情况下运行，提高了数据隐私和降低了使用成本。

## 安装
确保您的系统中已安装 Python 3.8 或更高版本。然后，按照以下步骤安装：
1. 克隆仓库：
   ```bash
   git clone https://github.com/your-username/GraphRAG4OpenWebUI.git
   cd GraphRAG4OpenWebUI
   ```
   
2. 创建并激活虚拟环境：
   ```bash
   python -m venv venv
   source venv/bin/activate  # 在 Windows 上使用 venv\Scripts\activate
   ```
   
3. 安装依赖：
   ```bash
   pip install -r requirements.txt
   ```
   注意：graphrag 包可能需要从特定的源安装。如果上述命令无法安装 graphrag，请参考微软研究院的具体说明或联系维护者获取正确的安装方法。

## 配置

在运行 API 之前，需要设置以下环境变量。您可以通过创建 `.env` 文件或直接在终端中导出这些变量：
那么我已经在根目录创建了一个.env文件，直接改这个即可

```bash
export TAVILY_API_KEY="your_tavily_api_key"

export INPUT_DIR="/path/to/your/input/directory"

# 设置llm API密钥
export GRAPHRAG_API_KEY="your_actual_api_key_here"

# 设置嵌入API密钥（如果与GRAPHRAG_API_KEY不同）
export GRAPHRAG_API_KEY_EMBEDDING="your_embedding_api_key_here"

# 设置LLM模型（默认为"gemma2"）
export GRAPHRAG_LLM_MODEL="gemma2"

# 设置API基础URL（默认为本地服务器）
export API_BASE="http://localhost:11434/v1"

# 设置嵌入API基础URL（默认为OpenAI的API）
export API_BASE_EMBEDDING="https://api.openai.com/v1"

# 设置嵌入模型（默认为"text-embedding-3-small"）
export GRAPHRAG_EMBEDDING_MODEL="text-embedding-3-small"
```

请确保将上述命令中的占位符替换为实际的 API 密钥和路径。

## 使用方法

0. 生成索引（指定文件夹需要有相关的配置）：
   ```
   python -m graphrag.index --root ./ragtest
   ```

1. 启动服务器：
   ```
   python main-cn.py
   ```
   服务器将在 `http://localhost:8012` 上运行。

2. API 端点：
   - `/v1/chat/completions`: POST 请求，用于执行搜索
   - `/v1/models`: GET 请求，获取可用模型列表

3. 在 Open WebUI 中集成：
   在 Open WebUI 的配置中，将 API 端点设置为 `http://localhost:8012/v1/chat/completions`。这将允许 Open WebUI 使用 GraphRAG4OpenWebUI 的搜索功能。

4. 发送搜索请求示例：
   ```python
   import requests
   import json

   url = "http://localhost:8012/v1/chat/completions"
   headers = {"Content-Type": "application/json"}
   data = {
       "model": "full-model:latest",
       "messages": [{"role": "user", "content": "您的搜索查询"}],
       "temperature": 0.7
   }

   response = requests.post(url, headers=headers, data=json.dumps(data))
   print(response.json())
   ```

## 可用模型

- `graphrag-local-search:latest`: 本地搜索
- `graphrag-global-search:latest`: 全局搜索
- `tavily-search:latest`: Tavily 搜索
- `full-model:latest`: 综合搜索（包含上述所有搜索方法）

## 注意事项

- 确保在 `INPUT_DIR` 目录中有正确的输入文件（如 Parquet 文件）。
- API 使用异步编程，确保您的环境支持异步操作。
- 对于大规模部署，建议使用生产级的 ASGI 服务器。
- 本项目专为 Open WebUI 设计，可以轻松集成到各种基于 Web 的应用中。

## 贡献

我们欢迎您提交 Pull Requests 来改进这个项目。对于重大变更，请先开 issue 讨论您想要改变的内容。

## 许可证

[Apache-2.0 许可证](LICENSE)
