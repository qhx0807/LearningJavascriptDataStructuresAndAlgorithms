####  Array 总结

* 方法

```javascript
// 会改变自身
copyWithin()
fill()
pop()
push()
reverse()
shift()
unshift()
splice()

// 不会改变自己 返回一个新的数组或者返回一个其它的期望值。
concat()
includes()
indexOf()
lastIndexOf()
silce()
toLocalString()
toSource()
toString()
values()
join()

// 遍历方法
every()
filter()
entries()
find()
findIndex()
flat()
flatMap()
forEach()
keys()
map()
reduce()
reduceRight()
some()

Array​.isArray()
Array​.from()
Array​.length

```
* 重点

##### `entries()`

方法返回一个新的Array Iterator对象，该对象包含数组中每个索引的键/值对

`let iterator1 = arr1.entries()`

##### `flat()`

会按照一个可指定的深度递归遍历数组，将所有元素与遍历到的子数组中的元素合并为一个新数组返回。

```javascript
var arr = [1, 2, [3, 4]]
arr.flat()
// => [1, 2, 3, 4]
// 可以使用 `Infinity` 作为参数
// arr3.flat(); 

// 替代方案
// 1层
const flatSingle = arr => [].concat(...arr)
// 多层
function flattenDeep(arr1) {
  return arr1.reduce((acc, val) => Array.isArray(val) ? acc.concat(flattenDeep(val)) : acc.concat(val), [])
}
```

#### `flatMap()`

```javascript
let arr = ["今天天气不错", "", "早上好"]

arr.map(s => s.split(""))
// [["今", "天", "天", "气", "不", "错"],[""],["早", "上", "好"]]

arr.flatMap(s => s.split(''));
// ["今", "天", "天", "气", "不", "错", "", "早", "上", "好"]
```

#### `reduce()` [reduce](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce)

`reduce(acc, cur, index, arr)` 接受4个参数

`acc` 累计器, `cur` 当前值, `index` 当前索引, `arr` 源数组

#### es6 结构

```javascript
let [a, b] = [1, 2, 3]

// 利用解构 可快速生成斐波拉契数列
// 获得 n 以内的斐波拉契数
const fib = (n) => {
  let [a, b] = [0, 1]
  while (a < n) {
    [a, b] = [b, b + a]
    console.log(a)
  }
}
```

