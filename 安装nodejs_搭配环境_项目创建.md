
### 安装nodejs，搭配环境
<pre>1.安装nodejs（node-v0.12.7-x64）https://nodejs.org/en/ 在此官网下载，  中文版网址：http://nodejs.cn/
2.安装ruby（rubyinstaller-1.9.2-p180）注：只能安装在C盘，不要改变路径
3.命名语句：gem sources --remove http://rubygems.org/  （注：斜杠不能掉）
4.命名语句 ：gem sources -a https://ruby.taobao.org/ （注：斜杠不能掉）
5.命名语句 ：gem sources -l （是英文 l，list的 l, 不是数字 1）
6.命名语句 ：gem install compass（安装compass）
7.命名语句 ：gem install scss （安装scss）
8.cd 到项目 compass init（初始化项目）安装完成
9.全局安装gulp：npm install -g gulp
10.下载项目文件：npm install
</pre>


### nodejs 创建项目

<pre>1、创建项目名再在命名中cd到创建项目上。
2、命名语句：npm init 都直接按回车键跳过，直到在项目内生成package.json文件。
3、将下面代码复制到package.json文件内：
"dependencies": {
    "browser-sync": "^2.7.1",
    "gulp": "^3.8.11",
    "gulp-compass": "^2.0.4",
    "gulp-jade": "^1.0.0",
    "gulp-plumber": "^1.0.0",
    "gulp-watch": "^4.2.4",
  }
可以修改这里面的配置，然后运行：npm install（生成node_modules文件夹）
运行命令语句：compass init 初始化生成 config.rb写好对应文件路径
<span style="color:red">111</span>

4、再将gulpfile.js和config.rb两个文件复制到项目内，如果没有这两个文件就得到官网：https://www.npmjs.com/上去看文档写。
5、在项目内创建对应的文件夹，然后注意修改这gulpfile.js和config.rb两个文件里的对应路径。
注：gulp.task('default', ['server','jade','compass']);  注意修改这里面的对应要生成的文件。
jade：对应jade文件，compass：对应scss文件。
6、在命名中运行：compass init 初始化scss
7、在命名中运行：gulp  结束

如果不复制代码就一个个安装
3、cd到这个项目上，然后在命名中运行：npm install gulp gulp-compass 这就安装了gulp-compass 其他如这
</pre>



