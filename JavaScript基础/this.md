在JavaScript中，对象的定义是这样的：
```JavaScript
var xiaoming = {
    name: '小明',
    birth: 1990
};
```
接下来我们给```xiaoming```绑定一个函数，比如写个```age()```方法，返回```xiaoming```的年龄：
```JavaScript
var xiaoming = {
    name: '小明',
    birth: 1990,
    age: function() {
        var y = new Date().getFullYear();
        return y - this.birth;
    }
};

xiaoming.age; //function xiaoming.age()
xiaoming.age(); // 今年调用是25，明年调用就变成26了
```
在一个方法内部，```this```是一个特殊变量，它**始终指向当前对象**，也就是```xiaoming```这个变量。所以，```this.birth```可以拿到```xiaoming```的```birth```属性。
分开来写：
```javascript
function getAge() {
    var y = new Date().getFullYear();
    return y - this.birth;
}

var xiaoming = {
    name: '小明',
    birth: 1990,
    age: getAge
};

xiaoming.age(); // 30，正常结果
getAge(); // TypeError: Cannot read property 'birth' of undefined
```
以上打印的输出结果是因为如果以对象的方法形式调用，比如```xiaoming.age()```,该函数的```this```指向被调用的对象，也就是```xiaoming```，这是符合我们预期的。

如果单独调用函数，比如```getAge()```，此时，该函数的```this```指向全局对象，也就是```window```。
而且，即便是这样写：
```javascript
var fn = xiaoming.age;
fn();
```
仍然是行不通滴，要保证```this```指向正确，必须用```obj.xxx()```的形式调用！

由于这是一个巨大的设计错误，难以纠正。ECMA决定，在strict模式下让函数的```this```指向```undefined```，但这并没有解决```this```应该指向的正确位置。
#### apply
虽然在一个独立的函数调用中，根据是否是strict模式，```this```指向```undefined```或```window```，但我们还是可以控制```this```的指向的！

要指定函数的```this```指向哪个对象，可以用函数本身的```apply```方法，它接受两个参数，第一个参数是需要绑定的```this```变量，第二个参数是```Array```，表示函数本身的参数。
用```apply```修复```getAge()```调用：
```javascript
function getAge() {
    var y = new Date().getFullYear();
    return y - this.birth;
}

var xiaoming = {
    name: '小明',
    birth: 1990, 
    age: getAge
};

xiaoming.age(); // 25
getAge.apply(xiaoming, []); // 25, this指向xiaoming，参数为空
```
另一个与```apply()```类似的方法是```call()```，唯一区别是：
- ```apply()```把参数打包成```Array```再传入；
- ```call()```把参数按顺序传入。
比如调用```Math.max(3,5,4)```，分别用```apply()```和```call()```实现如下：
```javascript
Math.max.apply(null, [3, 5, 4]); // 5
Math.max.call(null, 3, 5, 4); // 5
```
举一个例子：
```javascript
var person1 = {
  fullName: function(){
    return this.firstName + " " + this.lastName; 
  }
}
var person2 = {
  firstName: "John",
  lastName: "Doe",
}
person1.fullName.call(person2); // Will return "John Doe"
```
对普通函数调用，我们通常把```this```绑定为```null```。

https://www.w3schools.com/js/js_this.asp

The JavaScript ```this``` keyword refers to **the object it belongs to**.
### this is a Method
```javascript
var person = {
  firstName: "John",
  lastName : "Doe",
  id       : 5566,
  fullName : function(){
    return this.firstName + " " + this.lastName;
  }
};
```
In an object method, ```this``` refers to the "owner" of the method. In the above example, ```this``` refers to the **person** object because the **person** object is the **owner** of the **fullName** method.

### this Alone
When used alone, the **owner** is the Global object, so ```this``` refers to the Global object.

In a browser window the Global object is [object Window](also in strict mode).
### this in a Function (Default)
In a JavaScript function, the owner of the function is the **default** binding for ```this```.
So, in a function, ```this``` refers to the Global object [object Window]. However, JavaScript **strict mode** does not allow default binding. So, ```this``` is ```undefined``` when used in a function in strict mode.
