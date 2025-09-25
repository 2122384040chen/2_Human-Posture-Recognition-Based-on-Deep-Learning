# 行为识别系统

## 项目介绍
这是一个基于ResNet深度学习模型的人体行为识别系统，通过计算机视觉技术对人体动作进行实时识别和分类。系统具有友好的图形界面，支持视频文件分析和实时摄像头输入分析。

## 功能特点
- 支持多种人体动作识别：站立、坐、摔倒、打电话、骑自行车、跳舞等14种行为
- 提供两种使用模式：直接使用模式和登录认证模式
- 实时视频分析功能
- 视频文件导入分析功能
- 友好的图形用户界面
- 模型训练和评估工具

## 系统要求
- Python 3.8+
- CUDA支持（推荐用于加速模型推理）
- 摄像头（用于实时分析功能）

## 安装指南
1. 克隆或下载项目代码
2. 安装所需依赖：
   ```
   pip install -r requirements.txt
   ```
3. 将预训练模型权重文件放置在`weights`文件夹下，并确保命名为`resnet34_best`

## 使用方法
### 直接使用模式
运行以下命令直接启动系统（无需登录）：
```
python run_main_noLogin.py
```

### 登录认证模式
运行以下命令启动需要登录的系统：
```
python run_main_login.py
```

## 模型训练
如需重新训练模型，请运行：
```
python train1.py
```
训练指标会保存在`training_metrics`文件夹中。

## 自定义行为类别
如需自定义行为类别，请按以下步骤操作：
1. 在`label_name.py`中修改类别标签定义
2. 在`System_noLogin.py`中添加详细的类别信息

## 项目结构
- `run_main_noLogin.py`：无登录版本的主运行脚本
- `run_main_login.py`：需要登录的主运行脚本
- `System_noLogin.py`：无登录版本的系统实现
- `System_login.py`：需要登录的系统实现
- `LoginWindow.py`与`LoginForm.py`：登录界面相关实现
- `Recognition_UI.py`：主界面UI实现
- `model.py`：ResNet深度学习模型实现
- `label_name.py`：行为类别标签定义
- `dataset.py`：数据集处理（按6:2:2划分训练/验证/测试集）
- `train1.py`：模型训练脚本
- `predict1.py`：模型预测工具
- `weights/`：模型权重存放目录
- `training_metrics/`：训练评价指标图表保存目录
- `test_images/`：测试图像目录

## 注意事项
1. 确保预训练权重文件已正确放置在`weights`文件夹中
2. 修改行为类别需同时更新多个相关文件
3. 默认使用ResNet34架构 