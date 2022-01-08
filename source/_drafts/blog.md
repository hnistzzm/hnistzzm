---

title: blog

categories:
- blog搭建
tags:
- hexo


---
# blog

# 安装hexo出现问题

![image-20220105172513638](https://gitee.com/jwz--jwz/cloud-img/raw/master/image/202201051725679.png)



## 解决办法：

 **nodejs没有配置全局变量**

**获取全局变量配置**

```bash
npm config get prefix
```



![image-20220105172739717](https://gitee.com/jwz--jwz/cloud-img/raw/master/image/202201051727741.png)

**配置系统变量（如下图所示）:**



<img src="https://gitee.com/jwz--jwz/cloud-img/raw/master/image/202201051729183.png" alt="image-20220105172905149" style="zoom: 67%;" />

**安装：**

```bash
npm install -g hexo-cli 
```

**测试是否成功：**

```bash
hexo -v 
```





<img src="https://gitee.com/jwz--jwz/cloud-img/raw/master/image/202201051730000.png" alt="image-20220105173021966" style="zoom:80%;" />





# VScode管理博客分类与标签

> 应用商店搜索：vscode-hexo-utils ，点击安装即可
>

![image-20220105173327385](https://gitee.com/jwz--jwz/cloud-img/raw/master/image/202201051733412.png)

效果图展示：

<img src="https://gitee.com/jwz--jwz/cloud-img/raw/master/image/202201051739143.png" alt="image-20220105173956092" style="zoom:80%;" />





# 看板娘收集：

##  看板娘：

> 看板娘是一种职业和习惯称呼，也是ACGN次文化中的萌属性之一。简而言之就是小店的女服务生，也有“吸引顾客，招揽生意，提高人气”等作用类似品牌形象代言人的含义。
>
> 资源（.moc）全部收集自互联网，目前合集包括海王星系列、初音未来、雷姆、凉风青叶、尼禄、薇尔莉特、小埋、樱花庄、玉藻前。

## 链接地址：

> [Live2d模型合集分享 | FaceRig | 海王星系列 | 初音未来 | 雷姆 | 凉风青叶 | 尼禄 | 薇尔莉特 | 小埋 | 樱花庄 | 玉藻前 (wikimoe.com)](https://www.wikimoe.com/?post=158&comment-page=2#comments)



## hexo配置：

### 安装：

> 使用`helper-live2d`的Live2d插件https://github.com/EYHN/hexo-helper-live2d



```bash
npm install --save hexo-helper-live2d

```

### 配置:

> 安装成功后，在hexo根目录的`_config.yml`添加如下配置(可以写在主题配置文件里)

```yaml
# Live2D
## https://github.com/EYHN/hexo-helper-live2d
live2d:
  enable: true # 开启live2d
  # enable: false
  scriptFrom: local # 默认
  pluginRootPath: live2d_models/ # 插件在站点上的根目录(相对路径)
  pluginJsPath: lib/ # 脚本文件相对与插件根目录路径
  pluginModelPath: assets/ # 模型文件相对与插件根目录路径
  # scriptFrom: jsdelivr # jsdelivr CDN
  # scriptFrom: unpkg # unpkg CDN
  # scriptFrom: https://cdn.jsdelivr.net/npm/live2d-widget@3.x/lib/L2Dwidget.min.js # 你的自定义 url
  tagMode: false # 标签模式, 是否仅替换 live2d tag标签而非插入到所有页面中
  debug: false # 调试, 是否在控制台输出日志
  display:
     position: right
  mobile:
     show: false   
  model:
     scale: 1.2
     use: violet
```

![](https://gitee.com/jwz--jwz/cloud-img/raw/master/image/202201052100966.png)



> 将`薇尔莉特·伊芙加登`复制到刚从新建的`live2d_models`文件夹内，然后重命名为`violet`(当然这个名字是你自定义的)，然后进入`violet`文件夹，里面有个`14.json`文件，将他重命名为`violet.model.json`其他文件无需修改，最后在`live2d`配置里的`model:`下的`use:`输入模型文件夹名(violet)
>
> ![image-20220105210408068](https://gitee.com/jwz--jwz/cloud-img/raw/master/image/202201052104094.png)

![image-20220105210324967](https://gitee.com/jwz--jwz/cloud-img/raw/master/image/202201052103997.png)

> 使用hexo g 生成代码 ，hexo s 运行
