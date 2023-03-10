
## hexo theme
 https://ac-heron.github.io

### 我的修改：

1. 点击文章标题在当前页面打开
article.ejs 
去除<a target="blac

2. 去除文章页自动生成的目录
article.ejs
<!-- <%- toc(post.content, {"list_number":false}) %> -->

3. 样式调整,只对电脑端有效，手机端宽度正常显示
css/common.style:
```
 //margin: 5% 20% 5% 20%;//desktop version
  //width: 50%; // desktop version
  //>=768的设备
  @media (min-width: 768px){ 
    margin: 5% 20% 5% 20%;//desktop version
    width: 50%; // desktop version 
  }
```

4. 文章标题不用下划线：
css/common.style:
border-bottom: 0px 
```
a {
  text-decoration: none;
  cursor: crosshair;
  border-bottom: 0px dashed Red;
  padding: 1px;
  color: black;
}
```

5. 居右显示发布时间,并设置1989年的不显示，比如菜单栏read等页面
article.ejs:
```
<div class="article-category" style="text-align:right;">
<% if (date(post.date, 'YYYY') != '1989') { %>
<%- date(post.date, 'YYYY年M月D日') %>
<% } %>
```

6. 给表格中的链接加颜色
common.style
```
table td a, table th a {
  color: #428bca;
  text-decoration: none;
}
```

7. 引用的字体颜色修改

```
blockquote {
  color:#715959;
```

8.a链接添加颜色
common.styl:

```
a {
  text-decoration: none;
  cursor: crosshair;
  border-bottom: 0px dashed Red;
  padding: 1px;
  color: #428bca;
}
```

9. 图片缩小显示
common.styl
```
img {
  width: 50%;
}

```

10. 导航栏黑色
nav.ejs:
<nav class="navbar navbar-inverse


11. 导航栏横着展示
原先: <ul class="nav navbar-nav navbar-right">
```
<!-- Collect the nav links, forms, and other content for toggling -->
        <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
            <ul class="nav navbar-nav navbar-right">
            <%if(theme.menu){%>
                <%for(key in theme.menu){%>
                    <li <%if(key == 'Blog'){%> class="active" <%}%>>
                        <a href="<%- url_for(theme.menu[key])%>"> <%= key%></a>
                    </li>
                <%}%>
            <%}%>
            </ul>
        </div><!-- /.navbar-collapse -->
```
改为：
 <ul class="nav nav-tabs navbar-right">

12.js改为本地引入
afterfooter.ejs
<%- js('js/bootstrap.min.js')%>


13.更换favicon.ico
https://www.logosc.cn/logo/favicon?s=A
https://www.gaituba.com/favicon