## 使用 [`git-repo`](https://github.com/GerritCodeReview/git-repo) 管理多个 git 代码库

1. 获取 repo 脚本
```
mkdir -p ~/.bin
PATH="${HOME}/.bin:${PATH}"
curl https://raw.githubusercontent.com/GerritCodeReview/git-repo/master/repo > ~/.bin/repo
chmod a+rx ~/.bin/repo
```

2. 初始化 `repo`
```
repo init -u https://github.com/dezng/manifests --repo-url=https://github.com/GerritCodeReview/git-repo
```

3. 添加 `local_manifests`
```
mkdir .repo/local_manifests
touch .repo/local_manifests/github.xml
```
文件内容如下，具体格式可查看[官方文档](https://github.com/GerritCodeReview/git-repo/blob/main/docs/manifest-format.md)：
```
<?xml version="1.0" encoding="UTF-8" ?>
<manifest>
    <!-- your project -->
    <project
        name="google/volley"
        group="demo"
        path="google/volley" />
</manifest>
```

4. 同步代码
```
repo sync
```

详细用法请访问 [git-repo](https://github.com/GerritCodeReview/git-repo)
