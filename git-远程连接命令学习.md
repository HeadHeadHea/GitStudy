# git-远程连接
---

### git-远程操作

- **本地代码推送远端**
```shell
# 添加远程仓库
git remote add <remote_host_name>(远程主机名任意命名) <url>

# 推送代码
git push [-u] <remote_host_name> <local_host_name>:<remote_branch>

# 将本地的dev分支上的代码推送到远程主机名为origin中test的分支上。如果远程的test分支不存在，则会被创建
git push origin dev:test

# 本地分支名和远程分支名一样的情况下，可以省略:<远程分支名>。如果远程主机中不存在该分支，那么会被创建
git push origin dev

# 如果本地分支已经跟远程分支建立了追踪关系，那么可以省略<远程主机名>和<远程分支名>
git push
```

- **远端代码克隆到本地**
```shell
git clone <url>
```

- **本地同步远端代码**
```shell
git pull <remote_host_name> <remote_branch>:<local_branch>

# 要取回origin主机的next分支，与本地的master分支合并
git pull origin next:master

# 远程分支(next)要与当前分支合并，则冒号后面的部分可以省略
git pull origin next
```

### git-案例

- **在家里上传代码**
```shell
# 1.给远程主机起名
git remote add origin 仓库链接

# 2.向远程主机推送代码
git push -u origin main
git push -u origin dev

# 3.假设此时main分支上为最新代码
```

- **公司新电脑上第一次获取代码**
```shell
# 1.克隆远程代码(此时，main分支和dev分支都被clone下来)
git clone 仓库地址
```

- **公司新电脑上开发**
```shell
# 1.切换到dev分支进行开发
git checkout dev

# 2.把main分支最新代码合并到dev分支(此时，main分支和dev分支代码一样为最新)
git merge main

# 3.提交代码到远程dev分支(main分支保持不变)
git push origin dev
```

- **回到家中继续写代码**
```shell
# 1.重远程拉取代码
git pull origin dev

# 2.切换到dev分支
git checkout dev

# 3.写代码

# 4.提交代码
git push origin dev
```

- **程序编写完成将dev分支代码合并到main分支**
```shell
# 1.本地合并
git checkout main && git merge dev

# 2.提交远程(此时，main分支和dev分支都为最新)
git push origin main && git push origin dev
```