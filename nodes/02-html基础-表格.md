# 表格

## 基础

- 创建一个简单的表格至少由三个标签组成
  - table: 表格，定义的是整个的表格大结构
  - tr: table rows，表格的行，定义的是表格由多少行组成
  - td: table data，表格数据，也叫表格单元格，定义的是每一行内部的单元格
- 三者关系：`table>tr>td`，一个表格中有多行，每行中有多个单元格

### table 的属性

- `<table>`标签可以添加 border 边框属性。
  - 属性值：数字，表示像素值。
- 表格的单元格之间有默认的空隙，会导致双线边框。
  - 解决方法：设置标签样式属性 style。
  - 属性值：border-collapse : collapse; 表示边框塌陷。

### 表头单元格

- 如果要绘制表头，使用标签`<th>`，table head data, 表头单元格
- 在表格中绘制的时候，替换的是 `<td>` 的位置
- `<th>` 标签中自带默认的 css 样式效果，文字显示粗体居中

## 合并单元格

常见的表格操作中，有一种叫做合并单 元格，可以通过单元格属性进行设置

### 单元格属性

- 表格的单元格可以进行合并，通过`<th>`和`<td>` 的两个属性可以进行合并设置
- rowspan: 跨行合并，上下的合并
- colspan: 跨列合并，左右的合并
- 属性值：数字，数字是几表示跨几行或几列合并

### 制作技巧

1. 线列出所有行`<tr>`，以最小单元格为标准
2. 在添加每一行的 td 或 th 单元格
3. 划分单元格所在行时，顶边对齐的属于同一行
4. 在所有行和列写完后，在查看哪些单元格有跨行或跨列，属性值的个数要参考最小的单元格

## 表格区分

一个完整的表格分为四个大的区域：表格标题、表格头部、表格主体、表格页脚

### 分区标签

- table: 内部最直接的子级包含四个分区标签
  - caption: 表格的标题，内部书写标题文字
  - thead: table head, 表格头部，内部嵌套 `tr>th`
  - tbody: table body, 表格的主体，内部嵌套 `tr>td`
  - tfoot: table foot, 表格的页脚，内部嵌套 `tr>td`
- 四个分区选择性的进行组合
- 注意：不论书写的顺序如何颠倒，浏览器中的加载顺序都是自动按照 caption、thead、tbody、tfoot 执行的

### 制作技巧

1. 先书写大分区标签结构
2. 填充每个分区的内部内容
3. 如果有合并单元格内容，进行单元格合并
