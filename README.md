# MCP 项目

这是一个基于 Model Context Protocol (MCP) 的 AI 助手客户端项目。

## 环境要求

- Python 3.12+
- macOS/Linux/Windows

## 快速开始

### 1. 克隆项目

```bash
git clone <your-repo-url>
cd mcp-project
```

### 2. 设置虚拟环境

```bash
# 创建虚拟环境
python3 -m venv venv

# 激活虚拟环境
# macOS/Linux:
source venv/bin/activate
# Windows:
# venv\Scripts\activate
```

### 3. 安装依赖

```bash
pip install openai python-dotenv mcp
```

### 4. 配置环境变量

创建 `.env` 文件并添加以下配置：

```env
DASHSCOPE_API_KEY=your_api_key_here
BASE_URL=https://dashscope.aliyuncs.com/compatible-mode/v1
MODEL=qwen-plus
```

### 5. 运行项目

```bash
# 方法1: 使用启动脚本
./run_client.sh

# 方法2: 手动运行
source venv/bin/activate
python3 client.py
```

## IDE 配置

### VS Code

项目已包含 `.vscode/settings.json` 配置，会自动使用虚拟环境中的 Python 解释器。

如果仍然遇到导入错误：

1. 按 `Cmd+Shift+P` (macOS) 或 `Ctrl+Shift+P` (Windows/Linux)
2. 输入 "Python: Select Interpreter"
3. 选择 `./venv/bin/python3`

### PyCharm

1. 打开项目设置 (File > Settings)
2. 转到 Project > Python Interpreter
3. 选择 "Add Interpreter" > "Existing Environment"
4. 选择 `./venv/bin/python3`

## 项目结构

```
mcp-project/
├── client.py              # MCP 客户端主程序
├── server.py              # MCP 服务器脚本
├── main.py                # 主程序入口
├── pyproject.toml         # 项目配置
├── requirements.txt       # 依赖列表
├── .env                   # 环境变量配置
├── .gitignore            # Git 忽略文件
├── run_client.sh         # 启动脚本
├── test_imports.py       # 导入测试脚本
├── venv/                 # 虚拟环境目录
├── llm_outputs/          # LLM 输出文件
├── sentiment_reports/    # 情感分析报告
└── google_news/          # 新闻数据
```

## 故障排除

### 导入错误

如果遇到 "无法解析导入" 错误：

1. **确保虚拟环境已激活**：

   ```bash
   source venv/bin/activate
   ```

2. **检查包是否已安装**：

   ```bash
   pip list | grep -E "(openai|mcp|dotenv)"
   ```

3. **重新安装依赖**：

   ```bash
   pip install --force-reinstall openai python-dotenv mcp
   ```

4. **运行测试脚本**：
   ```bash
   python3 test_imports.py
   ```

### IDE 相关问题

- 确保 IDE 使用正确的 Python 解释器
- 重启 IDE 以应用新的解释器设置
- 清除 IDE 缓存

## 使用说明

1. 启动客户端后，输入自然语言查询
2. 系统会自动选择合适的工具处理您的请求
3. 结果会保存到相应的输出目录
4. 输入 'quit' 退出程序

## 许可证

MIT License
