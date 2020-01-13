
### @media + rem + less 的使用

#### less安装
```
npm install -g less
```
#### 命令行使用
 ```
 lessc styles.less
 
 lessc styles.less styles.css
 
 lessc --clean-css styles.less styles.min.css
 
 ```
 
##### 定义变量、属性值为变量 使用@
```
@color: #fff000; 
.link {
    color: @color;
}

// 编译后：
.link {
    color: #fff000;
}
```
##### 变量插值（选择器、属性名、属性值；选择器、属性名中、部分片段中：必须使用插值语句） 使用 @{}
```
@mySelector: banner;
.@{mySelector} {
  font-weight: bold;
}

// 编译后：
.banner {
    font-weight: bold;
}

@property: color;
.widget {
    @{property}: #0ee;
    background-@{property}: #999;
}

// 编译后：
.widget {
    color: #0ee;
    background-color: #999;
}

@images: "../img";
body {
  color: #444;
  background: url("@{images}/white-sand.png");
}

// 被编译为：
body {
  color: #444;
  background: url("../img/white-sand.png");
}
```

