**1、** git status：命令可以列出当前目录所有还没有被git管理的文件和被git管理且被修改但还未提交(git commit)的文件。<br>
**2、**git add . ：命令主要用于把我们要提交的文件的信息添加到索引库中。或<br>
**2、**git add -A：表示把(path)中所有tracked文件中被修改过或已删除文件和所有untracted的文件信息添加到索引库。<br>
**3、**git commit  -m "提交的描述信息"：提交修改内容和备注。<br>
**4、**git fetch origin branch：<pre>$ git fetch &lt;远程主机名&gt;：该命令将某个远程主机的更新，全部取回本地。
默认情况下，git fetch取回所有分支(branch)的更新。如果只想取回特定分支的更新，可以指定分支名。
$ git fetch &lt;远程主机名&gt; &lt;分支名&gt;
比如，取回origin主机的master分支：$ git fetch origin maste
git branch命令的-r选项，可以用来查看远程分支，-a选项查看所有分支。
</pre>
**5、**git rebase origin/branch：让你在和别人分享提交之前对你的提交进行分割、合并或者重排序。<br>
<span style="color:red">注:在git rebase origin/branch遇到冲突，要解决冲突后重组：git add --all 然后 git rebase --continue</span>
<span style="color:blue">注：4和5两步可合成一步：git pull --rebase origin master</span><br>

**6、**git push origin branch：将本地代码推送到远程分支上<br>
**7、**git rebase --abort：撤销合并操作<br>
**8、**git reset --hard origin/html：切换到最新分支<br>
**9、**rm -rf site：删除分支
**10、**git push origin html:master：把html分支的代码推到master分支上<br>
**11、**git pull origin html：在html分支上拉代码<br>

**15、**撤销操作<pre>git checkout file-name：恢复某个已修改的文件
git checkout . ：撤销所有修改文件
git revert：撤销add
git revert HEAD：撤销前一次 commit
git revert HEAD^：撤销前前一次 commit
git revert commit-id （比如：fa042ce57ebbe5bb9c8db709f719cec2c58ee7ff）撤销指定的版本，撤销也会作为一次提交进行保存。
</pre>

**16、**克隆：先cd到要克隆的目录然后放克隆文件地址<br>
如：git clone git@git.siyinjia.com:siyinjia/background.git
