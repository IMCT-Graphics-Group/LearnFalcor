# Falcor踩坑笔记

## 1. 拉取与编译流程

大体上可以参考这篇[知乎文章](https://zhuanlan.zhihu.com/p/594293309)，但还有一些需要注意的小细节（可能由Falcor版本不同引起）：

-  运行**setup_vs2022.bat**生成vs工程的时候可能会报错，原因可能是来自python的版本问题，也可能是挂了梯子（最好不挂梯子的情况下编译工程）。
- visual studio中生成解决方案时，可能会由出现由文件编码问题引发的错误。我遇到的问题是**fast_float.h**文件的unicode字符集不够大，将其从**UTF-8**修改为**UTF-16**解决。
- 编译成功之后一般是先运行**Mogwai.exe**，这个是Falcor的图形化界面。需要加载脚本（例如Falcor/scripts/PathTracer.py），并加载场景（例如Falcor/media/Arcade/Arcade.pyscene）。相当于指定渲染器和场景信息，只加载一个是渲染不出东西的！