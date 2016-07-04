
### js常用函数
1、split() 方法用于把一个字符串分割成字符串数组。 如：
<pre>var str="how are you doing today?"
document.write(str.split(" "));     //["how", "are", "you", "doing", "today?"]
document.write(str.split(" ",3));   //["how", "are", "you"]
</pre>
2、join() 方法用于把数组中的所有元素放入一个字符串。如：
<pre>var arr = ["George","John","Thomas"];
document.write(arr.join());         //"George,John,Thomas"
document.write(arr.join("."));      //"George.John.Thomas"
</pre>
3、concat() 方法用于连接两个或多个数组。如：
<pre>var a = [1,2,3], b=[4,5,6]
document.write(a.concat(4,5));  //[1, 2, 3, 4, 5]
document.write(a.concat(b));    //[1, 2, 3, 4, 5, 6]
</pre>
4、pop() 方法用于删除并返回数组的最后一个元素。如：
<pre>var arr = ["George","John","Thomas"];
document.write(arr.pop());     //"Thomas"
document.write(arr);           //["George", "John"]
</pre>
5、push() 方法可向数组的末尾添加一个或多个元素，并返回新的长度。如：
<pre>var arr = ["George","John","Thomas"];
document.write(arr.push("tom"));   //4
document.write(arr);               //["George", "John", "Thomas", "tom"]
</pre>
6、reverse() 方法用于颠倒数组中元素的顺序。如：
<pre>var arr = ["George","John","Thomas"];
document.write(arr.reverse());     //["tom", "Thomas", "John", "George"]
</pre>