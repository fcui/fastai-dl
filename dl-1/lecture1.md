# 第一课 猫狗识别

## windows 10下的运行环境配置

1. 安装anaconda 5.2版本并进行更新

   ```bash
   conda update --all
   ```

2. 安装pythorch 0.4版本, 需搭配CUDA 9.0版本

   ```bash
   conda install pytorch -c pytorch
   pip3 install torchvision
   ```

3. 在运行过程中可能会出现 `import PIL.Image` 的错误, 这里需要

   ```bash
   conda uninstall pillow
   pip intall pillow
   ```

   如果`pip`安装不了, 就去[这里](https://www.lfd.uci.edu/~gohlke/pythonlibs/)下载, 然后本地安装.

4. 在本地下载fastai

   ```bash
   git pull https://github.com/fastai/fastai.git
   ```

## 第一个示例

1. 为了在notebook中能导入本地的fastai, 要加入路径

   ```python
   import sys
   sys.path.append("E:\\MyProject\\Book\\fastai\\old")
   print(sys.path)
   ```

2. 在`notebook`中加入必备的库:
    ```python
    # to get automatic reloading
    %reload_ext autoreload
    %autoreload 2
    %matplotlib inline

    import fastai
    # This file contains all the main external libs we'll use
    from fastai.imports import *

    from fastai.transforms import *
    from fastai.conv_learner import *
    from fastai.model import *
    from fastai.dataset import *
    from fastai.sgdr import *
    from fastai.plots import *
    ```

3. 设定数据目录, `sz`是图片重置后的尺寸, 以确保运算速度(具体看以后的课程解释)
    ```python
    PATH = "../../data/dogscats/" # 根据个人情况调整
    sz = 224
    ```

4. 确认`CUDA`和`CuDNN`是否启用:
    ```python
    torch.cuda.is_available()
    torch.backends.cudnn.enabled
    ```

5. 获取[数据](http://files.fast.ai/data/dogscats.zip), 将其解压至前面指定的目录`PATH`中

6. 