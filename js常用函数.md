
### js常用函数
1、split() 方法用于把一个字符串分割成字符串数组。 如：
<pre>var str="how are you doing today?"
document.write(str.split(" "));
document.write(str.split(" ",3)); //取前三个单词
</pre>
2、join() 方法用于把数组中的所有元素放入一个字符串。如：
<pre>var arr = new Array(3)
arr[0] = "George"
arr[1] = "John"
arr[2] = "Thomas"
document.write(arr.join());  //George,John,Thomas
document.write(arr.join(.)); //George.John.Thomas
</pre>

