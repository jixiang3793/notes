https://git-scm.com/docs

使用场景示例
#### 1. 克隆代码，建立自己分支
```js
git clone http://192.168.54.191/rg-linkid/linkid-frontend.git
git fetch                                   // 拉取所有分支最新代码
git checkout -b your-branch origin/develop  // 从远端develop分支建立本地your-branch分支
```
#### 2. 功能完成后，提交代码合并请求流程
当开发一新功能点完后，或者解决bug后，提交代码到远端的develop分支
```js
git fetch                                        // 拉取所有分支最新代码
git checkout develop                             //切换到本地develop分支
git pull                                         // 在本地的develop分支上更新远程develop分支最新代码
git checkout your-branch                         // 切换到本地自己新建your-branch的分支上
git merge develop                                // 合并本地develop分支代码
git push origin your-branch:fix-bug-develop-auth //推送本地your-branch分支到远端新建的fix-bug-develop-aut分支
```
当上述命令操作后，到gitlab服务器上提合并请求或者点击命令行提供的链接，合并到develop分支上，如下图所示

#### 3. 当功能较多，需要逐步提交代码，但有未完成的代码提交流程
```js
git add ./your-code-finish.js  // 添加需要提交的已完成的功能代码
git commit -m "已完成的功能代码"  // 本地提交
git stash                      // 将未完成代码放入暂存区
...                            // 提交代码合并请求流程的操作命令
```
#### 4. 合并提交
当在gitlab服务器上提合并请求，勾选提交合并

#### 5. 撤销本地提交
```js
git reset HEAD~1   // 撤回本地的一次提交
```

#### 6. 本地合并冲突，使用远端覆盖本地代码
```js
git reset --hard origin/master
```

#### 7. 创建patch导入patch
从指定commit区间创建patch
```js
git diff d3d0d26cbf8e6c13cc71cf21da562c6cd35cbc8e HEAD > 490_493_bug.patch
```
git apply 490_493_bug.patch
```js
```

#### 8. 指定版本号，建立新分支
```js
git checkout d3d0d26cbf8e6c13cc71cf21da562c6cd35cbc8e
git checkout -b fix-some-bug
```
参考链接1：https://juejin.im/post/5b5851976fb9a04f844ad0f4

参考链接2：https://blog.csdn.net/liuhaomatou/article/details/54410361

#### 9.撤销add操作
```
git reset HEAD
```

#### 10.add操作参数
```
git add -h  // 查看帮助
git add -u  // 有更新过的文件才add
```

#### 11.在checkout某个commit之后，不小心提交到这上面；然后切回到develop分支，此次是如何回到上次提交的地方
```
git reflog
找到提交的相关信息及comoit号
再切回commit号
```




