---
title: GitHub 部署个人博客
cover: 'https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204052130527.png'
date: 2022-04-05 21:13:20
tags: 
  - 前端
  - GitHub
  - Hexo
excerpt: 借助GitHub的力量，部署好自己的个人博客
categories: 前端


---

教程适用于`Windows`

---

# 安装

## 1、安装`node.js`

​	`hexo`是基于`node.js`的，所以需要先安装`node.js`

​	直接去[官网](https://nodejs.org/zh-cn/)下载对应你电脑版本的安装即可

## 2、安装`hexo`

[官网参考文档](https://hexo.io/zh-cn/docs/)，可以参考一下

```shell
npm install -g hexo-cli  # 安装hexo
# 这一步往往需要科学上网，不然会非常慢
# 也有的教程是说改国内镜像源
# 但是适用国内镜像源会出一点小问题，所以我用了官网镜像源
```

出现下面就算成功了

![image-20220405213817866](https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204052138992.png)

---

# 创建博客

## 1、初始化

```shell
# 生成一个名为 folder 的文件夹
# 这个文件夹里面就是你的博客了
hexo init <folder>
cd <folder>  # 切花到这个文件夹下
```

## 2、文件结构

```shell
.
|—— _config.yml  # 配置文件
|—— package.json # 配置文件
|—— scaffolds # 生成的markdown模板
|—— source # 资源文件，图片或者文章都在这
|	|—— _posts # 文章
|—— themes # 主题
```

## 3、下载主题

​	每个主题的用法有些许不一样，主题一般会给出官方用法，我们去到[主题网](https://hexo.io/themes/)下载自己喜欢的主题即可

​	我使用的主题叫做`quiet`，所以接下来会使用这个主题作为教程，其他主题操作类似

​	下载下来的主题，放到 `themes` 目录下，**如图所示**，我这里下载了多个主题，有一个就够了

![image-20220405215544804](https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204052155840.png)

## 4、测试

​	首先，我们先到本地测试，记住三条命令即可，随便找一个终端，切换到上述`<folder>`目录即可。

​	发布，记住一条命令即可。

- **生成网页**

```shell
hexo g  # 我们发现根目录下有 public 文件夹
hexo server # 生成服务
# 然后浏览器访问 https://localhost:4000即可
```

​	下图是我的文件根目录结构，只需要注意**红框**里面的即可。

![image-20220405215423041](https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204052154141.png)

---

# 配置

## 1、更改`hexo`博客的配置

​	更改**`_config.yml`**的文件内容

```yaml
# 第5行处
# Site
title: # 网站标题
subtitle: ''
description: '' # 简单介绍
keywords:
author: # 作者
language: zh-CN
timezone: ''

# 第100行左右
theme: quiet # 更改为自己的主题名字，themes/<主题文件夹名>
# 使用这个后面<主题文件夹名>就可以
```



## 2、更改`quiet`主题的配置

​	更改文件**`themes/<主题文件夹>/_config.yml`**，这个是更改主题的配置，这里要根据自己的主题来。

​	每个主题都不一样，只能作为参考，不能完全照抄。

- **基础设置**

​	图片修改**`themes/<folder>/source/image/`**下面的图片即可，最好**长宽比例**不要变，不然丑，哈哈哈

```yaml
# 网站标题
title: 主页
# 网站标题后缀
suffix: 雨探青鸟
# 作者名称(会显示在首页文章下面)
author: MINZHI
# 首页简介（显示在首页顶部Logo的那句话）
home_describe: 我   想    读    研    究   生
# 网站关键字
keyword: 雨探青鸟的博客
is_article_img: false  #false是否开启文章背景图显示(随机图片)
# 网站描述
web_description: 雨探青鸟的个人博客

# logo
logo: /image/logo.png  # 我更改了自己的图片
# 网页标签上那个小图标 一定要用本地存储
icon: /image/favicon.ico # 我也更改了自己的icon
##### 上面的话，没有啥好讲的
#### 对应着下图的一些东西
```

![image-20220405222601632](https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204052226682.png)

![image-20220405222631005](https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204052226063.png)



- **导航栏设置**

```yaml
# 导航名称，原版是英文，我修改为中文
menus_title:
  home: 主页
  archive: 档案
  categories: 分类
  tags: 标签
  links: 友链
  about: 关于
```

![image-20220405222935475](https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204052229553.png)



- **图标设置**

图标我是在[阿里巴巴](https://www.iconfont.cn/)上面找到的

```yaml
# 这里我用的我自己图床里面的文件，如果想知道怎么配置图床，可以看我的另一篇博客
topIcon:
  homeIcon: "/image/logo.png"  # 这个只能使用本地的文件，不然会有点问题
  archivesIcon: "https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204051903462.png"
  tagIcon: "https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204051929205.png"
  linksIcon: "https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204051905452.png"
  categoriesIcon: "https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204051828739.png"
 # 列如下图
```

![image-20220405223336833](https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204052233887.png)

- **访问量统计**

​	我用的是不蒜子做的，原本的主题没有加入访问量统计的插件。我改了一下代码，对于一般主题都适用。

​	当然，如果你下载的主题有访问量统计，只需要配置一下就行。

**`_config.yml`**文件修改：

```yaml
# 网页访问统计
web_analytics:  
  enable: true #需要改为true
  baidu: https://busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js  # 不蒜子
```

**`themes/<folder>/layout/_partial/foot.ejs`**文件修改：

```javascript
<div class="Copyright">
	©<%= new Date().getFullYear() %> By <%- theme.author %>.    本站总访问量：
	<script async src="//busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js"></script>
	<span id="busuanzi_container_site_pv"><span id="busuanzi_value_site_pv"></span>次</span>
</div>
<!--这个是更改过的，注意上面第3 4行，这个是重点-->
```



- **底部图标**

```yaml
# 底部显示的图标（github 或者其他）
bottomIcon: 
  #可以多个
  - {
    #描述名称
    name: 'Github',
    #图标    
    iconLink: 'https://cdn.jsdelivr.net/gh/duogongneng/MyBlogImg/imggithub.png',
    #跳转链接    
    toUrl: 'https://github.com/MinzhiYoyo'
  }
```

- **友情链接**

```yaml
# 友情链接
linksList:
  - {
    title: '本项目仓库', # 名字
    intro: '包含源码和发布文件', # 简单的描述
    link: 'https://github.com/MinzhiYoyo/MinzhiYoyo.github.io', # 跳转链接
    image: 'https://raw.githubusercontent.com/MinzhiYoyo/ImageHost/main/202204052122364.jpg' # 图片链接
  }
```

# 发布

## 1、`GitHub`配置

## 2、配置`token`

## 3、上传

 ```shell
# 上述配置完成
hexo g -d  # 一条命令上传了
 ```

