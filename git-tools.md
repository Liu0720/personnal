#本地所有改动都需要用git push推送到网页上的git仓库才能更新远程仓库内容
#涉及到合并代码的操作时，如果有冲突就要先解决冲突后才能进行代码推送
#任何进行了git的误操作都可以进行版本回退
#使用http的提交方式需要每次都进行用户密码验证，推荐使用ssh的方式（需要进行公钥生成并添加到远程仓库中）

git add ./相对于当前目录路径的文件名
git status #查看当前暂存区和未添加到暂存区的内容
git log #查看当前的git历史提交记录
git commit -m "提交内容"  #提交到本地仓库里
git push 远程仓库名 HEAD:远程分支名 #如果当前分支关联了远程的某一分支则可以直接进行git push


git reflog #查看git操作记录
git revert commitid #撤销本地远程仓库某一个提交

git checkout -b 新分支  #创建并切换到这个新分支
git switch <新分支> #切换到新分支
git merge <其他分支>  #合并其他分支到当前分支

git cherry-pick commitid  #这里是将其他分支上的某一个hash提交到当前分支上 ***推荐的挑选提交的方式

git stash #保存当前工作区的修改以便切换到其他分支做其他事情也可以将提交进行回退将内容添加到暂存区切换分支进行pop覆盖
git stash pop  #将保存stash的修改导出到当前分支上

git reset --soft/--hard/--mixed commitid #将当前分支退回到某一次提交,对应保留工作和暂存区/不保留工作和暂存区/暂存变为工作区   #回退文件则在后面加上路径

git branch #查看本地分支
git branch -a #查看本地和远程的所有分支
git branch -r #查看远程分支

git remote -v #查看远程仓库的信息
git remote add 远程仓库名 远程仓库链接 #本地添加远程仓库可以进行push提交或者pull拉取代码
git remote set-url 远程仓库名 远程仓库链接 #修改远程仓库链接
git remote rm 远程仓库名 #删除本地远程仓库

git restore --staged <file>：将指定文件从暂存区中移除，恢复到未暂存的状态，但不影响工作区的文件。
git restore --staged.：这将清空整个暂存区，将所有暂存的文件恢复到未暂存的状态。
