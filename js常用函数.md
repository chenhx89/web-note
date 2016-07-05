
### js常用函数
1、split() 方法用于把一个字符串分割成字符串数组。 如：
<pre>var str="how are you doing today?"
console.log(str.split(" "));     //["how", "are", "you", "doing", "today?"]
console.log(str.split(" ",3));   //["how", "are", "you"]
</pre>
2、join() 方法用于把数组中的所有元素放入一个字符串。如：
<pre>var arr = ["George","John","Thomas"];
console.log(arr.join());         //"George,John,Thomas"
console.log(arr.join("."));      //"George.John.Thomas"
</pre>
3、concat() 方法用于连接两个或多个数组。如：
<pre>var a = [1,2,3], b=[4,5,6]
console.log(a.concat(4,5));  //[1, 2, 3, 4, 5]
console.log(a.concat(b));    //[1, 2, 3, 4, 5, 6]
</pre>
4、pop() 方法用于删除并返回数组的最后一个元素。如：
<pre>var arr = ["George","John","Thomas"];
console.log(arr.pop());     //"Thomas"
console.log(arr);           //["George", "John"]
</pre>
5、push() 方法可向数组的末尾添加一个或多个元素，并返回新的长度。如：
<pre>var arr = ["George","John","Thomas"];
console.log(arr.push("tom"));   //4
console.log(arr);               //["George", "John", "Thomas", "tom"]
</pre>
6、reverse() 方法用于颠倒数组中元素的顺序。如：
<pre>var arr = ["George","John","Thomas"];
console.log(arr.reverse());     //["tom", "Thomas", "John", "George"]
</pre>
7、shift() 方法用于把数组的第一个元素从其中删除，并返回第一个元素的值。(如果数组是空的，那么 shift() 方法将不进行任何操作，返回 undefined 值。请注意，该方法不创建新数组，而是直接修改原有的 arrayObject。)如：
<pre>var arr = ["George","John","Thomas"];
console.log(arr.shift());       //"tom"
</pre>
8、slice() 方法可从已有的数组中返回选定的元素。语法：arrayObject.slice(start,end)<br>
start	必需。规定从何处开始选取。如果是负数，那么它规定从数组尾部开始算起的位置。也就是说，-1 指最后一个元素，-2 指倒数第二个元素，以此类推。<br>
end	可选。规定从何处结束选取。该参数是数组片断结束处的数组下标。如果没有指定该参数，那么切分的数组包含从 start 到数组结束的所有元素。如果这个参数是负数，那么它规定的是从数组尾部开始算起的元素。
<pre>var arr = ["George","John","Thomas"];
console.log(arr.slice(1));   //["John", "George"]
console.log(arr.slice(0,2)); //["Thomas", "John"]
</pre>
9、sort() 方法用于对数组的元素进行排序。（对数组元素首字母或首数字排序）如：
<pre>var arr=["George","John","Thomas","James","Adrew","Martin"];
console.log(arr.sort());  //["Adrew", "George", "James", "John", "Martin", "Thomas"]
</pre>
<pre>对数字进行排序需借助函数
var arr=[10,5,40,25,1000,1];
function sortNumber(a,b){
  return a - b
}
console.log(arr.sort(sortNumber));   //[1, 5, 10, 25, 40, 1000]
</pre>
10、splice() 方法向/从数组中添加/删除项目，然后返回被删除的项目。如：
<pre>var arr=["George","John","Thomas","James","Adrew","Martin"];
//删除从 index 2 ("Thomas") 开始的三个元素，并添加一个新元素 ("William") 来替代被删除的元素
console.log(arr.splice(2,3,"William"));  //["Thomas", "James", "Adrew"]
console.log(arr);    //["George", "John", "William", "Martin"]
</pre>
11、toString() 方法可把数组转换为字符串，并返回结果。如：
<pre>var arr=["George","John","Thomas","James","Adrew","Martin"];
console.log(arr.toString());   //"George,John,Thomas,James,Adrew,Martin"
</pre>
12、toLocaleString() 把数组转换为本地字符串。如：
<pre>var arr=["George","John","Thomas","James","Adrew","Martin"];
console.log(arr.toLocaleString());   //"George,John,Thomas,James,Adrew,Martin"
</pre>
13、unshift() 方法可向数组的开头添加一个或更多元素，并返回新的长度。（注：unshift() 方法无法在 Internet Explorer 中正确地工作！）如：
<pre>var arr=["George","John","Thomas"];
console.log(arr.unshift("William"));    //4
console.log(arr);                       //["William", "George", "John", "Thomas"]
</pre>
14、valueOf() 方法返回 Array 对象的原始值。如：
<pre>var arr=["George","John","Thomas"];
console.log(arr.valueOf());  //["George","John","Thomas"]
</pre>