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
**5、**git rebase origin/branch**：让你在和别人分享提交之前对你的提交进行分割、合并或者重排序。<br>
<span style="color:red">注:在git rebase origin/branch遇到冲突，要解决冲突后重组：git add --all 然后 git rebase --continue</span>
