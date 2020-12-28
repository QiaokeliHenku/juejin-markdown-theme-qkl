# TypeScript系列--初始TypeScript

> 本文为系列文章《TypeScript系列》中的**第一篇**文章 -- 初始TypeScript。  

作为一名前端的javascript开发者，如果你总是担心上线后的javascript代码类型错误导致线上时程序崩溃，如果你写代码的时候总需要在文件间跳转查询变量的类型，如果你正在准备接手一个大型的JS项目，那么该是时候请考虑使用TypeScript进行开发你的大型项目了。

## 什么是TypeScript

**TypeScript**是微软**开源**的编程语言，该语言项目由**微软**进行维护和管理。TypeScript不仅包含JavaScript的语法，而且还提供了静态类型检查以及使用看起来像基于类的面向对象编程语法操作 Prototype。

> `C#`的首席架构师以及`Delphi`和`Turbo Pascal`的创始人**安德斯·海尔斯伯格**参与了TypeScript的开发。

### TypeScript特点

#### 始于JavaScript，归于JavaScript

TypeScript从今天数以百万计的JavaScript开发者所熟悉的语法和语义开始。使用现有的JavaScript代码，包括流行的JavaScript库，并从JavaScript代码中调用TypeScript代码。

> TypeScript可以编译出纯净、 简洁的JavaScript代码，并且可以运行在任何浏览器上、Node.js环境中和任何支持ECMAScript 3（或更高版本）的JavaScript引擎中。

#### 强大的工具构建 大型应用程序

类型允许JavaScript开发者在开发JavaScript应用程序时使用高效的开发工具和常用操作比如静态检查和代码重构。

> 类型是可选的，类型推断让一些类型的注释使你的代码的静态验证有很大的不同。类型让你定义软件组件之间的接口和洞察现有JavaScript库的行为。

#### 先进的 JavaScript

TypeScript提供最新的和不断发展的JavaScript特性，包括那些来自2015年的ECMAScript和未来的提案中的特性，比如异步功能和Decorators，以帮助建立健壮的组件。

> 这些特性为高可信应用程序开发时是可用的，但是会被编译成简洁的ECMAScript3（或更新版本）的JavaScript。

## JavaScript与TypeScript之间的区别

TypeScript 可以使用 JavaScript 中的所有代码和编码概念，TypeScript 是为了使 JavaScript 的开发变得更加容易而创建的。

> 例如：TypeScript 使用类型和接口等概念来描述正在使用的数据，这使开发人员能够快速检测错误并调试应用程序。

**主要区别如下**

1. TypeScript 从核心语言方面和类概念的模塑方面对 JavaScript 对象模型进行扩展。
2. JavaScript 代码可以在无需任何修改的情况下与 TypeScript 一同工作，同时可以使用编译器将 TypeScript 代码转换为 JavaScript。
3. TypeScript 通过类型注解提供编译时的静态类型检查。
4. TypeScript 中的数据要求带有明确的类型，JavaScript不要求。
5. TypeScript 为函数提供了缺省参数值。
6. TypeScript 引入了 JavaScript 中没有的“类”概念。
7. TypeScript 中引入了模块的概念，可以把声明、数据、函数和类封装在模块中。

## 为什么要使用TypeScript

### 代码约束

> TypeScript 的类型机制可以有效杜绝由变量类型引起的误用问题，而且开发者可以控制对类型的监控程度，是严格限制变量类型还是宽松限制变量类型，都取决于开发者的开发需求。

```typescript
const myName : string = 'hello Word';
const alias : any = '奥利给'; // 该变量可以是任何的数据类型
const age : number = 13;
const man : boolean = true;
function test (name : string) :void {}; // 该方法不需要任何的返回值
// 自定义类型
class Person {
    name: string;
    age: number;
}
const qkl : Person = new Person()
qkl.name = '巧克力很苦'
qkl.age = 18
```

### 强大的类型系统

#### 什么是类型系统

我们都知道，JavaScript中的数据类型可以分为基础数据类型和引用数据类型。

> 这里说的类型其实就是 TypeScript 中的 `Type`。只不过在 JavaScript 中，我们不需要把变量的类型明确写出来，而且，同一个变量可以赋值为不同类型的数据。但是在 TypeScript 中，每一个变量的类型都是确定的，不同类型的数据之间不能赋值。

举个，栗子：

```typescript
// javascript
let name = '巧克力很苦'
name = 5 // OK

// typescript
let name: string = '巧克力很苦'
name = 5    // Error: Type '5' is not assignable to type 'string'.
```

除此以外，在TypeScript中，我们还可以指明函数的类型。通过声明函数应该接收什么类型的数据，返回什么类型的数据，可以有效地避免许多低级错误的出现。 

```typescript
// typescript
function sayName(name: string) {
    return `你好: ${sayName}`
}
// sayName(42) // Error 类型'number'的参数不能赋给类型'string'的参数。
```

> 请注意：TypeScript 使用静态类型系统，只在编译时进行类型分析，最终编译出的 JS 源码中**不含任何类型检查的代码**（人为添加的除外），这一点要与运行时检查加以区分。 

总而言之，类型系统就是定义如何将数值和表达式归类为许多不同的类型，如何操作这些类型，通过类型，我们可以确认一个值或者一组值特定的意义和目的。 

#### 类型系统的益处

##### 在编译阶段检测错误

静态类型系统最重要的优点是，**能尽早发现逻辑错误**，而不是到真正项目上线执行的时候才发现。

JavaScript 松散的语法，在带来方便的同时，也让它变得很脆弱。通过上面的两个例子，可以感受到静态类型分析带来的优势。

> 举个例子，相信不少人在 JavaScript 开发中，都遇到过**强制类型转换**的坑，而使用 TypeScript 则可以有效地避免这种问题，原因自然是不言而喻。

#####  **舒适的开发体验**

首先，类型系统的存在为很多辅助开发的工具提供了可能。

> 比如说，当你调用函数时，现代的编辑器可以清楚地告诉你该函数需要几个参数、参数是什么类型的、哪些参数是可选的。这样可以省去大量查阅 API 的时间，提高开发效率。 

其次，类型具有一定的**自解释**（`self-explain`）的能力。而类型就像是对程序自身的注释。毕竟，代码写出来是让人读的。很多时候，光是看类型本身，我们就能理解某段程序的意图。与纯人工注释不同，随着项目的不断迭代，人工注释可能会越来越词不达意，但类型标注却可以始终忠实地反映程序本身的意义。

> 更强大的是，借助某些工具，可以根据类型标注自动生成文档。详情请参阅 [typedoc](https://typedoc.org/)。 

#####  **更高的抽象性**

类型系统允许程序设计者对程序以较高层次的方式思考，将设计者从烦人的低层次实现中解脱出来，有一种提纲挈领的感觉。

设计者可以通过设计子系统间的接口，来表达程序的逻辑。也就是说，让设计脱离实现，体现出一种 IDL（接口定义语言）的感觉，让程序设计回归本质。 

## 安装TypeScript

> 安装TypeScript环境之前要提前安装Node.js

TypeScript的命令行工具安装方法如下：

```
npm install -g typescript // npm安装
yarn global add typescript // yarn安装
```

执行上面的命令会在全局环境下安装 `tsc` 命令，安装完成之后，我们就可以在任何地方执行 `tsc` 命令了。 

编译一个 typescript 文件很简单：

```
tsc hello.ts
```

### ts-node

> 使用tsc命令运行ts文件的时候，需要先把ts文件代码转换成js文件代码，在进行运行，而这样会很麻烦的的

那么我们可以通过`ts-node`这个包来运行ts代码

**安装**

```
npm install -g ts-node // npm安装
yarn global add ts-node // yarn安装
```

安装完成之后执行`ts-node ts文件名`就可以运行ts文件了，无须要进行编译成js代码，在进行运行 。

> 我们使用TypeScript编写的文件以 `.ts` 为后缀，用 TypeScript 编写React项目时，以 `.tsx` 为后缀。 

## 关于编辑器

当前主流的编辑器都支持 TypeScript。不过在这里作者还是要着重推荐一下 [Visual Studio Code](https://code.visualstudio.com/)。 

> 它是一款免费、开源、跨终端的编辑器。由 MicroSoft 开发，与臃肿的 Visual Studio 系列 IDE 不同，这是一款现代化、轻量级的编辑器。 

最重要的是，VSCode 本身就是**用TypeScript编写的**，内置了TypeScript 支持。不管是代码补全、接口提示，还是定义跳转、代码重构等等，都可以轻松应对。 

获取其他编辑器或 IDE 对 TypeScript 的支持： 

- [Sublime Text](https://github.com/Microsoft/TypeScript-Sublime-Plugin)
- [WebStorm](https://www.jetbrains.com/webstorm/)
- [Vim](https://github.com/Microsoft/TypeScript/wiki/TypeScript-Editor-Support#vim)
- [Emacs](https://github.com/ananthakumaran/tide)
- [Eclipse](https://github.com/palantir/eclipse-typescript)
- [Atom](https://atom.io/packages/atom-typescript)
- [Visual Studio 2019](https://marketplace.visualstudio.com/search?term=TypeScriptTeam&target=VS&category=All categories&vsVersion=vs2019&sortBy=UpdatedDate)
- [Visual Studio 2017](https://marketplace.visualstudio.com/search?term=TypeScriptTeam&target=VS&category=All categories&vsVersion=vs15&sortBy=UpdatedDate)

![img](http://www.qklhk.co:5200/lassock.jpg)

> 下一章节我们主要讲解**typescript的数据类型与断言类型**，请大家敬请期待。

**文章发布时间：2020-12-21。**

