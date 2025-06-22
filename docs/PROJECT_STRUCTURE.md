# 项目结构说明

本文档详细说明了Qwen3 Embedding & Reranker检索系统的项目结构。

## 📁 目录结构

```
qwen3_embedding/
├── src/                           # 源代码目录
│   ├── core/                      # 核心功能模块
│   │   ├── test_qwen3_embedding.py    # Embedding模型测试
│   │   ├── test_qwen3_reranker.py     # Reranker模型测试
│   │   ├── hybrid_retrieval.py        # 混合检索系统
│   │   ├── hybrid_retrieval_db.py     # 带数据库的混合检索
│   │   ├── semantic_search.py         # 语义搜索示例
│   │   ├── search_name.py             # 姓名精确搜索
│   │   └── pdf_retrieval.py           # PDF检索工具
│   ├── api/                       # API服务模块
│   │   ├── ray_qwen3.py              # Ray Serve API服务
│   │   └── embeeding4openai.py       # OpenAI兼容接口
│   ├── tools/                     # 工具模块
│   │   └── vector_db_manager.py      # 向量数据库管理工具
│   └── utils/                     # 工具函数模块（预留）
├── web/                          # Web界面模块
│   └── vector_db_viewer.py          # 向量数据库可视化工具
├── scripts/                      # 脚本文件
│   ├── download_models.ps1          # 模型下载脚本（PowerShell）
│   ├── download_models.bat          # 模型下载脚本（Windows CMD）
│   ├── download_models.sh           # 模型下载脚本（Linux/Mac）
│   ├── start_viewer.bat             # 启动可视化工具（Windows）
│   └── start_viewer.ps1             # 启动可视化工具（PowerShell）
├── docs/                         # 文档目录
│   ├── README.md                    # 详细说明文档
│   ├── PROJECT_STRUCTURE.md         # 项目结构说明（本文件）
│   ├── ray_config_guide.md          # Ray配置指南
│   ├── 向量数据库可视化软件使用说明.md  # 可视化工具使用说明
│   └── database_report.html         # 数据库报告
├── examples/                      # 示例文件
│   └── client.ipynb                # Jupyter客户端示例
├── tests/                         # 测试文件
│   └── test_ray_api.py             # API测试
├── models/                        # 模型文件目录（不包含在Git中）
├── vector_db/                     # 向量数据库目录
├── requirements.txt               # 项目依赖
└── .gitignore                     # Git忽略文件
```

## 📂 目录说明

### `src/` - 源代码目录
包含所有Python源代码，按功能模块分类：

#### `src/core/` - 核心功能模块
- **test_qwen3_embedding.py**: Qwen3 Embedding模型的测试和基础功能
- **test_qwen3_reranker.py**: Qwen3 Reranker模型的测试和基础功能
- **hybrid_retrieval.py**: 混合检索系统（内存版本）
- **hybrid_retrieval_db.py**: 混合检索系统（数据库版本）
- **semantic_search.py**: 语义搜索示例和演示
- **search_name.py**: 姓名精确搜索功能
- **pdf_retrieval.py**: PDF文档检索工具

#### `src/api/` - API服务模块
- **ray_qwen3.py**: Ray Serve API服务，提供RESTful接口
- **embeeding4openai.py**: OpenAI兼容的Embedding接口

#### `src/tools/` - 工具模块
- **vector_db_manager.py**: 向量数据库管理工具，支持批量导入、统计、导出等功能

#### `src/utils/` - 工具函数模块
- 预留目录，用于存放通用工具函数

### `web/` - Web界面模块
- **vector_db_viewer.py**: 基于Streamlit的向量数据库可视化工具

### `scripts/` - 脚本文件
包含各种平台的启动和安装脚本：

#### 模型下载脚本
- **download_models.ps1**: PowerShell版本（Windows）
- **download_models.bat**: 批处理版本（Windows CMD）
- **download_models.sh**: Shell脚本版本（Linux/Mac）

#### 应用启动脚本
- **start_viewer.bat**: 启动可视化工具（Windows）
- **start_viewer.ps1**: 启动可视化工具（PowerShell）

### `docs/` - 文档目录
- **README.md**: 项目主要说明文档
- **PROJECT_STRUCTURE.md**: 项目结构说明（本文件）
- **ray_config_guide.md**: Ray Serve配置和使用指南
- **向量数据库可视化软件使用说明.md**: 可视化工具详细使用说明
- **database_report.html**: 数据库统计报告

### `examples/` - 示例文件
- **client.ipynb**: Jupyter Notebook客户端示例，展示如何使用API

### `tests/` - 测试文件
- **test_ray_api.py**: Ray API服务的测试脚本

### 其他目录
- **models/**: 存放下载的模型文件（不包含在Git中）
- **vector_db/**: Chroma向量数据库文件
- **.venv/**: Python虚拟环境（不包含在Git中）

## 🔄 文件移动历史

项目文件结构经过重新整理，主要变化：

1. **核心功能模块** → `src/core/`
2. **API服务模块** → `src/api/`
3. **工具模块** → `src/tools/`
4. **Web界面** → `web/`
5. **脚本文件** → `scripts/`
6. **文档文件** → `docs/`
7. **示例文件** → `examples/`
8. **测试文件** → `tests/`

## 📝 使用说明

### 运行核心功能
```bash
# 测试Embedding模型
python src/core/test_qwen3_embedding.py

# 运行混合检索
python src/core/hybrid_retrieval_db.py
```

### 启动Web界面
```bash
# 直接启动
python web/vector_db_viewer.py

# 使用脚本启动
.\scripts\start_viewer.bat
```

### 启动API服务
```bash
python src/api/ray_qwen3.py
```

### 管理向量数据库
```bash
python src/tools/vector_db_manager.py
```

## 🎯 设计原则

1. **模块化**: 按功能将代码分为不同模块
2. **可维护性**: 清晰的目录结构便于维护和扩展
3. **可扩展性**: 预留目录和接口便于添加新功能
4. **跨平台**: 提供多平台的脚本支持
5. **文档化**: 完善的文档说明

## 🔮 未来扩展

- `src/utils/`: 可添加通用工具函数
- `src/models/`: 可添加自定义模型
- `src/config/`: 可添加配置文件管理
- `src/data/`: 可添加数据处理模块 