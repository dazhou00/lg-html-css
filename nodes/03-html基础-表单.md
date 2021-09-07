# 表单

## 表单组成

- HTML 表单用于搜集不同类型的用户输入，表单元素就是网页中提供用户进行输入或点击 的小控件。
- 在 HTML 中，一个完整的表单通常由表单域、提示信息和表单控件（也称为表单元素）3 个 部分构成。

### 功能

- 表单域：相当于一个容器，用来容纳所有的表单控件和提示信息，可以通过它定义处理表单数据所用程序的 url 地址，以及数据提交到服务器的方法，如果不定义表单域，表单中的数据就无法传送到后台服务器
- 提示控件：一个表单通常还需要一些说明性的文字，提示用户进行填写和操作
- 表单控件，包含了具体的表单功能项，如单行文本输入框、密码框、复选框、提交和重置按钮等

## 表单域标签

- HTML 表单域使用`<form>` 标签进行定义
- form 标签是一个功能性标签，填写的表单信息要想正确的提交到后台服务器，必须放在一个 form 标签之内
- form 标签为双标签，容器级标签

### 属性

- form 标签通过对应属性 规定提交数据的方法和提交位置

| 属性名 | 属性值     | 描述                                          |
| ------ | ---------- | --------------------------------------------- |
| action | url        | 指定接收并处理表单数据的服务器程序的 url 地址 |
| method | get/post   | 设置表单数据提交方式                          |
| name   | 自定义名称 | 规定表单的名称                                |

```html
<form action="index.php" method="post/get" name="message">
  提示信息及表单控件书写的位置
</form>
```

## 表单元素

### input 标签

- input 标签是最重要的一个表达元素
- input 标签为单标签，本身相当于一个特殊的文本
- input 需要通过标签属性实现各种功能

<table>
  <tr><td>属性名</td><td>属性值</td><td>说明</td></tr>
  <tr><td rowspan='10'>type</td><td>text</td><td>单行文本输入框</td></tr>
  <tr><td>password</td><td>密码输入框</td></tr>
  <tr><td>radio</td><td>单选框</td></tr>
  <tr><td>checkbox</td><td>复选框</td></tr>
  <tr><td>botton</td><td>普通按钮</td></tr>
  <tr><td>reset</td><td>重置按钮</td></tr>
  <tr><td>submit</td><td>提交按钮</td></tr>
  <tr><td>image</td><td>图片形式的按钮</td></tr>
  <tr><td>file</td><td>定义输入字段和“浏览”按钮，供文件上传</td></tr>
  <tr><td>hidden</td><td>定义隐藏的输入字段</td></tr>
  <tr><td>name</td><td>自定义</td><td>定义控件的名称</td>
  <tr><td>value</td><td>自定义</td><td>定义控件的默认文本</td>
  <tr><td>size</td><td>数字</td><td>定义控件的宽度</td>
  <tr><td>checked</td><td>checked</td><td>定义选框控件的默认被选中项</td>
  <tr><td>maxlength</td><td>数字</td><td>定义允许输入的最多字符数</td>
</table>

### 文本域

- 文本域使用 `<textarea>` 标签定义，制作可以输入多行文本的区域
- textarea 标签为双标签，本身相当于一个特殊文字
- 文本域可以设置默认输入的文字，在双标签之间竖线默认文字

#### 属性

- rows: 行，属性值是数字，数字是几表示文本框显示的最大行数，如果超过了行数，会被隐藏并且出现滚动条
- cols: 列，属性值是数字，数字是几，表示出现滚动条之后，每一行显示的最大字节数（一个汉字按两个字节计算）

```html
<textarea cols="30" rows="10">默认输入文字</textarea>
```

### 下拉菜单

HTML 中的下拉菜单提前设置一些选项，然后可以通过点击选择其中一项

- 下拉菜单需要至少两个标签完成结构
  - select：选择，表示定义下拉菜单整体结构
  - option：选项，表示定义下拉菜单的每一项
  - 两个标签都是双标签，文本级标签
  - `select>options`, option 可以有任意多项

```html
<select>
  <option>选项一</option>
  <option>选项二</option>
  <option>选项三</option>
</select>
```

- 默认情况下，选中的是第一项
- 下拉菜单可以通过给 option 标签设置 selected 属性，属性值为 selected, 更改默认选中项

```html
<option selected="selected">选项二</option>
```

#### 分组管理

- 下拉菜单如果选项变得复杂，可以将 option 进行分组管理
- 可以使用 optgroup 标签对选项进行分组，optgroup 是一个双标签
- `select>optgroup>option`
- optgroup 可以设置一个 label 属性，表示给这一组选项添加一个分组标签名，分组标签 optgroup 是不能被点击选择的

```html
<select>
  <optgroup label="分组一">
    <option>选项一</option>
    <option>选项二</option>
  </optgroup>
  <optgroup label="分组二">
    <option>选项一</option>
    <option>选项二</option>
  </optgroup>
</select>
```

### label 标签

所有的表单元素都可以通过绑定其他内容去扩大 触发点击范围，这时需要使用一个`<label>`标签。

- label 标签的作用是帮表单元素定义标注（标记）
- 如果将表单控件与内容使用 label 进行绑定后，当用户鼠标点击 label 内的提示内容时，浏览器就会自动将焦点转到和标签相关的表单控件上

#### 绑定方法一

1. 给表单元素设置 id 属性
2. 将需要绑定的其他内容用 label 标签包裹
3. 给 label 标签设置 for 属性，属性值为绑定的表单元素的 id 属性值

```html
<input type="checkbox" name="hobby" id="sport" /> <label for="sport"></label>
```

#### 绑定方法二

- 如果绑定内容和表单元素写在一起，可以简化绑定写法
- 直接使用 label 标签将绑定内容与表单元素一起进行嵌套

```html
<label><input type="radio" name="sex" />单选</label>
```
