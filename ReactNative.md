# React 编码规范

RN项目的目录结构
```
.
├── README.md  -------------------------------------------------- 工程相关说明文件
├── __tests__  -------------------------------------------------- 测试用例相关文件
│   ├── index.android.js ---------------------------------------- RN-Android测试用例入口文件
│   └── index.ios.js -------------------------------------------- RN-iOS测试用例入口文件
├── android          -------------------------------------------- Android原生工程
│   ├── app
│   │   ├── BUCK
│   │   ├── build
│   │   │   ├── intermediates
│   │   │   │   │   ├── compileDebugAidl
│   │   │   │   │   │   └── dependency.store
│   │   │   │   │   ├── mergeDebugAssets
│   │   │   │   │   │   └── merger.xml
│   │   │   │   │   ├── mergeDebugJniLibFolders
│   │   │   │   │   │   └── merger.xml
│   │   │   │   │   ├── mergeDebugResources
│   │   │   │   │   ├── packageDebug
│   │   │   │   │   │   ├── dex-renamer-state.txt
│   │   │   │   │   │   ├── file-input-save-data.txt
│   │   │   │   │   │   └── zip-cache
│   │   │   │   │   │       └── PzrhxNJY9uJjLWIBu3gBJuVHS2Q=
│   │   │   │   │   ├── packageDebugAndroidTest
│   │   │   │   │   │   └── zip-cache
│   │   │   │   │   ├── packageRelease
│   │   │   │   │   │   └── zip-cache
│   │   │   │   │   └── processDebugResources
│   │   │   │   │       └── aapt-temp
│   │   │   │   ├── incremental-safeguard
│   │   │   │   │   └── debug
│   │   │   │   │       └── tag.txt
│   │   │   │   ├── jniLibs
│   │   │   │   │   └── debug
│   │   │   │   ├── manifests
│   │   │   │   │   ├── full
│   │   │   │   │   │   └── debug
│   │   │   │   │   │       └── AndroidManifest.xml
│   │   │   │   │   └── instant-run
│   │   │   │   │       └── debug
│   │   │   │   ├── pre-dexed
│   │   │   │   │   └── debug
│   │   │   │   ├── res
│   │   │   │   │   ├── merged
│   │   │   │   │   │   └── debug
│   │   │   ├── outputs
│   │   │   │   ├── apk
│   │   │   │   │   └── app-debug.apk
│   │   │   │   └── logs
│   │   │   │       └── manifest-merger-debug-report.txt
│   │   │   └── tmp
│   │   │       └── compileDebugJavaWithJavac
│   │   │           └── emptySourcePathRef
│   │   ├── build.gradle
│   │   ├── proguard-rules.pro
│   │   └── src
│   │       └── main
│   │           ├── AndroidManifest.xml
│   │           ├── java
│   │           │   └── com
│   │           │       └── acmp
│   │           │           ├── MainActivity.java
│   │           │           └── MainApplication.java
│   │           └── res
│   │               ├── mipmap-hdpi
│   │               │   └── ic_launcher.png
│   │               ├── mipmap-mdpi
│   │               │   └── ic_launcher.png
│   │               ├── mipmap-xhdpi
│   │               │   └── ic_launcher.png
│   │               ├── mipmap-xxhdpi
│   │               │   └── ic_launcher.png
│   │               └── values
│   │                   ├── strings.xml
│   │                   └── styles.xml
│   ├── build.gradle
│   ├── gradle
│   │   └── wrapper
│   │       ├── gradle-wrapper.jar
│   │       └── gradle-wrapper.properties
│   ├── gradle.properties
│   ├── gradlew
│   ├── gradlew.bat
│   ├── keystores
│   │   ├── BUCK
│   │   └── debug.keystore.properties
│   ├── local.properties
│   └── settings.gradle
├── app -----------------------------------------------------  存放开发编写的ReactNative代码总文件夹
│   ├── actions ------------------------------   Reducer actions文件夹
│   │   ├── root.js
│   │   └── user.js
│   ├── components ---------------------------  自定义组件文件夹
│   │   └── TitleView.js
│   ├── containers --------------------------- 容器文件夹
│   │   └── user.js
│   ├── img ---------------------------------- ReactNative 存放图片文件夹
│   │   ├── home
│   ├── middlewares -------------------------- 中间件文件夹
│   │   └── root.js
│   ├── pages ------------------------------- 存放页面代码文件夹（各个模块的页面）
│   │   ├── contact
│   │   │   ├── index.js
│   │   │   └── styles.js
│   │   ├── find
│   │   │   ├── index.js
│   │   │   └── styles.js
│   │   ├── home
│   │   │   ├── common
│   │   │   │   └── review.js
│   │   │   ├── index.js
│   │   │   ├── payment
│   │   │   │   ├── index.js
│   │   │   │   ├── salaryReviewRecord.js
│   │   │   │   └── style.js
│   │   │   └── styles.js
│   │   ├── root.js
│   │   ├── setup
│   │   │   ├── index.js
│   │   │   └── styles.js
│   │   └── user
│   │       ├── index.js
│   │       └── styles.js
│   ├── reducers ----------------------------- Reducer 代码文件夹
│   │   ├── root.js
│   │   └── user.js
│   ├── root.js ------------------------------ ReactNative 二级入口
│   ├── store -------------------------------- Reducer Store代码文件夹
│   │   ├── appContainer.js
│   │   └── createStore.js
│   └── utils --------------------------------- 自定工具类代码文件夹
├── index.android.js --------------------------------------------- ReactNative Android总入口文件
├── index.ios.js ------------------------------------------------- ReactNative iOS总入口文件
├── ios ---------------------------------------------------------- iOS原生工程
│   ├── acmp
│   │   ├── AppDelegate.h
│   │   ├── AppDelegate.m
│   │   ├── Base.lproj
│   │   │   └── LaunchScreen.xib
│   │   ├── Images.xcassets
│   │   │   └── AppIcon.appiconset
│   │   │       └── Contents.json
│   │   ├── Info.plist
│   │   └── main.m
│   ├── acmp-tvOS
│   │   └── Info.plist
│   ├── acmp-tvOSTests
│   │   └── Info.plist
│   ├── acmp.xcodeproj
│   │   ├── project.pbxproj
│   │   └── xcshareddata
│   │       └── xcschemes
│   │           ├── acmp-tvOS.xcscheme
│   │           └── acmp.xcscheme
│   └── acmpTests
│       ├── Info.plist
│       └── acmpTests.m
├── jsconfig.json
├── log
├── node_modules ----------------------------------------------------- react依赖文件 
├── package.json ----------------------------------------------------- React npm包依赖文件
```

文件与组件命名
- 扩展名: 使用.js作为js文件的扩展名。如果同一个文件夹下有同名而不同作用的js文件，则通过中缀（小写）进一步区分，例如：HomePageView.component.js, HomePageView.style.js, HomePageView.action.js等
- 文件名: 使用驼峰命名法且首字母大写，如HomePageView.js
- 组件命名: 与文件名（除中缀外）完全一致。如果组件单独放置在目录中，则目录名也一致

###### 组件声明

- 使用class与extends关键字。不使用React.createClass方法。需要导出的组件直接在class关键字前使用export default。

推荐

```jsx
export default class HomePageView extends Component { }
```

不推荐

```jsx
export default React.createClass({ });
```

##### 对齐

- 按下面的案列对齐

推荐

```jsx
<Foo superLongParam="bar"
     anotherSuperLongParam="baz" /> 
```

不推荐

```jsx
<Foo superLongParam="bar"
            anotherSuperLongParam="baz" /> 
```

**如果一行能放下props，那就放在一行，不需要换行**

**子组件照常缩进**

```jsx
<Foo
   superLongParam="bar"
   anotherSuperLongParam="baz"
> 
   <Spazz />
</Foo>
```

##### 引号

- 对于JSX的字符串属性使用双引号(")，其他情况下使用单引号。

推荐

```jsx
 <Foo bar="bar" /> 
```

不推荐

```jsx
<Foo bar='bar' />
```

推荐

```jsx
<Foo style={{ left: '20px' }} />
```

不推荐

```jsx
<Foo style={{ left: "20px" }} />
```

##### 空格

- 在自闭合的标签中包含一个空格。

推荐

```jsx
<Foo />
```

不推荐

```jsx
<Foo/> 
<Foo                 /> 
<Foo  /> 
```

##### state/props

- 对于多个单词组成的pros，使用驼峰命名法。不使用下划线或连接线。

推荐

```jsx
<Foo
   userName="hello"
   phoneNumber={12345678}
/>
```

不推荐

```jsx
<Foo
   UserName="hello"
   phone_number={12345678}
/>
```

- 读取state和props时，使用const与解构，必要时可使用let。不使用var。

推荐

```jsx
const { userName, age, sex } = this.props;
const { checked } = this.state;
```

不推荐

```jsx
var userName = this.props.userName;
let checked = this.state.checked; 
```

##### 括号

- 当JSX标签超过一行时，使用括号包裹。

推荐

```jsx
render() {
   return (
            <MyComponent className="long body" foo="bar">
           <MyChild />
            </MyComponent>
   );
} 
```

不推荐

```jsx
render() {
   return <MyComponent className="long body" foo="bar">
            <MyChild />
      </MyComponent>;
} 
```

**good, when single line**

推荐

```jsx
render() {
   const body = <div>hello</div>;
   return <MyComponent>{body}</MyComponent>;
}
```

##### 标签

- 对于没有子组件的JSX标签，始终自闭合。

推荐

```jsx
<Foo className="stuff" />
```

不推荐

```jsx
<Foo className="stuff"></Foo>
```

- 如果组件有多行属性，则另起一行进行自闭合。

推荐

```jsx
<Foo
   bar="bar"
   baz="baz"
/>
```

不推荐

```jsx
<Foo
   bar="bar"
   baz="baz" /> 
```

##### 方法

- 为方法命名时，不使用下划线开头（哪怕是想用作私有方法）。

推荐

```jsx
class extends React.Component {
   onClickSubmit() {
        // do stuff
    }
    // other stuff
});
```

不推荐

```jsx
React.createClass({
   _onClickSubmit() {
        // do stuff
   }
    // other stuff
}); 
```

ES6代码规范
======================

##### 变量与常量声明

- 变量与常量声明
    + 尽量使用let来代替var
    +  对于全局变量声明，采用global.xxx = xxx，但应避免声明过多全局变量污染环境
-  常量
    +  对于常量应使用const进行声明，命名采用驼峰写法
    +   对于使用 immutable 数据应用const进行声明

推荐

```jsx
 const someNum = 123;
 const anotherStr = '不变的字符串';
 const arr = ['不', '变', '数', '组'];
 const anotherObj = {   '不变对象': true };
```

不推荐

```jsx
 let someNum = 123;
  const AnotherStr = '不变的字符串';
  let arr = ['不', '变', '数', '组'];
  var ANOTHER_OBJ = {   '不变对象': true };
```

字符串

-  处理多行字符串,使用模板字符串
以反引号( ` )标示

可读性更强，代码更易编写

注意排版引起空格的问题，使用场景为声明HTML模板字符串

推荐

```jsx
const tmpl = ` <div class="content">   <h1>这是换行了。</h1> </div>`;

function sayHi(name) {
    return `How are you, ${name}?`;
}

```

- 处理字符串拼接变量时,使用模板字符串 
不推荐

```jsx
const tmpl = '<div class="content"> \n' +
'<h1>这是换行了。</h1> \n' +
                  '</div>';  

function sayHi(name) {
    return 'How are you, ' + name + '?';  
} 
```


##### 解构

- 解构语句中不使用圆括号

推荐

```jsx
let [a, b] = [11, 22];
```

不推荐

```jsx
[(a)] = [11]; // a未定义
let { a: (b) } = {}; // 解析出错  
```

- 对象解构

对象解构 元素与顺序无关

对象指定默认值时仅对恒等于undefined ( !== null ) 的情况生效

- 若函数形参为对象时，使用对象解构赋值

推荐

```jsx
function someFun(opt) {
   let { opt1, opt2 } = opt;
   console.log(`$(opt1) 加上 $(opt2)`);
} 
function someFun({ opt1, opt2 }) {
   console.log(opt1);
}
```

不推荐

```jsx
function someFun(opt) {
   let opt1 = opt.opt1;
   let opt2 = opt.opt2;
   console.log(op1);
 }
```

- 若函数有多个返回值时，使用对象解构，不使用数组解构，避免添加顺序的问题

推荐

```jsx
function anotherFun() {
   const one = 1, two = 2, three = 3;
   return { one, two, three };
}
const { one, three, two } = anotherFun(); // 不用管顺序
// one = 1, two = 2, three = 3
```

不推荐

```jsx
function anotherFun() {
   const one = 1, two = 2, three = 3;
   return [one, two, three];
 }
const [one, three, two] = anotherFun(); // 顺序乱了
 // one = 1, two = 3, three = 2  
```

- 已声明的变量不能用于解构赋值（语法错误）
<!-- 语法错误 -->

不推荐

```jsx
let a; { a } = { b: 123};
```

- 数组解构
    + 数组元素与顺序相关
- 交换变量的值

```jsx
let x = 1; let y = 2; 
// 不好
let temp;
temp = x;
x = y;
y = temp;  
// 好
[x, y] = [y, x]; // 交换变量
```

- 将数组成员赋值给变量时，使用数组解构

```jsx
const arr = [1, 2, 3, 4, 5]; 
// 不好
const one = arr[0];
const two = arr[1];  
// 好
const [one, two] = arr;
```

##### 数组

- 将类数组(array-like)对象与可遍历对象(如Set, Map)转为真正数组

采用Array.from进行转换

```jsx
// 不好
    function foo() {
       let args = Array.prototype.slice.call(arguments);
    }  
   // 好
   function foo() {
      let args = Array.from(arguments);
   }
```

- 数组去重

结合Set结构与Array.from

使用indexOf，HashTable等形式，不够简洁清晰

```jsx
// 好
function deduplication(arr) {
   return Array.from(new Set(arr));
}
```

- 数组拷贝
采用数组扩展...形式

```jsx
const items = [1, 2, 3]; 
// 不好
const len = items.length;
let copyTemp = [];
for (let i = 0; i < len; i++) {  
copyTemp[i] = items[i];
}  
// 好
let copyTemp = [...items];
```

- 将一组数值转为数组

采用Array.of进行转换

```jsx
// 不好
let arr1 = new Array(2); // [undefined x 2]
let arr2 = new Array(1, 2, 3); // [1, 2, 3]  
// 好
let arr1 = Array.of(2);  // [2]
let arr2 = Array.of(1, 2, 3); // [1, 2, 3]
```

##### 函数
- 当要用函数表达式或匿名函数时，使用箭头函数(Arrow Functions)
箭头函数更加简洁，并且绑定了this

```jsx
// 不好
const foo = function(x) {  
    console.log(foo.name); // 返回'' ，函数表达式默认省略name属性
}; 
[1, 2, 3].map(function(x) {  
    return x + 1;
}); 
var testObj = {  
    name: 'testObj',  
    init() {    
   var _this = this;
   // 保存定义时的this引用    
   document.addEventListener('click', function() {      
   return _this.doSth();    
   }, false);  
},  
doSth() {    
    console.log(this.name);  
    }
}; 
// 好
const foo = (x) => {  
    console.log(foo.name); // 返回'foo'
}; 
[1, 2, 3].map( (x) => {  
    return x + 1;
}); 
var testObj = {  
    name: 'testObj',  
    init() {    
        // 箭头函数自动绑定定义时所在的对象    
        document.addEventListener('click', () => this.doSth(), false);  
    },  
    doSth() {    
        console.log(this.name);  
    }
};

```

- 箭头函数书写约定

函数体只有单行语句时，允许写在同一行并去除花括号

当函数只有一个参数时，允许去除参数外层的括号

```jsx
// 好
const foo = x => x + x; // 注意此处会隐性return x + x 
const foo = (x) => {  
return x + x; // 若函数体有花括号语句块时须进行显性的return
};  
[1, 2, 3].map( x => x * x);
```

- 用箭头函数返回一个对象，应用括号包裹

```jsx
// 不好
let test = x => { x: x }; // 花括号会变成语句块，不表示对象  
// 好
let test = x => ({ x: x }); // 使用括号可正确return {x:x}
```

- 立即调用函数 IIFE

```jsx
// 不好
function foo(opts) {
   opts = opts || {};// 此处有将0，''等假值转换掉为默认值的副作用
}  
// 好
function foo(opts = {}) {
   console.log('更加简洁，安全');
}
```

-  对象中的函数方法使用缩写形式

更加简洁

函数方法不要使用箭头函数，避免this指向的混乱

```jsx
// 不好
const shopObj = {
   des: '对象模块写法',
   foo: function() {
     console.log(this.des);
   }
}; 
const shopObj = {
   des: '对象模块写法',
   foo: () => {
     console.log(this.des); // 此处会变成undefined.des，因为指向顶层模块的this  
}
}; 
// 好
const des = '对象模块写法'; // 使用对象属性值简写方式
const shopObj = {
   des,
   foo() {
console.log(this.des);
   }
 };

```

##### 类
- 类名应使用帕斯卡写法(PascalCased)

```jsx
// 好
class SomeClass {
  }
l        类名与花括号须保留一个空格间距
// 不好
class Foo{
   constructor(){
    // constructor
    }  
   sayHi()
    {
     // 仅保留一个空格间距
    }
}  
// 好
class Foo {
   constructor() {
    // constructor  
    }
  sayHi() {
  // 仅保留一个空格间距
  }
}

```

- 定义类时，方法的顺序如下：
    1. constructor
    2. public get/set 公用访问器，set只能传一个参数
    3.  methods 公用方法，公用相关命名使用小驼峰式写法(lowerCamelCase)
    4.  private get/set 私有访问器，私有相关命名应加上下划线 _ 为前缀
    5.  private methods 私有方法
```jsx
// 好
 class SomeClass {
   constructor() {
// constructor  
}
 get aval() {
     // public getter
   }
 set aval(val) {
     // public setter
   }   
doSth() {
     // 公用方法
   }
 get _aval() {
     // private getter
   }
 set _aval() {
     // private setter  
}   
_doSth() {
     // 私有方法
   }
}
```

- 如果不是class类，不使用new

```jsx
// 不好
 function Foo() {
  }
const foo = new Foo();  
// 好
class Foo {
  }
const foo = new Foo();
```

- 使用真正意思上的类Class写法，不使用prototype进行模拟扩展

```jsx
Class更加简洁，易维护
// 不好
function Dog(names = []) {
   this._names = [...names];
 }
Dog.prototype.bark = function() {
   const currName = this._names[0];
   alert(`one one ${currName}`);
 } 
// 好
class Dog {
   constructor(names = []) {
this._names = [...names];
 }
   
bark() {
     const currName = this._names[0];
     alert(`one one ${currName}`);
   }
 }
```

- this的注意事项

子类使用super关键字时，this应在调用super之后才能使用

可在方法中return this来实现链式调用写法

```jsx
class Foo {
   constructor(x, y) {
   this.x = x;
   this.y = y;
   }
} 
// 不好
class SubFoo extends Foo {
   constructor(x, y, z) {
this.z = z; // 引用错误
super(x, y);
       }
}  
// 好
class SubFoo extends Foo {
   constructor(x, y, z) {
     super(x, y);
     this.z = z; // this 放在 super 后调用
   }
   setHeight(height) {
     this.height = height;
     return this;
   }
}
```

##### 模块

- 使用import / export来做模块加载导出，不使用非标准模块写法

跟着标准走的人，运气总不会太差

```jsx
// 不好
const colors  = require('./colors');
module.exports = color.lightRed;  
// 好
import { lightRed } from './colors';
export default lightRed;
```

- import / export 后面采用花括号{ }引入模块的写法时，须在花括号内左右各保留一个空格

```jsx
// 不好
import {lightRed} from './colors';
import { lightRed} from './colors'; 
// 好
import { lightRed } from './colors';
```
