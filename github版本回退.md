# 查看日志
> git log
```
$ git log
commit 2a80b3422168fbf33dda83af0bcb84c2dd3d6586
Author: 1107185874 <1107185874@qq.com>
Date:   Mon Mar 27 21:52:24 2017 +0800
    版本1
commit 6eb46eddbe9d0f3e8bd3404bae96d3a65d3895ad
Author: 1107185874 <1107185874@qq.com>
Date:   Mon Mar 27 21:28:09 2017 +0800
    Initial commit
```
## 简化
> git log --pretty=oneline
```
$ git log --pretty=oneline
2a80b3422168fbf33dda83af0bcb84c2dd3d6586 版本1
6eb46eddbe9d0f3e8bd3404bae96d3a65d3895ad Initial commit
```
**2a80b3是commit id(版本号)**

# 回退
**HEAD 代表当前版本**
**HEAD^ 代表上个版本，以此类推**
**HEAD~n，表示上n个版本**
> git reset --hard HEAD^
```
$ git reset --hard HEAD^
HEAD is now at 6eb46ed Initial commit
```
## 回退'未来的'版本
> git reset --hard 2a80b3

**可以不用写全版本号，git会自动去找**
```
$ git reset --hard 6eb46
HEAD is now at 6eb46ed Initial commit
```

# 查看历史日志
> git reflog
```
$ git reflog
6eb46ed HEAD@{0}: reset: moving to 6eb46
6eb46ed HEAD@{1}: reset: moving to HEAD^
2a80b34 HEAD@{2}: commit: 版本1
6eb46ed HEAD@{3}: clone: from https://github.com/1107185874/Test.git
```