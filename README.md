# study-ast

# AST 抽象语法树

## 抽象语法树和虚拟节点的关系

h 函数就是渲染函数,它既是 AST 的产物,也是 vnode 的起源

## cache 思想(缓存)

## 递归

小技巧 : 只要出现了`规则复现`,就要想到用`递归`

## 栈 stack

`词法分析的时候,经常要用到栈这个数据结构`

`3[2[a]2[b]]`
遍历每一个字符:
如果这个字符是数字,那么就把数字压栈,把空字符串压栈
如果这个字符是字母,那么此时就把栈顶这项改为这个字母
如果这个字符是],那么就将数字弹栈,就把字符串栈的栈顶的元素重复刚刚的这个次数,弹栈,拼接到新栈顶上

## 正则表达式

①`replace`
`'abc333def'.replace(/\d/g,'')`=>`abcdef`删除数字
②`search`
`'abc333def'.search(/\d/)`=>`3`寻找第一个数字的位置
③`match`
`'abc333def'.match(/\d/g)`=>`['3','3','3']`
④`test`
`/^\d/.test('2abc')`=>`true`是否已数字开头

`search()`方法加 g 修饰符没有用
`match()`方法加 g 非常好用,能够寻找到所有匹配的字符
