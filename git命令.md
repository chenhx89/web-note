**1、**git status：命令可以列出当前目录所有还没有被git管理的文件和被git管理且被修改但还未提交(git commit)的文件。<br>
**2、**git add . ：命令主要用于把我们要提交的文件的信息添加到索引库中。或<br>
**2、**git add -A：表示把(path)中所有tracked文件中被修改过或已删除文件和所有untracted的文件信息添加到索引库。<br>
**3、**git commit  -m "提交的描述信息"：提交修改内容和备注。<br>
**4、**git fetch origin branch：
<pre>$ git fetch &lt;远程主机名&gt;：该命令将某个远程主机的更新，全部取回本地。
默认情况下，git fetch取回所有分支(branch)的更新。如果只想取回特定分支的更新，可以指定分支名。
$ git fetch &lt;远程主机名&gt; &lt;分支名&gt;
比如，取回origin主机的master分支：$ git fetch origin maste
git branch命令的-r选项，可以用来查看远程分支，-a选项查看所有分支。</pre>

**5、**git rebase origin/branch：让你在和别人分享提交之前对你的提交进行分割、合并或者重排序。<br>
<span style="color:red">注:在git rebase origin/branch遇到冲突，要解决冲突后重组：git add --all 然后 git rebase --continue</span>
<span style="color:blue">注：4和5两步可合成一步：git pull --rebase origin master</span><br>

**6、**git push origin branch：将本地代码推送到远程分支上<br>
**7、**git reset --hard origin/html：切换到最新分支<br>
**8、**rm -rf site：删除分支
**9、**git push origin html:master：把html分支的代码推到master分支上<br>
**10、**git pull origin html：在html分支上拉代码<br>

**11、撤销操作**
<pre>git rebase --abort：撤销合并操作
git checkout file-name：恢复某个已修改的文件
git checkout . ：撤销所有修改文件
git revert：撤销add
git revert HEAD：撤销前一次 commit
git revert HEAD^：撤销前前一次 commit
git revert commit-id （比如：fa042ce57ebbe5bb9c8db709f719cec2c58ee7ff）撤销指定的版本，撤销也会作为一次提交进行保存。
</pre>

**12、**克隆：先cd到要克隆的目录然后放克隆文件地址<br>
如：git clone git@git.siyinjia.com:siyinjia/background.git<br>
**13、**git diff：上下左右键盘查看提交代码修改情况 退出 q<br>

**14、分支合并**
<pre>比如，如果要将开发中的分支（develop），合并到稳定分支（master），
首先切换的master分支：git checkout master。
然后执行合并操作：git merge develop。
如果有冲突，会提示你，调用git status查看冲突文件。
解决冲突，然后调用git add或git rm将解决后的文件暂存。
所有冲突解决后，git commit 提交更改。</pre>

**15、分支衍合**
<pre>分支衍合和分支合并的差别在于，分支衍合不会保留合并的日志，不留痕迹，而分支合并则会保留合并的日志。
要将开发中的分支（develop），衍合到稳定分支（master）。
首先切换的master分支：git checkout master。
然后执行衍和操作：git rebase develop。
如果有冲突，会提示你，调用git status查看冲突文件。
解决冲突，然后调用git add或git rm将解决后的文件暂存。
所有冲突解决后，git rebase --continue 提交更改。</pre>

**16、删除分支**
<pre>执行git branch -d <分支名>
如果该分支没有合并到主分支会报错，可以用以下命令强制删除git branch -D <分支名></pre>


