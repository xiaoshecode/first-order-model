# first-order-model 维护说明

First Order Motion Model 论文的人像/物体运动迁移实现。

- 上游：https://github.com/AliaksandrSiarohin/first-order-model
- 在线文档：https://xiaoshecode.github.io/xiaoshecode/repos/first-order-model/
- 检查日期：2026-10-30

## 环境与使用

- 在隔离 Python 环境安装 requirements.txt 的历史版本依赖。
- python -m pip install -r requirements.txt

使用/检查入口（需先满足依赖条件）：

- `python demo.py --config config/vox-256.yaml --driving_video driving.mp4 --source_image source.png --checkpoint checkpoint.pth.tar --relative --adapt_scale`

## 目录职责

- demo.py — 推理入口
- run.py / train.py — 训练
- modules/ — 网络组件
- config/ — 数据集配置
- frames_dataset.py — 训练数据加载

## 本次整理

- 新增维护文档和在线文档入口，补全用途、目录、使用路径及验证边界。

## 检查记录

- **仓库目录与入口盘点**（passed）：检查 Git 索引中的 47 个路径、README 和项目配置；不等于功能验收。
- **Python AST**（passed）：21 个文件通过解析；不导入依赖、不执行应用。
- **JSON/notebook parse**（passed）：2 个文件通过解析；不导入依赖、不执行应用。
- **完整构建与端到端运行**（not_run）：旧版本 PyTorch/scikit-image 依赖可能不兼容当前 Python；未下载训练数据或模型，未完成 GPU 推理。

## 验证边界与待办

- 旧版本 PyTorch/scikit-image 依赖可能不兼容当前 Python；未下载训练数据或模型，未完成 GPU 推理。

## 后续维护约定

保留上游许可证与作者信息。沿用现有模块边界和格式配置；修复功能时同步最小回归验证。依赖或接口变更需写明迁移步骤，避免仅为目录美观搬动公开入口。
