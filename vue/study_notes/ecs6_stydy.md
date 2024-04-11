## 关于ECS6规范

[参考来源](https://www.dengruicode.com/classes?uuid=04682448c47b45e980e57d476918d740)

1.0 关于函数的花式写法...

>nomal: 关键字-函数名-()-{}

- function name(){

}

> high: 一种计算赋值： 变量赋值-关键字-括号-花括号

- let a = funtion(){

}

> higher: 括号-箭头-花括号

- let a = () => {

}

> highest： 括号-箭头-表达式

- let a = () => 表达式

1.1 函数的几种方式

- 空函数 参数函数 默认值参数函数

- 匿名函数 箭头函数 隐式返回函数

2.0 数组

- 数组的方法：

    - push pop unshift shift sort adverse splice(start,length)  filter( ()=> {} ) concat

- 循环
    
    - for each ((value, index) => {})
    - for(let item of arry) {} 

- for of & for in 

    - for...of循环主要用于遍历可迭代对象（包括Array，Map，Set，String，TypedArray，函数的 arguments 对象等等）的值。for...in循环主要用于遍历对象的可枚举属性，包括数组或对象的索引（键名）。
    - for...of循环返回的是迭代器产生的值，即遍历的是对象的值。for...in循环返回的是对象自身的属性名，且包括原型链上的可枚举属性。这意味着它不仅会遍历对象自身的属性，还会遍历其原型链上的属性。

        - example:
        
        - const arr = ['a', 'b', 'c'];  
        for (const index in arr) {  
 console.log(arr[index]); // 输出 'a', 'b', 'c'  
}

        - const arr = ['a', 'b', 'c'];  
for (const value of arr) {  
 console.log(value); // 输出 'a', 'b', 'c'

 3.0 set集合

 - 方法：

    - add delete  size has('attribute') clear  Array.from(set)  [...set]

    - for [let item of fruits]{}

    - foreach(value=> {})

    -  去重 new set(arry)


4.0 map

- 构建

    - 创建时构建

        - const myMap = new Map([  
  ['key1', 'value1'],  
  ['key2', 'value2'],  
  [1, 'numberValue']  
]);

    - 创建后设置

        - const myMap = new Map();  
myMap.set('key1', 'value1');  
myMap.set('key2', 'value2');

    - 其他转化

        - const iterable = new Set([  
  ['key1', 'value1'],  
  ['key2', 'value2']  
]);  
const mapFromIterable = new Map(iterable); //set转化

        - const obj = {  
  key1: 'value1',  
  key2: 'value2'  
};  
  
const mapFromObject = new Map(Object.entries(obj)); //对象转化

- 方法

    - set('', '') delete('') has('') size  [...map] clear

    - for (let [key, value] of map){      
    }

    - map.foreach((value, key) => {key, value })

5.0 对象obj

操作：

- obj.attrbute = * ; delete obj.attribute ; let has =  'attribute' in obj ; person = {}

-  Object.keys(person) Object.keys(person).length //获取对象属性名的数组、数组内属性的数量

- Object.entries(person)  // 对象转换为数组

```
 //将对象转换为数组
    let arr = Object.entries(person) //Object.entries() 用于获取对象的键值对数组
    console.log("arr", arr)

    //使用for...in循环遍历对象 
    //for...of 用于遍历可迭代对象[如数组、Set、Map、字符串等]
    //for...in 用于遍历对象的可枚举属性
    for (let key in person) {
        console.log("for...in", key, person[key])
    }

    //使用forEach方法遍历对象的属性和值
    Object.entries(person).forEach(([key, value]) => {
        console.log("forEach", key, value)
    })

```
6.0 类、继承、模板字符串、解构

类：

 class ClassName{
    constructor(){

        this.name =name
        this.gender = gender
    }

    method(){

    }
}

let class = new Classname()

继承：

class Son extens Parent{

    constructor(,,,){
        super(,)       //调用父类构造函数 // 参数与父级相同
        this.sonAttribute = sonAttribute
    }
    sonMethod(){

    }
} 

模板字符串：

    `${变量}`

结构：

let [A, ...B] = [1, 2, 3, 4, 5, 6]

let { name: userName, gender, web } = person

//两数交换

let x3 = 10

let y3 = 20; //不加分号会报错

[x3, y3] = [y3, x3]

//扩展运算符

let [, , c] = [10, 20, 30]

console.log("c:", c)

6.0字符串

方法

- length; toLowerCase(); toUpCase();  [...str]; parseInt(""); replace('',''); replaceAll('',''); trim(); includes(''); indexOf(''); startWith(''); endWith('');  split(',')

7.0 Promise & axios


promise定义：

    - let promise =new Promise((resolve, reject) =>{})

promise使用：

    成功1
    - let promise = new Promise((resolve, reject) =>{
        resolve('success')
    })
      promise.then(result=>{
        console.log("result: result) 
      })
    失败2
     let promise = new Promise((resolve, reject) => {
                reject("邮件发送失败") //异步执行失败
            })
     promise.catch(error =>{
        console.log('error', error)
     })  

    综合：
        let promise = new Promise((resolve, reject) =>{
            resolve('success')   //
            or 
            reject('fail')  //
        }).then(result=>{
            console.log('result',result)
        }).catch(error =>{
            concole.log('error', error)
        }).finnaly(()=>{
            console.log('执行结束‘)
        })

Axios:

    /*
        Axios 是基于 Promise 的网络请求库, 它可以发送http请求并接收服务器返回的响应数据
        Axios 返回的是一个 Promise 对象

        Axios 不仅可以用于浏览器, 也可以用于 Node.js, 而 Fetch 主要用于浏览器
    */

    //get请求
    axios.get('http://127.0.0.1/get').then(response => {
        console.log("get.data:", response.data)
    }).catch(error => {
        console.log("get.error:", error)
    }).finally(() => {
        console.log("get.finally")
    })

    //post请求 post
    let data = { //参数
        name: '邓瑞',
        web: 'dengruicode.com',
    }

    axios.post('http://127.0.0.1/post', data, {
        headers: {
            'Content-Type': 'application/x-www-form-urlencoded'
        }
    }).then(response => {
        console.log("post.data:", response.data)
    }).catch(error => {
        console.log("post.error:", error)
    }).finally(() => {
        console.log("post.finally")
    })

    //post请求 postJson [axios 的默认请求头是 application/json]
    axios.post('http://127.0.0.1/postJson', data).then(response => {
        console.log("postJson.data:", response.data)
    }).catch(error => {
        console.log("postJson.error:", error)
    }).finally(() => {
        console.log("postJson.finally")
    })