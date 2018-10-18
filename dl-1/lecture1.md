# 第一课 猫狗识别

## windows 10下的安装环境配置

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

5. 为了在notebook中能导入本地的fastai, 要加入路径

   ```python
   import sys
   sys.path.append("E:\\MyProject\\fastai\\old")
   print(sys.path)
   ```

6. 