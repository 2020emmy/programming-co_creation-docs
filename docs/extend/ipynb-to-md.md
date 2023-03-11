---
title: Jupyter Notebook转markdown
---

### 缘起

为了能方便的把Jupyter Notebook的 .ipynb文件能方便的导出到其他地方展示，最终发现能转成markdown,这可太香了，既能发文章，又能很方便的用于前端网页展示。

### 方法

打开powershell，新建一个文件夹，把需要转化的jupyter文件克隆到本地。

> 比如说我们要把李俊老师的Github仓库克隆到本地：https://github.com/coding-newbies-group/pilot

![image-20230311135759840](https://raw.githubusercontent.com/DSH5200/images/master/image-20230311135759840.png)

然后安装转化工具：pip install nbconvert

![image-20230311135850001](https://raw.githubusercontent.com/DSH5200/images/master/image-20230311135850001.png)

如果这一步报错了，请尝试 更新pip版本，可以使用以下命令更新

> python -m pip install --upgrade pip

![image-20230311135929006](https://raw.githubusercontent.com/DSH5200/images/master/image-20230311135929006.png)

如果更新后仍然无法正常安装，可以尝试指定一个不同的源来安装，比如清华源：

> python -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple nbconvert

![image-20230311140009564](https://raw.githubusercontent.com/DSH5200/images/master/image-20230311140009564.png)

![image-20230311140050937](https://raw.githubusercontent.com/DSH5200/images/master/image-20230311140050937.png)

如此这样就是安装OK啦

> successfully installed attrs-22.2.0 beautifulsoup4-4.11.2

在powershell里面，执行这条命令 jupyter nbconvert --to markdown XXX.ipynb

![image-20230311140151414](https://raw.githubusercontent.com/DSH5200/images/master/image-20230311140151414.png)

然后就可以转化我们想要转化的文件了，比如说我们现在想转化 p1-3,可以执行以下命令

> jupyter nbconvert --to markdown .\p1-3-structure-2.ipynb

![image-20230311140308736](https://raw.githubusercontent.com/DSH5200/images/master/image-20230311140308736.png)

可以看到 converting notebook to markdown, 然后它写了9134个字节到 .md文件。

执行 start . 就可以打开当前目录

![image-20230311140410901](https://raw.githubusercontent.com/DSH5200/images/master/image-20230311140410901.png)

### 更改公式

需要注意的是，在转化markdown之后，然后就可以更改公式。举个例子：

> $
>
> \begin{align}
>
> f(a,b) = \sqrt{a^2 + b^2}
>
> \end{align}
>
> $

方法是，分别把以下两个内容改成$$

> $
>
> \begin{align}
>
> \end{align}
>
> $

也就变成了这样，如此就成功了。

> $$
>f(a,b) = \sqrt{a^2 + b^2}
> $$



同学们可以练起来啦！
