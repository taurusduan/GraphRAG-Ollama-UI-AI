# GraphRAG-Ollama-UI + GraphRAG4OpenWebUI 融合版

视频教程：[https://www.bilibili.com/video/BV1sW42197hT/](https://www.bilibili.com/video/BV1sW42197hT/)  

win整合包：[夸克网盘](https://pan.quark.cn/s/936dcae8aba0#/list/share/56a79e143a8b4877a98a61854e07b229-AI%20Vtuber/a45ffa878e304910a1bfe15c67932807-%E5%85%B6%E4%BB%96%E5%8C%85/c252f86f288540d190ad044ef688ee14-GraphRAG*101Ollama*101UI), [迅雷网盘](https://pan.xunlei.com/s/VNitDF0Y3l-qwTpE0A5Rh4DaA1?path=%2F%E5%88%86%E4%BA%AB%2F%E5%85%B6%E4%BB%96%E8%BD%AF%E4%BB%B6%2FGraphRAG-Ollama-UI) , [123盘](https://www.123pan.com/s/O02bVv-Fr6Wd)  

## 部署&使用

### 0. 环境
python 3.10.10  

### 1. 下载代码
```
git clone https://github.com/Ikaros-521/GraphRAG-Ollama-UI.git
```

### 2. 安装依赖

安装pytorch
```
pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
```

```
pip install -r requirements.txt
```

### 3. 运行

#### gradio webui

ragtest\settings.yaml 完成相应配置（llm，embedding等） 更多参考：[https://microsoft.github.io/graphrag/posts/config/json_yaml/](https://microsoft.github.io/graphrag/posts/config/json_yaml/)  
ragtest\\.env 配置密钥  

运行gradio webui
```
python app.py
```

#### api

api_config.json 完成配置（INPUT_RAG_DIR这个RAG完成后输出的路径下的artifacts，以及llm，embedding等）  
tavily API获取：[https://app.tavily.com/home](https://app.tavily.com/home) (Tavily Search API是针对LLMs和RAG优化的搜索引擎，旨在提供高效、快速和持久的搜索结果。与Serp或Google等其他搜索API不同，Tavily专注于为AI开发人员和自主AI代理优化搜索。我们负责从在线资源中搜索、抓取、过滤和提取最相关信息的所有负担。所有这些都在一个API调用中完成！)   

运行api.py
```
python api.py
```

### 4. 访问

#### webui

打开浏览器，访问 http://127.0.0.1:7860 即可使用。

#### api文档

http://127.0.0.1:8012/docs


## 原始项目

[https://github.com/microsoft/graphrag](https://github.com/microsoft/graphrag)  

[https://github.com/severian42/GraphRAG-Ollama-UI](https://github.com/severian42/GraphRAG-Ollama-UI)  

[https://github.com/win4r/GraphRAG4OpenWebUI](https://github.com/win4r/GraphRAG4OpenWebUI)  

# GraphRAG-Ollama-UI

#  🕸️ GraphRAG Local with Interactive UI

Welcome to **GraphRAG Local with Interactive UI**! This is an adaptation of Microsoft's [GraphRAG](https://github.com/microsoft/graphrag), tailored to support local models and featuring a comprehensive interactive user interface.

## 📄 Research Paper

For more details on the original GraphRAG implementation, please refer to the [GraphRAG paper](https://arxiv.org/pdf/2404.16130).

## 🌟 Features

- **Local Model Support:** Leverage local models for LLM and embeddings, including compatibility with Ollama and OpenAI-compatible APIs.
- **Cost-Effective:** Eliminate dependency on costly cloud-based models by using your own local models.
- **Interactive UI:** User-friendly interface for managing data, running queries, and visualizing results.
- **Real-time Graph Visualization:** Visualize your knowledge graph in 2D or 3D using Plotly.
- **File Management:** Upload, view, edit, and delete input files directly from the UI.
- **Settings Management:** Easily update and manage your GraphRAG settings through the UI.
- **Output Exploration:** Browse and view indexing outputs and artifacts.
- **Logging:** Real-time logging for better debugging and monitoring.
- **Flexible Querying:** Support for global, local, and direct chat queries with customizable parameters.
- **Customizable Visualization:** Adjust graph layout, node sizes, colors, and more to suit your preferences.

![GraphRAG UI](uiv3.png)

## 🗺️ Roadmap

### **Important Note:** GraphRAG Local UI is currently a major work in progress and building a UI around the GraphRAG library has introduced a number of challenges; mainly with the Indexing process. The query is also a work in progress as it tends to go between functional and breaking with the changes to the GraphRAG library. As I strive to make the application more stable with local LLMs, users should expect to encounter some bugs and breaking changes. I appreciate your patience and feedback during this development phase. If you encounter indexing issues while running this Gradio app while I am debugging it, you can typically run it straight in the terminal with the CLI args and have it work out 80-90% of the time.

*While it is currently functional, it has only been primarily tested on a Mac Studio M2.*

My vision for GraphRAG Local UI is to become the ultimate GraphRAG app for local LLMs, incorporating as many cool features and knowledge graph tools as possible. I am continuously working on improvements and new features.

### Recent Updates
- [x] Indexing Works! Fixes to the Indexing process and caching of embeddings.
- [x] LLM agnostic: Use Ollama or set your own base URL and local model for LLM and Embedder
- [x] Custom configurable graph visuals
- [x] Preset Query/Indexing library options to quickly and easily harness all the GraphRAG args
- [x] Enhanced UI with tabbed interface for better organization
- [x] Improved file management system
- [x] Real-time indexing progress and control

### Upcoming Features
- [ ] Dockerfile for easier deployment
- [ ] Launch your own GraphRAG API server for use in external applications
- [ ] Experimental: Mixture of Agents for Indexing/Query of knowledge graph
- [ ] Support for more file formats (CSV, PDF, etc.)
- [ ] Web search/Scraping capabilities
- [ ] Enhanced error handling and user feedback
- [ ] Improved performance and scalability
- [ ] Advanced graph analysis tools
- [ ] Integration with popular knowledge management tools
- [ ] Collaborative features for team-based knowledge graph building

I am committed to making GraphRAG Local UI the most comprehensive and user-friendly tool for working with knowledge graphs and LLMs. Your feedback and suggestions are much needed in shaping the future of this project.

Feel free to open an Issue if you run into an error, and we will try to address it as soon as possible to minimize any downtime you might experience.

## 📦 Installation and Setup

Follow these steps to set up and run GraphRAG Local with Interactive UI:

1. **Create and activate a new conda environment:**
    ```bash
    conda create -n graphrag-local -y
    conda activate graphrag-local
    ```

2. **Install the required packages:**
    ```bash
    pip install -r requirements.txt
    ```

3. **Launch the interactive UI:**
    ```bash
    gradio app.py
    ```

    or

    ```bash
    python app.py
    ```

4. **Access the UI:**
    Open your web browser and navigate to `http://localhost:7860` to access the GraphRAG Local UI.

## 🖥️ Using the GraphRAG Local UI

### Data Management

1. **File Upload:**
   - Navigate to the "Data Management" tab.
   - Use the "File Upload" section to upload .txt files to the input directory.
   - Click the "Upload File" button to add your file to the system.

2. **File Management:**
   - View, edit, and delete uploaded files in the "File Management" section.
   - Use the dropdown to select a file, then view its content in the text area below.
   - Edit the file content directly in the text area and click "Save Changes" to update.
   - Use the "Delete Selected File" button to remove a file from the system.
   - Click "Refresh File List" to update the list of available files.

### Indexing

1. **Configure Indexing:**
   - Go to the "Indexing" tab.
   - Set the root directory (default is "./ragtest").
   - Optionally upload a config file.
   - Adjust other parameters like verbosity, caching, and output formats.

2. **Run Indexing:**
   - Click "Run Indexing" to start the indexing process.
   - Monitor progress in real-time through the output box and progress bar.
   - Use "Stop Indexing" if you need to halt the process.
   - The "Refresh Indexing" button allows you to reset the indexing process if needed.

3. **Custom CLI Arguments:**
   - For advanced users, you can add custom CLI arguments in the provided text area.
   - Refer to the CLI Argument Key Guide for available options.

### Indexing Outputs/Visuals

1. **Explore Indexed Data:**
   - Select an output folder from the dropdown.
   - Browse through the folder contents and view file information and content.
   - Use the "Initialize Selected Folder" button to load the contents of a specific output folder.

2. **Visualize Graph:**
   - Select a GraphML file from the output folder.
   - Click "Visualize Graph" to generate a 2D or 3D visualization of your knowledge graph.
   - Customize the visualization using the "Visualization Settings" accordion:
     - Choose between 3D Spring, 2D Spring, or Circular layouts
     - Adjust node size, edge width, and label size
     - Select node color attributes and color schemes
     - Toggle node labels on/off

### LLM Settings

1. **Configure LLM and Embeddings:**
   - Set API base URLs and keys for both LLM and embeddings.
   - Choose the service type (OpenAI-compatible or Ollama).
   - Select models from the dropdown or refresh the list of available models.

2. **Adjust Parameters:**
   - Set the system message, context window, temperature, and max tokens.
   - Click "Update LLM Settings" to save your changes.

### YAML Settings

- Adjust additional GraphRAG settings in the "YAML Settings" tab as needed.
- Each setting is presented in an accordion for easy access and editing.

### Querying

1. **Choose Query Type:**
   - Select between global, local, or direct chat queries.

2. **Select Preset or Custom Options:**
   - Choose a preset query option or customize your query parameters.
   - Presets include options like "Default Global Search", "Detailed Local Analysis", "Quick Global Summary", etc.
   - For custom queries, you can adjust community level, response type, and add custom CLI arguments.

3. **Enter Your Query:**
   - Type your query in the input box and click "Send Query" or press Shift+Enter.

4. **View Results:**
   - See the chat history and responses in the chat interface.
   - The chat history is preserved between queries for context.

5. **Clear Chat:**
   - Use the "Clear Chat" button to reset the conversation history.

### Graph Visualization

1. **Select Output Folder and GraphML File:**
   - Choose the output folder and GraphML file you want to visualize.

2. **Customize Visualization:**
   - Use the "Visualization Settings" accordion to adjust various aspects of the graph:
     - Layout Type: Choose between 3D Spring, 2D Spring, or Circular layouts.
     - Node Size: Adjust the size of nodes in the graph.
     - Edge Width: Change the thickness of edges connecting nodes.
     - Node Color Attribute: Color nodes based on their degree or randomly.
     - Color Scheme: Select from various color palettes for node coloring.
     - Show Node Labels: Toggle the visibility of node labels.
     - Label Size: Adjust the size of node labels.

3. **Generate Visualization:**
   - Click the "Visualize Graph" button to create the graph based on your settings.

4. **Interact with the Graph:**
   - Once generated, you can interact with the 3D graph by rotating, zooming, and panning.
   - Hover over nodes to see additional information.

## 📊 Visualization

The UI includes a 2D/3D graph visualization feature:

1. Run indexing on your data.
2. Go to the "Indexing Outputs/Visuals" tab.
3. Select the latest output folder and navigate to the GraphML file.
4. Click the "Visualize Graph" button.
5. Customize the visualization using the settings provided in the "Visualization Settings" accordion.

## 🚀 Advanced Usage

- **Custom CLI Arguments:** In both the indexing and query interfaces, advanced users can add custom CLI arguments for more granular control over the processes.
- **LLM and Embeddings Configuration:** You can configure different models and APIs for LLM and embeddings separately, allowing for flexible setups.

## 📚 Citations

- Original GraphRAG repository by Microsoft: [GraphRAG](https://github.com/microsoft/graphrag)

---

## Troubleshooting

- `No module named 'distutils'`: If you can't run `gradio app.py`, try running `pip install --upgrade gradio` and then exit out and start a new terminal. It should then load and launch properly as a Gradio app.

- On Windows, if you run into an encoding/UTF error, you can change it to the correct format in the YAML Settings menu.

- Indexing Errors: These are still tough to debug and track down as it is dependent on your specific pipeline of LLMs and embedders. Right now it seems to call /v1/embeddings no matter what in the Index workflow, but I think I found a workaround that allows Ollama and other local options. I'll keep trying to reinforce the Indexing process to make it more stable and robust.

For any issues or feature requests, please open an issue on the GitHub repository. Happy knowledge graphing!


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
