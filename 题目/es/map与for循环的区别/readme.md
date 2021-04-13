## for循环与forEach
1. 在固定长度且长度不需要计算的时候for循环效率高于forEach
2. forEach 只适用于集合或者数组遍历，它内部的原理是Iterator
3. forEach 相比于普通 for 循环的优势在于对稀疏数组的处理，会跳过数组中的empty空位

## forEach与map
1. map返回一个新的数组，数组中的元素为原始数组调用函数处理后的值。
2. map方法不会对空数组检测，map方法不会改变原始数组。forEach会有空数组检测，会改变会有数组
3. forEach和map方法里每次执行匿名函数都支持3个参数，参数分别是item（当前每一项），index（索引值），arr（原数组）

## 什么是空数组检测
比如[empty,empty]就是空数组。  
1. forEach遇到empty不会执行回调函数
2. map会执行
3. for循环会执行

## 性能对比
for > forEach > map
1. for 循环当然是最简单的，因为它没有任何额外的函数调用栈和上下文；  
2. forEach 其次，因为它其实比我们想象得要复杂一些，它的函数签名实际上是
```
array.forEach(function(currentValue, index, arr), thisValue)
```
它不是普通的 for 循环的语法糖，还有诸多参数和上下文需要在执行的时候考虑进来，这里可能拖慢性能；  
3. map 最慢，因为它的返回值是一个等长的全新的数组，数组创建和赋值产生的性能开销很大

## 参考
https://www.cnblogs.com/huangqiao/p/12190806.html  
如何从性能方面选择for，map和forEach？ - Starkwang的回答 - 知乎
https://www.zhihu.com/question/263645361/answer/271426852  