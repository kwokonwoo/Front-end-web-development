### Navigation Menu
```
<!DOCTYPE html>
<html lang="en">
<head>
<style>
    ul {
        list-style-type: none; /*去掉无序列表圆点 */
        margin: 0;
        padding: 0;
        overflow: hidden;
        background-color: #333;
    }
    li {
        float: left;
    }
    li a {
        display: inline-block; /*设置元素宽高padding*/
        color: white;
        text-align: center;
        padding: 14px 16px;
        text-decoration: none; /*去掉超链接自带下划线*/
    }
    li a:hover {
        background-color: #111; /*鼠标悬浮时颜色*/
    }

    .active {
        background-color: red;
    }
</style>
</head>
<body>
<ul>
    <li><a href="#home" class="active">Home</a></li>
    <li><a href="#news">News</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#about">About</a></li>
</ul>

</body>
</html>
```
效果如图：
![Navigation Menu](https://github.com/kwokonwoo/Front-end-web-development/tree/master/images/Navigation Menu.png)
