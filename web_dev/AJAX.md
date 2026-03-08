## AJAX概要
- AJAX = Asynchronous JavaScript and XML（异步的 JavaScript 和 XML）
- AJAX 最大的优点是在不重新加载整个页面的情况下，可以与服务器交换数据并更新部分网页内容。
<img width="798" height="502" alt="image" src="https://github.com/user-attachments/assets/2926cdb4-c30d-42f3-a918-b1f6d907734e" />

## XMLHttpRequest 对象
XMLHttpRequest 用于在后台与服务器交换数据
```html
var xmlhttp;
if (window.XMLHttpRequest) {
    //  IE7+, Firefox, Chrome, Opera, Safari 浏览器执行代码
    xmlhttp=new XMLHttpRequest();
} else {
    // IE6, IE5 浏览器执行代码
    xmlhttp=new ActiveXObject("Microsoft.XMLHTTP");
}
// example
// 创建 XMLHttpRequest 对象
var xhr = new XMLHttpRequest();

// 配置请求
xhr.open('GET', 'https://api.example.com/data', true);
// method：请求的类型；GET 或 POST
// url：文件在服务器上的位置
// async：true（异步）或 false（同步）

// 设置请求头（如果需要的话）
// xhr.setRequestHeader('Content-Type', 'application/json');

// 定义回调函数
xhr.onload = function () {
    if (xhr.status >= 200 && xhr.status < 300) {
        // 请求成功，处理响应
        console.log('Response:', xhr.responseText);
    } else {
        // 处理错误
        console.error('Error:', xhr.statusText);
    }
};

// 处理网络错误
xhr.onerror = function () {
    console.error('Request failed');
};

// 发送请求
xhr.send();
// send(string)：仅用于 POST 请求
```
## AJAX - 服务器 响应
```
// responseXML 属性
xmlDoc=xmlhttp.responseXML;
txt="";
x=xmlDoc.getElementsByTagName("ARTIST");
for (i=0;i<x.length;i++)
{
    txt=txt + x[i].childNodes[0].nodeValue + "<br>";
}
document.getElementById("myDiv").innerHTML=txt;

// responseText 属性/ 
document.getElementById("myDiv").innerHTML=xmlhttp.responseText;
```
