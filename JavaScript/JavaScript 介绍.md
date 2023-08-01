
## JavaScript 介绍

### 引入方式

单独的JavaScript文件无法运行，必须与HTML文件联系才能运行

#### 内部形式

- 行内式
- 内联式：通过\<script> \</script>标签包裹起来，写在\</body>之前

#### 外部形式

将JavaScript写在以.js结尾的文件中，通过\<script>标签的src属性引入。

**注**：外部引入形式的\<script>标签内不能写入代码，否则代码不生效

### 注释和结束符

#### 注释

##### 单行注释

单行注释使用"//"
快捷键：crtl + /

##### 多行注释

多行注释使用"/\* \*/"
快捷键：shift + Alt + A

#### 结束符

JavaScript使用`Enter`或`;`为一行代码的结束符

### 输入和输出

#### 输入

可以使用promt()获取用户输入

#### 输出

- document.write() 将内容写到 HTML 文档中
- console.log() 在控制台输出
- alert() 弹出窗口显示

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>JavaScript 基础 - 输入输出</title>
</head>
<body>
  
  <script> 
    // 1. 输入的任意数字，都会以弹窗形式展示
    document.write('要输出的内容')
    alert('要输出的内容')
    console.log('要输出的内容')

    // 2. 以弹窗形式提示用户输入姓名，注意这里的文字使用英文的引号
    prompt('请输入您的姓名:')
  </script>
</body>
</html>
```

## 类型转换

### 显式转换

### 隐式转换