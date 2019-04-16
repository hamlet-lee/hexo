---
title: 构建hexo博客的流程
date: 2019-04-16 23:32:37
tags:
---

参考：https://www.cnblogs.com/jackyroc/p/7681938.html

先新建仓库 ${your-github-name}.github.io，我的github名字是 hamlet-lee，所以我的仓库名是 hamlet-lee.github.io。  
然后运行如下命令：

```shell
cnpm install hexo-cli -g
hexo init #初始化网站
cnpm install
# 或者 hexo g
hexo generate
# 或者 hexo s
hexo server
```

访问 http://localhost:4000 即可看到效果 

## 新建博客文章的方法
```shell
hexo new "构建hexo博客的流程"
```

## 上传到github的方法

修改 _config.yml 文件  
```yaml
deploy:
  type: git
  repo: git@github.com:hamlet-lee/hamlet-lee.github.io.git
  branch: master
```

安装上传的扩展
```shell
cnpm install hexo-deployer-git --save
```

修改下git配置，把自己的email设定对了，例如
vi ~/.gitconfig
```text
[user]
        name = Hamlet Lee
        email = lisining@gmail.com
```

最后
```shell
# 或者 hexo generate
hexo g
# 或者 hexo deploy
hexo d
```