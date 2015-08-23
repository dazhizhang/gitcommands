# gitcommands
gitcommands essential

新建repository的时候，git给的提示是

…or create a new repository on the command line


echo # gitcommands >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin git@github.com:dazhizhang/gitcommands.git
git push -u origin master
…or push an existing repository from the command line


git remote add origin git@github.com:dazhizhang/gitcommands.git
git push -u origin master

实际操作的经验总结是（git shell，使用于只有一个branch）：

// 简单当前用户权限
ssh -T git@github.com

// 初始化当前文件夹为一个git项目（可能也就是一个branch）
git init

// 告诉本地git软件哪些文件是交给git处理的。 . 变成 * 也可以
git add . 
// 把所有本文件夹的（本branch）所有文本编辑器里面进行的新增，修改项目提交给本地的git软件
git commit -m "first commit"

// 连接本地branch到git服务器仓库 （只连接一次就可以）
// 如果连接时提示已经存在，就忽略，继续后面命令
git remote add origin git@github.com:IBPort/zhuanyuntiqu.git

// 把本地变更提交给git服务器， 如果不考虑branch, 直接用 git push 也可以。
git push -u origin master

// 每次新增或者修改文件都需要执行的操作是下面三个，
// 1. 每次都需要add是很奇怪的，但是本人测试不add就提交不成功。
// 2. 每个commit 的名字都不同，记住别忘了写 -m 参数，表明是新增的commit label
// 3. 如果只有一个branch就每次git push就可以了。
git add .
git commit -m "first commit"  
git push -u origin master

下面是参考文献：
http://www.cnblogs.com/xrong/archive/2013/03/22/2975882.html
http://blog.csdn.net/ithomer/article/details/7529022

git 有一个好的地方是如果服务器仓库发生了变化，
本地仓库也发生了变化。
如果先执行pull，可以把服务器的变化pull到本地来，本地发生的变化会保持不变
（在本地发生变化的文件和服务器发生变化是不同的文件的情况下）
然后可以再把本地的变化push到服务器上。


