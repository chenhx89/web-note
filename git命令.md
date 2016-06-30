**git status**：命令可以列出当前目录所有还没有被git管理的文件和被git管理且被修改但还未提交(git commit)的文件。<br>
**git add .**：命令主要用于把我们要提交的文件的信息添加到索引库中。<br>
**git add -A**：表示把(path)中所有tracked文件中被修改过或已删除文件和所有untracted的文件信息添加到索引库。<br>
**git commit  -m "提交的描述信息"**：提交修改内容和备注。<br>

**git fetch**：<pre>$ git fetch &lt;远程主机名&gt;：该命令将某个远程主机的更新，全部取回本地。
默认情况下，git fetch取回所有分支(branch)的更新。如果只想取回特定分支的更新，可以指定分支名。
$ git fetch &lt;远程主机名&gt; &lt;分支名&gt;
比如，取回origin主机的master分支：$ git fetch origin master
<span style="color:red">注：平时操作</span>
</pre>