# 数据分析MCP服务

这是一个基于MCP(Model Control Panel)框架的数据分析服务，提供数据分析和公司信息查询功能。

## 功能

- 公司算账经营数据分析
- 公司信息查询

## 环境要求

- Python 3.8+
- UV包管理器

## 安装
1. 克隆仓库:

```bash
git clone https://github.com/yourusername/data_analysis_mcp.git
cd data_analysis_mcp
```

2. 使用UV创建虚拟环境并安装依赖:

```bash
uv venv
source .venv/bin/activate  # Linux/Mac
# 或
.venv\Scripts\activate  # Windows

uv pip install -e .
```

## 配置

1. 复制环境变量示例文件并修改:

```bash
cp .env.example .env
```

2. 编辑`.env`文件，设置你的环境变量:

```
OPENAI_API_KEY=your_api_key_here
```

## 运行

```bash
python run.py
```

## 打包

使用UV打包应用:

```bash
uv pip build
```

这将在`dist`目录下生成wheel包。

## 部署

安装生成的wheel包:

```bash
uv pip install dist/data_analysis_mcp-0.1.0-py3-none-any.whl
```

## 使用Docker部署

1. 构建Docker镜像:

```bash
docker build -t data-analysis-mcp:latest .
```

2. 运行容器:

```bash
docker run -p 8000:8000 -e OPENAI_API_KEY=your_api_key_here data-analysis-mcp:latest
```

## 接口文档

### 分析数据

```python
analyze_data(query: str) -> dict
```

参数:
- query: 用户的查询内容，例如"请分析1-6月份边际贡献最高的5家分公司"

### 查询公司信息

```python
query_company_info(query: str) -> str
```

参数:
- query: 用户的查询内容，例如"欧冶金诚服务有限公司"

## 许可证

[MIT](LICENSE) 