# git-分支
---

### git-分支操作

- **查看当前所处分支**
```shell
git branch
```

- **创建分支**
```shell
git branch <branch_name>
```

- **切换分支**
```shell
git checkout <branch_name>
```

- **合并分支**
```shell
git merge <branch_name>
```

### git-分支案例

- **修复bug案例**
```shell
假设有一个程序需要开发新的需求，需求开发到一半时线上软件出现了bug需要紧急修复。
解决方案：
1. 终止新需求开发，解决bug，解决完毕后重新开发新需求
2. 利用git分支，bug修复和新需求开发同时进行

# 1.在main分支上创建bug分支和dev分支
git branch bug && git branch dev

# 2.切换到bug分支上修复bug
git checkout bug

# 3.bug修复完成合并到main分支
git checkout main && git merge bug

# 4.切换到dev分支开发功能
git checkout dev

# 5.功能开发完毕合并到main分支
git checkout main && git merge dev

# 6.此时可能会发生合并冲突，手动解决冲突

# 7.提交代码到版本库
```