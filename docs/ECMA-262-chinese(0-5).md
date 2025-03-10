个人翻译，仅供参考



ECMA-262草案/2025-02-27

# ECMAScript2025语言规范
## 关于本规范
位于[https://tc39.es/ecma262/](https://tc39.es/ecma262/)的文档是最准确且最新的 ECMAScript 规范。它包含了最近一次年度快照的内容，以及自那次快照以来所有已完成提案的内容（即那些已经达到了[提案过程](https://tc39.es/process-document/)的第4阶段并且已在多个该标准实现中已经实现的提案，这些提案将在下一个实际修订版中出现）。

  
该文档既有单页版本也有多页版本。

## 参与本规范的贡献
本规范是在GitHub上，在ECMAScript社区的帮助下开发的。有多种方式可以为本规范的发展做出贡献：

+ GitHub仓库: [https://github.com/tc39/ecma262](https://github.com/tc39/ecma262)
+ 问题: 所有问题, 提交新问题
+ 拉取请求: 所有拉取请求, 创建新的拉取请求
+ 测试套件: Test262
+ 编辑者:
    - 郭书玉 (@_shu)
    - Michael Ficarra (@smooshMap)
    - Kevin Gibbons (@bakkoting)
+ 社区:
    - 讨论: [https://es.discourse.group/](https://es.discourse.group/)
    - 聊天: Matrix
    - 邮件列表存档: [https://esdiscuss.org/](https://esdiscuss.org/)



有关此文档创建方式的更多信息，请参阅版权页。

## 介绍 Introduction
<font style="color:rgb(17, 17, 17);">This Ecma Standard defines the ECMAScript 2025 Language. It is the sixteenth edition of the ECMAScript Language Specification. Since publication of the first edition in 1997, ECMAScript has grown to be one of the world's most widely used general-purpose programming languages. It is best known as the language embedded in web browsers but has also been widely adopted for server and embedded applications.</font>

这份Ecma标准定义了ECMAScript 2025语言。它是ECMAScript语言规范的第十六版。自1997年第一版发布以来，ECMAScript已经成为世界上最广泛使用的通用编程语言之一。它最广为人知的身份是作为嵌入在网页浏览器中的语言，与此同时也被广泛应用于服务器和嵌入式应用中。



ECMAScript is based on several originating technologies, the most well-known being JavaScript (Netscape) and JScript (Microsoft). The language was invented by Brendan Eich at Netscape and first appeared in that company's Navigator 2.0 browser. It has appeared in all subsequent browsers from Netscape and in all browsers from Microsoft starting with Internet Explorer 3.0.  
ECMAScript基于几种起源技术，其中最为人熟知的是JavaScript（网景公司）和JScript（微软）。该语言由Brendan Eich在网景公司发明，并首次出现在该公司Navigator 2.0浏览器中。此后，所有版本的网景浏览器以及从Internet Explorer 3.0开始的所有微软浏览器都支持这种语言。



The development of the ECMAScript Language Specification started in November 1996. The first edition of this Ecma Standard was adopted by the Ecma General Assembly of June 1997.  
ECMAScript语言规范的开发始于1996年11月。这份Ecma标准的第一版于1997年6月被Ecma全体大会采纳。



That Ecma Standard was submitted to ISO/IEC JTC 1 for adoption under the fast-track procedure, and approved as international standard ISO/IEC 16262, in April 1998. The Ecma General Assembly of June 1998 approved the second edition of ECMA-262 to keep it fully aligned with ISO/IEC 16262. Changes between the first and the second edition are editorial in nature.

那份Ecma标准通过快速通道程序提交给了ISO/IEC JTC 1，并于1998年4月被批准为国际标准ISO/IEC 16262。1998年6月的Ecma全体大会批准了ECMA-262的第二版，以确保其与ISO/IEC 16262完全一致。第一版和第二版之间的变化主要是编辑性质的。



The third edition of the Standard introduced powerful regular expressions, better string handling, new control statements, try/catch exception handling, tighter definition of errors, formatting for numeric output and minor changes in anticipation of future language growth. The third edition of the ECMAScript standard was adopted by the Ecma General Assembly of December 1999 and published as ISO/IEC 16262:2002 in June 2002.  
该标准的第三版引入了强大的正则表达式、更好的字符串处理、新的控制语句、try/catch异常处理机制、更严格的错误定义、数值输出格式化以及一些为未来语言发展所做的小改动。ECMAScript标准的第三版在1999年12月的Ecma全体大会上被采纳，并于2002年6月作为ISO/IEC 16262:2002发布。



After publication of the third edition, ECMAScript achieved massive adoption in conjunction with the World Wide Web where it has become the programming language that is supported by essentially all web browsers. Significant work was done to develop a fourth edition of ECMAScript. However, that work was not completed and not published as the fourth edition of ECMAScript but some of it was incorporated into the development of the sixth edition.

在第三版发布之后，ECMAScript与万维网结合实现了大规模的应用，在这个过程中它成为了几乎所有网页浏览器都支持的编程语言。为了开发ECMAScript的第四版做了大量的工作。然而，这项工作并未完成，也没有作为第四版正式发布，但其中的一部分内容被纳入了第六版的开发中。



The fifth edition of ECMAScript (published as ECMA-262 5th edition) codified de facto interpretations of the language specification that have become common among browser implementations and added support for new features that had emerged since the publication of the third edition. Such features include [accessor properties](https://tc39.es/ecma262/#sec-object-type), reflective creation and inspection of objects, program control of property attributes, additional array manipulation functions, support for the JSON object encoding format, and a strict mode that provides enhanced error checking and program security. The fifth edition was adopted by the Ecma General Assembly of December 2009.  
ECMAScript第五版（以ECMA-262第五版的形式发布）将实践中已经成为浏览器实现之间共同遵循的语言规范解释进行了编纂，并增加了自第三版发布以来出现的新特性支持。这些新特性包括访问器属性、对象的反射式创建和检查、程序对属性特性的控制、更多的数组操作函数、对JSON对象编码格式的支持，以及提供增强错误检查和程序安全性的严格模式。第五版于2009年12月被Ecma全体大会采纳。



The fifth edition was submitted to ISO/IEC JTC 1 for adoption under the fast-track procedure, and approved as international standard ISO/IEC 16262:2011. Edition 5.1 of the ECMAScript Standard incorporated minor corrections and is the same text as ISO/IEC 16262:2011. The 5.1 Edition was adopted by the Ecma General Assembly of June 2011.  
第五版通过快速通道程序提交给ISO/IEC JTC 1进行采纳，并被批准为国际标准ISO/IEC 16262:2011。ECMAScript标准5.1版包含了一些小的修正，其文本与ISO/IEC 16262:2011相同。5.1版于2011年6月被Ecma全体大会采纳。



Focused development of the sixth edition started in 2009, as the fifth edition was being prepared for publication. However, this was preceded by significant experimentation and language enhancement design efforts dating to the publication of the third edition in 1999. In a very real sense, the completion of the sixth edition is the culmination of a fifteen year effort. The goals for this edition included providing better support for large applications, library creation, and for use of ECMAScript as a compilation target for other languages. Some of its major enhancements included modules, class declarations, lexical block scoping, [iterators](https://tc39.es/ecma262/#sec-iterator-interface) and generators, promises for asynchronous programming, destructuring patterns, and proper tail calls. The ECMAScript library of built-ins was expanded to support additional data abstractions including maps, sets, and arrays of binary numeric values as well as additional support for Unicode supplementary characters in strings and regular expressions. The built-ins were also made extensible via subclassing. The sixth edition provides the foundation for regular, incremental language and library enhancements. The sixth edition was adopted by the General Assembly of June 2015.

第六版的集中开发始于2009年，当时第五版正在准备出版。然而，早在1999年第三版发布时就已经开始了大量的实验和语言增强设计工作。从某种意义上说，第六版的完成是长达十五年努力的结果。这一版的目标包括为大型应用程序、库创建以及将ECMAScript用作其他语言编译目标提供更好的支持。其主要改进包括模块、类声明、词法块作用域、迭代器和生成器、用于异步编程的Promise、解构模式以及适当的尾调用。ECMAScript内置库被扩展以支持额外的数据抽象，包括映射、集合和二进制数值数组，以及在字符串和正则表达式中对Unicode补充字符的更多支持。此外，通过子类化使内置对象可以扩展。第六版为语言和库的定期增量改进奠定了基础。第六版于2015年6月由全体大会通过。



ECMAScript 2016 was the first ECMAScript edition released under Ecma TC39's new yearly release cadence and open development process. A plain-text source document was built from the ECMAScript 2015 source document to serve as the base for further development entirely on GitHub. Over the year of this standard's development, hundreds of pull requests and issues were filed representing thousands of bug fixes, editorial fixes and other improvements. Additionally, numerous software tools were developed to aid in this effort including Ecmarkup, Ecmarkdown, and Grammarkdown. ES2016 also included support for a new exponentiation operator and adds a new method to `Array.prototype` called `includes`.

ECMAScript 2016 是在 Ecma TC39 的新年度发布节奏和开放开发流程下发布的第一个 ECMAScript 版本。该版本基于 ECMAScript 2015 的源文档构建了一个纯文本源文件，作为完全在 GitHub 上进一步开发的基础。在这项标准的开发过程中，提交了数百个拉取请求和问题，代表了数千个错误修复、编辑修正和其他改进。此外，还开发了许多软件工具来辅助这一工作，包括 Ecmarkup、Ecmarkdown 和 Grammarkdown。ES2016 还新增了对指数运算符的支持，并向`Array.prototype`了一个名为 `includes` 的新方法。



ECMAScript 2017 introduced Async Functions, Shared Memory, and Atomics along with smaller language and library enhancements, bug fixes, and editorial updates. Async functions improve the asynchronous programming experience by providing syntax for promise-returning functions. Shared Memory and Atomics introduce a new [memory model](https://tc39.es/ecma262/#sec-memory-model) that allows multi-[agent](https://tc39.es/ecma262/#agent) programs to communicate using atomic operations that ensure a well-defined execution order even on parallel CPUs. It also included new static methods on Object: `Object.values`, `Object.entries`, and `Object.getOwnPropertyDescriptors`.

ECMAScript 2017 引入了异步函数、共享内存和原子操作，以及一些较小的语言和库的增强、错误修复和编辑更新。异步函数通过提供返回承诺的函数的语法来改进异步编程体验。共享内存和原子操作引入了一种新的内存模型，该模型允许多代理程序使用确保即使在并行CPU上也能有明确执行顺序的原子操作进行通信。此外，它还包括 Object 对象上的新静态方法：`Object.values`、`Object.entries` 和 `Object.getOwnPropertyDescriptors`。



ECMAScript 2018 introduced support for asynchronous iteration via the [async iterator](https://tc39.es/ecma262/#sec-asynciterator-interface) protocol and async generators. It also included four new regular expression features: the `dotAll` flag, named capture groups, Unicode property escapes, and look-behind assertions. Lastly it included object rest and spread properties.  
ECMAScript 2018 引入了通过异步迭代器协议和支持异步生成器的异步迭代支持。它还包含了四个新的正则表达式特性：dotAll 标志、命名捕获组、Unicode 属性转义和后瞻断言。最后，它还包含了对象剩余属性和扩展属性。



ECMAScript 2019 introduced a few new built-in functions: `flat` and `flatMap` on `Array.prototype` for flattening arrays, `Object.fromEntries` for directly turning the return value of `Object.entries` into a new Object, and `trimStart` and `trimEnd` on `String.prototype` as better-named alternatives to the widely implemented but non-standard `String.prototype.trimLeft` and `trimRight` built-ins. In addition, it included a few minor updates to syntax and semantics. Updated syntax included optional catch binding parameters and allowing U+2028 (LINE SEPARATOR) and U+2029 (PARAGRAPH SEPARATOR) in string literals to align with JSON. Other updates included requiring that `Array.prototype.sort` be a stable sort, requiring that `JSON.stringify` return well-formed UTF-8 regardless of input, and clarifying `Function.prototype.toString` by requiring that it either return the corresponding original source text or a standard placeholder.

ECMAScript 2019 引入了一些新的内置函数：`Array.prototype` 上的 `flat` 和 `flatMap` 用于数组扁平化，`Object.fromEntries` 用于直接将 `Object.entries` 的返回值转换为一个新的对象，以及 `String.prototype` 上的 `trimStart` 和 `trimEnd` 作为广泛实现但非标准的 `String.prototype.trimLeft` 和 `trimRight` 内置函数的更好命名替代。此外，它还包括对语法和语义的一些小更新。更新后的语法包括可选的 catch 绑定参数，并允许在字符串字面量中使用 U+2028（行分隔符）和 U+2029（段落分隔符），以与 JSON 对齐。其他更新包括要求 `Array.prototype.sort` 是一个稳定的排序算法，要求 `JSON.stringify` 不论输入如何都要返回格式良好的 UTF-8 字符串，并通过要求其要么返回相应的原始源代码文本，要么返回一个标准占位符来澄清 `Function.prototype.toString`。



ECMAScript 2020, the 11th edition, introduced the `matchAll` method for Strings, to produce an [iterator](https://tc39.es/ecma262/#sec-iterator-interface) for all match objects generated by a global regular expression; `import()`, a syntax to asynchronously import Modules with a dynamic specifier; `BigInt`, a new number primitive for working with arbitrary precision [integers](https://tc39.es/ecma262/#integer); `Promise.allSettled`, a new Promise combinator that does not short-circuit; `globalThis`, a universal way to access the global `this` value; dedicated `export * as ns from 'module'` syntax for use within modules; increased standardization of `for-in` enumeration order; `import.meta`, a [host](https://tc39.es/ecma262/#host)-populated object available in Modules that may contain contextual information about the Module; as well as adding two new syntax features to improve working with “nullish” values (undefined or null): nullish coalescing, a value selection operator; and optional chaining, a property access and function invocation operator that short-circuits if the value to access/invoke is nullish.  
ECMAScript 2020，即第 11 版，引入了 `matchAll` 方法给字符串，用以生成由全局正则表达式生成的所有匹配对象的迭代器；`import()` 语法，用于异步导入带有动态指定符的模块；`BigInt`，一种新的数字原生类型，用于处理任意精度整数；`Promise.allSettled`，一种新的 Promise 组合方法，不会短路；`globalThis`，一种访问全局 this 值的通用方式；专门的 `export * as ns from 'module'` 语法，用于模块内部；增加了对 for-in 枚举顺序的标准规范；`import.meta`，一个在模块中可用的、可能包含有关该模块上下文信息的宿主填充对象；以及添加了两个新语法特性来改进对“nullish”值（undefined 或 null）的操作：空值合并运算符和可选链操作符，后者是一种属性访问和函数调用运算符，在要访问/调用的值是 nullish 时会短路。



ECMAScript 2021, the 12th edition, introduced the `replaceAll` method for Strings; `Promise.any`, a Promise combinator that short-circuits when an input value is fulfilled; `AggregateError`, a new Error type to represent multiple errors at once; logical assignment operators (`??=`, `&&=`, `||=`); `WeakRef`, for referring to a target object without preserving it from garbage collection, and `FinalizationRegistry`, to manage registration and unregistration of cleanup operations performed when target objects are garbage collected; separators for numeric literals (`1_000`); and `Array.prototype.sort` was made more precise, reducing the amount of cases that result in an [implementation-defined](https://tc39.es/ecma262/#implementation-defined) [sort order](https://tc39.es/ecma262/#sort-order).

ECMAScript 2021，即第12版，为字符串引入了 `replaceAll` 方法；`Promise.any`，一种当输入值被解决时立即短路的 Promise 组合器；`AggregateError`，一种新的错误类型，用于同时表示多个错误；逻辑赋值运算符（`??=`, `&&=`, `||=`）；`WeakRef`，用于引用目标对象而不阻止其被垃圾回收；`FinalizationRegistry`，用于管理当目标对象被垃圾回收时执行清理操作的注册和注销；数字字面量分隔符（如 `1_000`）；以及使 `Array.prototype.sort` 更加精确，减少了导致实现定义排序顺序的情况。



ECMAScript 2022, the 13th edition, introduced top-level `await`, allowing the [keyword](https://tc39.es/ecma262/#sec-keywords-and-reserved-words) to be used at the top level of modules; new class elements: public and private instance fields, public and private static fields, private instance methods and accessors, and private static methods and accessors; static blocks inside classes, to perform per-class evaluation initialization; the `#x in obj` syntax, to test for presence of private fields on objects; regular expression match indices via the `/d` flag, which provides start and end indices for matched substrings; the `cause` property on `Error` objects, which can be used to record a causation chain in errors; the `at` method for Strings, Arrays, and [TypedArrays](https://tc39.es/ecma262/#typedarray), which allows relative indexing; and `Object.hasOwn`, a convenient alternative to `Object.prototype.hasOwnProperty`.  
ECMAScript 2022，即第13版，引入了顶层 `await`，允许在模块的顶层使用该关键字；新的类元素：公共实例字段、私有实例字段、公共静态字段、私有静态字段、私有实例方法和访问器、以及私有静态方法和访问器；类中的静态块，用于执行每类评估初始化；`#x in obj` 语法，用于测试对象上是否存在私有字段；通过 `/d` 标志提供的正则表达式匹配索引，提供匹配子字符串的起始和结束索引；`Error` 对象上的 `cause` 属性，可用于记录错误中的因果链；字符串、数组和类型化数组的 `at` 方法，支持相对索引；以及 `Object.hasOwn`，作为 `Object.prototype.hasOwnProperty` 的便捷替代。



ECMAScript 2023, the 14th edition, introduced the `toSorted`, `toReversed`, `with`, `findLast`, and `findLastIndex` methods on `Array.prototype` and `TypedArray.prototype`, as well as the `toSpliced` method on `Array.prototype`; added support for `#!` comments at the beginning of files to better facilitate executable ECMAScript files; and allowed the use of most Symbols as keys in weak collections.

ECMAScript 2023，即第14版，在`Array.prototype`和`TypedArray.prototype`上引入了`toSorted`、`toReversed`、`with`、`findLast`和`findLastIndex`方法，以及在`Array.prototype`上引入了`toSpliced`方法；增加了对文件开头的`#!`注释的支持，以便更好地支持可执行的ECMAScript文件；并允许在弱集合中使用大多数Symbol作为键。



ECMAScript 2024, the 15th edition, added facilities for resizing and transferring ArrayBuffers and SharedArrayBuffers; added a new RegExp `/v` flag for creating RegExps with more advanced features for working with sets of strings; and introduced the `Promise.withResolvers` convenience method for constructing Promises, the `Object.groupBy` and `Map.groupBy` methods for aggregating data, the `Atomics.waitAsync` method for asynchronously waiting for a change to shared memory, and the `String.prototype.isWellFormed` and `String.prototype.toWellFormed` methods for checking and ensuring that strings contain only well-formed Unicode.  
ECMAScript 2024，即第15版，增加了调整ArrayBuffers和SharedArrayBuffers大小及转移的功能；新增了一个`/v`标志用于创建具有更高级字符串集处理功能的正则表达式（RegExp）；引入了`Promise.withResolvers`便捷方法来构造Promise对象，以及`Object.groupBy`和`Map.groupBy`方法来聚合数据；还加入了`Atomics.waitAsync`方法以异步等待共享内存的变化，以及`String.prototype.isWellFormed`和`String.prototype.toWellFormed`方法用于检查和确保字符串仅包含格式良好的Unicode。



Dozens of individuals representing many organizations have made very significant contributions within Ecma TC39 to the development of this edition and to the prior editions. In addition, a vibrant community has emerged supporting TC39's ECMAScript efforts. This community has reviewed numerous drafts, filed thousands of bug reports, performed implementation experiments, contributed test suites, and educated the world-wide developer community about ECMAScript. Unfortunately, it is impossible to identify and acknowledge every person and organization who has contributed to this effort.

Allen Wirfs-Brock  
ECMA-262, Project Editor, 6th Edition

Brian Terlson  
ECMA-262, Project Editor, 7th through 10th Editions

Jordan Harband  
ECMA-262, Project Editor, 10th through 12th Editions

Shu-yu Guo  
ECMA-262, Project Editor, 12th through 15th Editions

Michael Ficarra  
ECMA-262, Project Editor, 12th through 15th Editions

Kevin Gibbons  
ECMA-262, Project Editor, 12th through 15th Editions

数十名来自许多组织的个人为Ecma TC39中的这一版及以前版本的发展做出了非常重要的贡献。此外，一个支持TC39的ECMAScript工作的并且充满活力的社区已经形成。这个社区审查了无数草案，提交了数千份错误报告，进行了实现试验，贡献了测试套件，并向全球开发者社区普及了关于ECMAScript的知识。遗憾的是，无法在这里列出并感谢每一位为此付出努力的人和组织。  
Allen Wirfs-Brock  
ECMA-262 第6版 项目编辑  
Brian Terlson  
ECMA-262 第7至10版 项目编辑  
Jordan Harband  
ECMA-262 第10至12版 项目编辑  
Shu-yu Guo  
ECMA-262 第12至15版 项目编辑  
Michael Ficarra  
ECMA-262 第12至15版 项目编辑  
Kevin Gibbons  
ECMA-262 第12至15版 项目编辑

## 1 范围 Scope
<font style="color:rgb(17, 17, 17);">This Standard defines the ECMAScript 2025 general-purpose programming language.</font>

<font style="color:rgb(17, 17, 17);">本标准定义了ECMAScript 2025通用编程语言。</font>

<font style="color:rgb(17, 17, 17);"></font>

## <font style="color:rgb(17, 17, 17);">2 符合性 Conformance</font>
<font style="color:rgb(17, 17, 17);">A conforming implementation of ECMAScript must provide and support all the types, values, objects, properties, functions, and program syntax and semantics described in this specification.</font>

一个符合标准的ECMAScript实现必须提供并支持本规范中描述的所有类型、值、对象、属性、函数以及程序语法和语义。



<font style="color:rgb(17, 17, 17);">A conforming implementation of ECMAScript must interpret source text input in conformance with the latest version of the Unicode Standard and ISO/IEC 10646.</font>

一个符合标准的ECMAScript实现必须按照最新版本的Unicode标准和ISO/IEC 10646来解释源文本输入。



<font style="color:rgb(17, 17, 17);">A conforming implementation of ECMAScript that provides an application programming interface (API) that supports programs that need to adapt to the linguistic and cultural conventions used by different human languages and countries must implement the interface defined by the most recent edition of ECMA-402 that is compatible with this specification.</font>

一个符合ECMAScript标准的实现，如果提供了支持需要适应不同人类语言和国家所使用语言和文化惯例的程序的应用编程接口（API），则必须实现与本规范兼容的最新版ECMA-402中定义的接口。



<font style="color:rgb(17, 17, 17);">A conforming implementation of ECMAScript may provide additional types, values, objects, properties, and functions beyond those described in this specification. In particular, a conforming implementation of ECMAScript may provide properties not described in this specification, and values for those properties, for objects that are described in this specification.</font>

一个符合ECMAScript标准的实现可以提供超出本规范描述之外的额外类型、值、对象、属性和函数。特别地，一个符合ECMAScript标准的实现可以为本规范中描述的对象提供未在本规范中描述的属性及其对应的值。

<font style="color:rgb(17, 17, 17);"></font>

<font style="color:rgb(17, 17, 17);">A conforming implementation of ECMAScript may support program and regular expression syntax not described in this specification. In particular, a conforming implementation of ECMAScript may support program syntax that makes use of any “future</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">reserved words</font>](https://tc39.es/ecma262/#sec-keywords-and-reserved-words)<font style="color:rgb(17, 17, 17);">” noted in subclause</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">12.7.2</font>](https://tc39.es/ecma262/#sec-keywords-and-reserved-words)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">of this specification.</font>

一个符合ECMAScript标准的实现可能支持本规范中未描述的程序和正则表达式语法。特别地，一个符合ECMAScript标准的实现可能支持使用本规范12.7.2小节中提到的任何“未来保留字”的程序语法。

<font style="color:rgb(17, 17, 17);"></font>

<font style="color:rgb(17, 17, 17);">A conforming implementation of ECMAScript must not implement any extension that is listed as a Forbidden Extension in subclause</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">17.1</font>](https://tc39.es/ecma262/#sec-forbidden-extensions)<font style="color:rgb(17, 17, 17);">.</font>

符合ECMAScript标准的实现不得实现子条款17.1中列为禁止扩展的任何扩展。

<font style="color:rgb(17, 17, 17);"></font>

<font style="color:rgb(17, 17, 17);">A conforming implementation of ECMAScript must not redefine any facilities that are not </font>[<font style="color:rgb(32, 108, 167);">implementation-defined</font>](https://tc39.es/ecma262/#implementation-defined)<font style="color:rgb(17, 17, 17);">, </font>[<font style="color:rgb(32, 108, 167);">implementation-approximated</font>](https://tc39.es/ecma262/#implementation-approximated)<font style="color:rgb(17, 17, 17);">, or </font>[<font style="color:rgb(32, 108, 167);">host-defined</font>](https://tc39.es/ecma262/#host-defined)<font style="color:rgb(17, 17, 17);">.</font>

一个符合标准的ECMAScript实现不得重新定义任何非实现定义、非实现近似或非宿主定义的功能。

<font style="color:rgb(17, 17, 17);"></font>

<font style="color:rgb(17, 17, 17);">A conforming implementation of ECMAScript may choose to implement or not implement Normative Optional subclauses. If any Normative Optional behaviour is implemented, all of the behaviour in the containing Normative Optional clause must be implemented. A Normative Optional clause is denoted in this specification with the words "Normative Optional" in a coloured box, as shown below.</font>

一个符合标准的ECMAScript实现可以选择实现或不实现规范性可选子条款。如果实现了任何规范性可选行为，那么必须实现包含该规范性可选行为的整个条款中的所有行为。本规范中，规范性可选项以彩色框中的“规范性可选”字样表示，如下所示。

<font style="color:rgb(17, 17, 17);"></font>

> [Normative Optional](https://tc39.es/ecma262/#sec-conformance)
>

### 2.1 Example Normative Optional Clause Heading
2.1 示例规范性可选条款标题

Example clause contents.

<font style="color:rgb(17, 17, 17);">A conforming implementation of ECMAScript must implement Legacy subclauses, unless they are also marked as Normative Optional. All of the language features and behaviours specified within Legacy subclauses have one or more undesirable characteristics. However, their continued usage in existing applications prevents their removal from this specification. These features are not considered part of the core ECMAScript language. Programmers should not use or assume the existence of these features and behaviours when writing new ECMAScript code.</font>

<font style="color:rgb(17, 17, 17);">示例条款内容。</font>

一个符合ECMAScript标准的实现必须实现遗留子条款，除非它们也被标记为“规范性可选”。所有在遗留子条款中指定的语言特性和行为都具有一种或多种不理想的特性。然而，由于这些特性在现有应用程序中的持续使用，使得它们无法从本规范中移除。这些特性不被视为ECMAScript核心语言的一部分。程序员在编写新的ECMAScript代码时，不应使用或假定存在这些特性和行为。

<font style="color:rgb(17, 17, 17);background-color:rgb(255, 238, 221);"></font>

> [Legacy](https://tc39.es/ecma262/#sec-conformance)
>

### 2.2 Example Legacy Clause Heading
Example clause contents.

<font style="color:rgb(17, 17, 17);">示例条款内容。</font>

<font style="color:rgb(17, 17, 17);"></font>

> [Normative Optional](https://tc39.es/ecma262/#sec-conformance), [Legacy](https://tc39.es/ecma262/#sec-conformance)
>

### 2.3 Example Legacy Normative Optional Clause Heading
Example clause contents.

<font style="color:rgb(17, 17, 17);">示例条款内容。</font>  


## <font style="color:rgb(17, 17, 17);">3 规范参考 Normative References</font>
<font style="color:rgb(17, 17, 17);">The following referenced documents are indispensable for the application of this document. For dated references, only the edition cited applies. For undated references, the latest edition of the referenced document (including any amendments) applies.</font>

[<font style="color:rgb(32, 108, 167);">IEEE 754-2019</font>](https://tc39.es/ecma262/#sec-bibliography)<font style="color:rgb(17, 17, 17);">,</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">IEEE Standard for Floating-Point Arithmetic</font><font style="color:rgb(17, 17, 17);">.</font>

<font style="color:rgb(17, 17, 17);">The Unicode Standard.  
</font>[<font style="color:rgb(32, 108, 167);">https://unicode.org/versions/latest</font>](https://unicode.org/versions/latest)

<font style="color:rgb(17, 17, 17);">ISO/IEC 10646,</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">Information Technology — Universal Multiple-Octet Coded Character Set (UCS)</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">plus Amendment 1:2005, Amendment 2:2006, Amendment 3:2008, Amendment 4:2008, and additional amendments and corrigenda, or successor.</font>

<font style="color:rgb(17, 17, 17);">ECMA-402,</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">ECMAScript Internationalization API Specification</font><font style="color:rgb(17, 17, 17);">, specifically the annual edition corresponding to this edition of this specification.  
</font>[<font style="color:rgb(32, 108, 167);">https://www.ecma-international.org/publications-and-standards/standards/ecma-402/</font>](https://www.ecma-international.org/publications-and-standards/standards/ecma-402/)

<font style="color:rgb(17, 17, 17);">ECMA-404, The JSON Data Interchange Format.  
</font>[<font style="color:rgb(32, 108, 167);">https://www.ecma-international.org/publications-and-standards/standards/ecma-404/</font>](https://www.ecma-international.org/publications-and-standards/standards/ecma-404/)

以下引用的文件对于本文件的应用是必不可少的。对于有日期的引用，仅适用所引用的版本。对于无日期的引用，适用所引用文件的最新版本（包括任何修订）。

+ IEEE 754-2019，《IEEE浮点算术标准》。
+ Unicode 标准。
    - [https://unicode.org/versions/latest](https://unicode.org/versions/latest)
+ ISO/IEC 10646，《信息技术 — 通用多八位编码字符集 (UCS)》及修正案 1:2005、修正案 2:2006、修正案 3:2008、修正案 4:2008 及其他后续的修正案和勘误表，或其后继版本。
+ ECMA-402，《ECMAScript 国际化 API 规范》，特别是与本规范这一版相对应的年度版本。
    - [https://www.ecma-international.org/publications-and-standards/standards/ecma-402/](https://www.ecma-international.org/publications-and-standards/standards/ecma-402/)
+ ECMA-404，《JSON 数据交换格式》。
    - [https://www.ecma-international.org/publications-and-standards/standards/ecma-404/](https://www.ecma-international.org/publications-and-standards/standards/ecma-404/)

<font style="color:rgb(17, 17, 17);"></font>

## <font style="color:rgb(17, 17, 17);">4 概述 Overview</font>
<font style="color:rgb(17, 17, 17);">This section contains a non-normative overview of the ECMAScript language.</font>

本节包含了ECMAScript语言的非规范性概述。



<font style="color:rgb(17, 17, 17);">ECMAScript is an object-oriented programming language for performing computations and manipulating computational objects within a</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);">. ECMAScript as defined here is not intended to be computationally self-sufficient; indeed, there are no provisions in this specification for input of external data or output of computed results. Instead, it is expected that the computational environment of an ECMAScript program will provide not only the objects and other facilities described in this specification but also certain environment-specific objects, whose description and behaviour are beyond the scope of this specification except to indicate that they may provide certain properties that can be accessed and certain functions that can be called from an ECMAScript program.</font>

ECMAScript是一种面向对象的编程语言，用于在宿主环境中执行计算和操作计算对象。此处定义的ECMAScript并不打算在计算上自给自足；实际上，本规范中并没有提供外部数据输入或计算结果输出的规定。相反，预期ECMAScript程序的计算环境不仅将提供本规范中描述的对象和其他设施，还将提供某些特定于环境的对象，这些对象的描述和行为超出了本规范的范围，除了指出它们可能提供可以从ECMAScript程序访问的某些属性以及可以调用的某些函数之外。



<font style="color:rgb(17, 17, 17);">ECMAScript was originally designed to be used as a scripting language, but has become widely used as a general-purpose programming language. A</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">scripting language</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">is a programming language that is used to manipulate, customize, and automate the facilities of an existing system. In such systems, useful functionality is already available through a user interface, and the scripting language is a mechanism for exposing that functionality to program control. In this way, the existing system is said to provide a</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">of objects and facilities, which completes the capabilities of the scripting language. A scripting language is intended for use by both professional and non-professional programmers.</font>

ECMAScript 最初被设计为一种脚本语言，但现在已经广泛用作一种通用编程语言。脚本语言是一种用于操作、定制和自动化现有系统功能的编程语言。在这样的系统中，有用的功能已经通过用户界面提供，而脚本语言则是一种将这些功能暴露给程序控制的机制。这样，现有的系统就被认为提供了对象和设施的宿主环境，从而补充了脚本语言的能力。脚本语言旨在供专业和非专业程序员使用。



<font style="color:rgb(17, 17, 17);">ECMAScript was originally designed to be a</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">Web scripting language</font><font style="color:rgb(17, 17, 17);">, providing a mechanism to enliven Web pages in browsers and to perform server computation as part of a Web-based client-server architecture. ECMAScript is now used to provide core scripting capabilities for a variety of</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">host environments</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);">. Therefore the core language is specified in this document apart from any particular</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);">.</font>

ECMAScript 最初被设计为一种网页脚本语言，提供了一种在浏览器中使网页变得生动以及作为基于 Web 的客户端-服务器架构的一部分执行服务器端计算的机制。现在，ECMAScript 被用于为各种宿主环境提供核心脚本功能。因此，本文档中单独规定了这种核心语言，不依赖于任何特定的宿主环境。



<font style="color:rgb(17, 17, 17);">ECMAScript usage has moved beyond simple scripting and it is now used for the full spectrum of programming tasks in many different environments and scales. As the usage of ECMAScript has expanded, so have the features and facilities it provides. ECMAScript is now a fully featured general-purpose programming language.</font>

ECMAScript 的使用已经超越了简单的脚本编写，现在它被广泛应用于各种不同环境和规模的全方位编程任务中。随着 ECMAScript 应用范围的扩大，其提供的特性和功能也日益丰富。如今，ECMAScript 已经成为一种功能齐全的通用编程语言。

### <font style="color:rgb(17, 17, 17);">4.1 Web Scripting 网页脚本</font>
<font style="color:rgb(17, 17, 17);">A web browser provides an ECMAScript </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);"> for client-side computation including, for instance, objects that represent windows, menus, pop-ups, dialog boxes, text areas, anchors, frames, history, cookies, and input/output. Further, the </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);"> provides a means to attach scripting code to events such as change of focus, page and image loading, unloading, error and abort, selection, form submission, and mouse actions. Scripting code appears within the HTML and the displayed page is a combination of user interface elements and fixed and computed text and images. The scripting code is reactive to user interaction, and there is no need for a main program.</font>

网页浏览器为客户端计算提供了一个ECMAScript宿主环境，其中包括表示窗口、菜单、弹出框、对话框、文本区域、锚点、框架、历史记录、cookie以及输入/输出的对象。此外，宿主环境还提供了一种方式，可以将脚本代码附加到诸如焦点变化、页面和图像加载、卸载、错误和中止、选择、表单提交以及鼠标动作等事件上。脚本代码会出现在HTML中，显示的页面是用户界面元素与固定和计算出的文本及图像的组合。脚本代码能够响应用户的交互，并且不需要一个主程序。



<font style="color:rgb(17, 17, 17);">A web server provides a different</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">for server-side computation including objects representing requests, clients, and files; and mechanisms to lock and share data. By using browser-side and server-side scripting together, it is possible to distribute computation between the client and server while providing a customized user interface for a Web-based application.</font>

网页服务器为服务器端计算提供了一个不同的主机环境，其中包括代表请求、客户端和文件的对象；以及锁定和共享数据的机制。通过同时使用浏览器端和服务器端脚本，可以将计算分布在客户端和服务器之间，同时为基于Web的应用程序提供定制化的用户界面。



<font style="color:rgb(17, 17, 17);">Each Web browser and server that supports ECMAScript supplies its own </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);">, completing the ECMAScript execution environment.</font>

每个支持ECMAScript的Web浏览器和服务器都提供了自己的宿主环境，从而完成了ECMAScript的执行环境。

### <font style="color:rgb(17, 17, 17);">4.2 Hosts and Implementations </font>宿主与实现
To aid integrating ECMAScript into [host environments](https://tc39.es/ecma262/#host-environment), this specification defers the definition of certain facilities (e.g., [abstract operations](https://tc39.es/ecma262/#sec-algorithm-conventions-abstract-operations)), either in whole or in part, to a source outside of this specification. Editorially, this specification distinguishes the following kinds of deferrals.

为了帮助将ECMAScript集成到宿主环境中，本规范将某些设施（例如，抽象操作）的定义全部或部分地推迟到本规范之外的来源进行定义。从编辑的角度来看，本规范区分了以下几种推迟方式。



An implementation is an external source that further defines facilities enumerated in Annex [D](https://tc39.es/ecma262/#sec-host-layering-points) or those that are marked as [implementation-defined](https://tc39.es/ecma262/#implementation-defined) or [implementation-approximated](https://tc39.es/ecma262/#implementation-approximated). In informal use, an implementation refers to a concrete artefact, such as a particular web browser.

实现是一个外部来源，它进一步定义了附录D中列举的设施，或者是那些被标记为实现定义或实现近似的设施。在非正式使用中，实现指的是一个具体的产物，比如某个特定的网页浏览器。



An implementation-defined facility is one that defers its definition to an external source without further qualification. This specification does not make any recommendations for particular behaviours, and conforming implementations are free to choose any behaviour within the constraints put forth by this specification.

实现定义的设施是指将定义推迟到外部来源而不再进一步限定的设施。本规范不对特定行为提出任何建议，遵循该规范的实现可以在本规范所设定的约束范围内自由选择任何行为。



An implementation-approximated facility is one that defers its definition to an external source while recommending an ideal behaviour. While conforming implementations are free to choose any behaviour within the constraints put forth by this specification, they are encouraged to strive to approximate the ideal. Some mathematical operations, such as [Math.exp](https://tc39.es/ecma262/#sec-math.exp), are [implementation-approximated](https://tc39.es/ecma262/#implementation-approximated).

一种实现近似的设施是指将其实现定义推迟到外部来源，同时推荐理想行为的方式。虽然符合标准的实现可以在本规范提出的约束范围内自由选择任何行为，但鼓励它们努力接近理想行为。一些数学运算，比如 Math.exp，就是实现近似的例子。



A host is an external source that further defines facilities listed in Annex [D](https://tc39.es/ecma262/#sec-host-layering-points) but does not further define other [implementation-defined](https://tc39.es/ecma262/#implementation-defined) or [implementation-approximated](https://tc39.es/ecma262/#implementation-approximated) facilities. In informal use, a [host](https://tc39.es/ecma262/#host) refers to the set of all implementations, such as the set of all web browsers, that interface with this specification in the same way via Annex [D](https://tc39.es/ecma262/#sec-host-layering-points). A [host](https://tc39.es/ecma262/#host) is often an external specification, such as WHATWG HTML ([https://html.spec.whatwg.org/](https://html.spec.whatwg.org/)). In other words, facilities that are [host-defined](https://tc39.es/ecma262/#host-defined) are often further defined in external specifications.

主机是一种外部来源，它进一步定义了附录D中列出的设施，但不进一步定义其他由实现定义或近似的设施。在非正式使用中，主机指的是所有以相同方式通过附录D与此规范接口的所有实现的集合，例如所有网络浏览器的集合。主机通常是一个外部规范，如WHATWG HTML（https://html.spec.whatwg.org/）。换句话说，由主机定义的设施通常在外部规范中有更详细的定义。



A host hook is an abstract operation that is defined in whole or in part by an external source. All [host hooks](https://tc39.es/ecma262/#host-hook) must be listed in Annex [D](https://tc39.es/ecma262/#sec-host-layering-points). A [host hook](https://tc39.es/ecma262/#host-hook) must conform to at least the following requirements:

+ It must return either a [normal completion](https://tc39.es/ecma262/#sec-completion-record-specification-type) or a [throw completion](https://tc39.es/ecma262/#sec-completion-record-specification-type).

主机钩子是一种全部或部分由外部源定义的抽象操作。所有主机钩子必须列在附录D中。主机钩子必须至少符合以下要求：

+ 它必须返回正常完成或抛出完成。



A host-defined facility is one that defers its definition to an external source without further qualification and is listed in Annex [D](https://tc39.es/ecma262/#sec-host-layering-points). Implementations that are not [hosts](https://tc39.es/ecma262/#host) may also provide definitions for [host-defined](https://tc39.es/ecma262/#host-defined) facilities.

宿主定义的设施是指那些将其定义推迟到外部来源而不再进一步限定，并且列在附录D中的设施。非宿主实现也可以为宿主定义的设施提供定义。



A host environment is a particular choice of definition for all [host-defined](https://tc39.es/ecma262/#host-defined) facilities. A [host environment](https://tc39.es/ecma262/#host-environment) typically includes objects or functions which allow obtaining input and providing output as [host-defined](https://tc39.es/ecma262/#host-defined) properties of the [global object](https://tc39.es/ecma262/#sec-global-object).

宿主环境是对所有由宿主定义的设施的一种特定选择。宿主环境通常包括对象或函数，这些对象或函数允许通过全局对象的宿主定义属性来获取输入和提供输出。



This specification follows the editorial convention of always using the most specific term. For example, if a facility is [host-defined](https://tc39.es/ecma262/#host-defined), it should not be referred to as [implementation-defined](https://tc39.es/ecma262/#implementation-defined).

本规范遵循使用最具体术语的编辑惯例。例如，如果某功能是由主机定义的，则不应将其称为由实现定义的。



Both [hosts](https://tc39.es/ecma262/#host) and implementations may interface with this specification via the language types, specification types, [abstract operations](https://tc39.es/ecma262/#sec-algorithm-conventions-abstract-operations), grammar productions, intrinsic objects, and intrinsic symbols defined herein.

宿主和实现可以通过本规范定义的语言类型、规范类型、抽象操作、语法产生式、内置对象和内置符号进行编写接口。

<font style="color:rgb(17, 17, 17);"></font>

### <font style="color:rgb(17, 17, 17);">4.3 ECMAScript Overview ECMAScript概述</font>
The following is an informal overview of ECMAScript—not all parts of the language are described. This overview is not part of the standard proper.

以下是非正式的ECMAScript概览——并非语言的所有部分都得到了描述。此概览并不属于标准文档本身。



ECMAScript is object-based: basic language and [host](https://tc39.es/ecma262/#host) facilities are provided by objects, and an ECMAScript program is a cluster of communicating objects. In ECMAScript, an object is a collection of zero or more properties each with attributes that determine how each property can be used—for example, when the Writable attribute for a property is set to false, any attempt by executed ECMAScript code to assign a different value to the property fails. Properties are containers that hold other objects, primitive values, or functions. A primitive value is a member of one of the following built-in types: Undefined, Null, Boolean, Number, BigInt, String, and Symbol; an object is a member of the built-in type Object; and a function is a callable object. A function that is associated with an object via a property is called a _method_.

ECMAScript 是基于对象的：基本语言和宿主设施都是通过对象提供的，而一个 ECMAScript 程序是由一群相互通讯的对象组成的。在 ECMAScript 中，对象是由零个或多个属性组成的集合，每个属性都有决定其使用方式的特性——例如，当某个属性的 Writable 特性被设置为 false 时，任何试图通过执行的 ECMAScript 代码来给该属性赋新值的操作都会失败。属性是存储其他对象、原始值或函数的容器。原始值属于以下内置类型之一：Undefined、Null、Boolean、Number、BigInt、String 和 Symbol；对象则属于内置类型 Object 的成员；函数是一种可调用的对象。通过属性与对象关联的函数被称为方法。



ECMAScript defines a collection of built-in objects that round out the definition of ECMAScript entities. These built-in objects include the [global object](https://tc39.es/ecma262/#sec-global-object); objects that are fundamental to the [runtime semantics](https://tc39.es/ecma262/#sec-runtime-semantics) of the language including `Object`, `Function`, `Boolean`, `Symbol`, and various `Error` objects; objects that represent and manipulate numeric values including `Math`, `Number`, and `Date`; the text processing objects `String` and `RegExp`; objects that are indexed collections of values including `Array` and nine different kinds of Typed Arrays whose elements all have a specific numeric data representation; keyed collections including `Map` and `Set` objects; objects supporting structured data including the `JSON` object, `ArrayBuffer`, `SharedArrayBuffer`, and `DataView`; objects supporting control abstractions including generator functions and `Promise` objects; and reflection objects including `Proxy` and `Reflect`.

ECMAScript 定义了一组内置对象，这些对象完善了 ECMAScript 实体的定义。这些内置对象包括全局对象；对语言运行时语义至关重要的对象，如 Object、Function、Boolean、Symbol 以及各种 Error 对象；表示和处理数值的对象，如 Math、Number 和 Date；文本处理对象 String 和 RegExp；作为值的索引集合的对象，包括 Array 和九种不同类型的 Typed Arrays，它们的元素都有特定的数值数据表示；键值集合，包括 Map 和 Set 对象；支持结构化数据的对象，如 JSON 对象、ArrayBuffer、SharedArrayBuffer 和 DataView；支持控制抽象的对象，包括生成器函数和 Promise 对象；以及反射对象，包括 Proxy 和 Reflect。



ECMAScript also defines a set of built-in _operators_. ECMAScript operators include various unary operations, multiplicative operators, additive operators, bitwise shift operators, relational operators, equality operators, binary bitwise operators, binary logical operators, assignment operators, and the comma operator.

ECMAScript 也定义了一组内置运算符。ECMAScript 运算符包括各种一元运算、乘性运算符、加性运算符、位移运算符、关系运算符、相等运算符、二进制位运算符、二进制逻辑运算符、赋值运算符以及逗号运算符。



Large ECMAScript programs are supported by modules which allow a program to be divided into multiple sequences of statements and declarations. Each module explicitly identifies declarations it uses that need to be provided by other modules and which of its declarations are available for use by other modules.

大型ECMAScript程序通过模块来支持，这些模块允许将程序划分为多个语句和声明序列。每个模块都明确指出了它所使用的需要由其他模块提供的声明，以及它的哪些声明可以供其他模块使用。



ECMAScript syntax intentionally resembles Java syntax. ECMAScript syntax is relaxed to enable it to serve as an easy-to-use scripting language. For example, a variable is not required to have its type declared nor are types associated with properties, and defined functions are not required to have their declarations appear textually before calls to them.

ECMAScript的语法有意地类似于Java的语法。ECMAScript的语法则更为宽松，使其能够作为一种易于使用的脚本语言。例如，变量不需要声明其类型，属性也不需要关联类型，并且定义的函数在被调用前不需要先进行文本上的声明。

#### <font style="color:#DF2A3F;">4.3.1 Objects</font><font style="color:rgb(17, 17, 17);"> 对象</font>
Even though ECMAScript includes syntax for class definitions, ECMAScript objects are not fundamentally class-based such as those in C++, Smalltalk, or Java. Instead objects may be created in various ways including via a literal notation or via [constructors](https://tc39.es/ecma262/#constructor) which create objects and then execute code that initializes all or part of them by assigning initial values to their properties. Each [constructor](https://tc39.es/ecma262/#constructor) is a function that has a property named "prototype" that is used to implement prototype-based inheritance and shared properties. Objects are created by using [constructors](https://tc39.es/ecma262/#constructor) in new expressions; for example, `new Date(2009, 11)` creates a new Date object. Invoking a [constructor](https://tc39.es/ecma262/#constructor) without using new has consequences that depend on the [constructor](https://tc39.es/ecma262/#constructor). For example, `Date()` produces a string representation of the current date and time rather than an object.

尽管ECMAScript包含类定义的语法，但ECMAScript对象本质上并不是基于类的，不像C++、Smalltalk或Java中的那些对象。相反，可以通过多种方式创建对象，包括使用字面量表示法或通过构造函数来创建对象，这些构造函数创建对象后会执行代码，通过给它们的属性赋初始值来初始化全部或部分对象。每个构造函数都是一个具有名为“prototype”的属性的函数，这个属性用于实现基于原型的继承和共享属性。对象是通过在new表达式中使用构造函数创建的；例如，new Date(2009, 11) 创建一个新的Date对象。如果不使用new调用构造函数，则结果取决于具体的构造函数。例如，Date() 会产生当前日期和时间的字符串表示形式，而不是一个对象。



Every object created by a [constructor](https://tc39.es/ecma262/#constructor) has an implicit reference (called the object's prototype) to the value of its [constructor](https://tc39.es/ecma262/#constructor)'s "prototype" property. Furthermore, a prototype may have a non-null implicit reference to its prototype, and so on; this is called the prototype chain. When a reference is made to a property in an object, that reference is to the property of that name in the first object in the prototype chain that contains a property of that name. In other words, first the object mentioned directly is examined for such a property; if that object contains the named property, that is the property to which the reference refers; if that object does not contain the named property, the prototype for that object is examined next; and so on.

每个由构造函数创建的对象都有一个隐式引用（称为对象的原型）指向其构造函数的“prototype”属性的值。此外，一个原型可以有一个非空的隐式引用来指向它的原型，以此类推；这被称为原型链。当引用对象中的某个属性时，该引用实际上是指向原型链中第一个包含该名称属性的对象中的该属性。换句话说，首先检查直接提到的对象是否存在这样的属性；如果该对象包含这个命名的属性，则引用就指向这个属性；如果该对象不包含这个命名的属性，则接下来检查该对象的原型；依此类推。  


**<font style="color:rgb(85, 85, 85);">Figure 1: Object/Prototype Relationships </font>**图1：对象/原型关系

![](https://cdn.nlark.com/yuque/0/2025/png/8418183/1741334820089-b3302de0-1ba6-49fb-8efa-24e884c775f3.png)

In a class-based object-oriented language, in general, state is carried by instances, methods are carried by classes, and inheritance is only of structure and behaviour. In ECMAScript, the state and methods are carried by objects, while structure, behaviour, and state are all inherited.

在基于类的面向对象语言中，通常情况下，状态是由实例携带的，方法是由类携带的，而继承仅涉及结构和行为。而在ECMAScript中，状态和方法都是由对象携带的，同时结构、行为和状态都可以被继承。



All objects that do not directly contain a particular property that their prototype contains share that property and its value. Figure 1 illustrates this:

**<font style="color:rgb(17, 17, 17);">CF</font>**<font style="color:rgb(17, 17, 17);"> is a </font>[<font style="color:rgb(32, 108, 167);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="color:rgb(17, 17, 17);"> (and also an object). Five objects have been created by using </font>`**<font style="color:rgb(17, 17, 17);">new</font>**`<font style="color:rgb(17, 17, 17);"> expressions: </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">1</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">2</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">3</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">4</font>**</sub><font style="color:rgb(17, 17, 17);">, and </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">5</font>**</sub><font style="color:rgb(17, 17, 17);">. Each of these objects contains properties named </font>**<font style="color:rgb(17, 17, 17);">"q1"</font>**<font style="color:rgb(17, 17, 17);"> and </font>**<font style="color:rgb(17, 17, 17);">"q2"</font>**<font style="color:rgb(17, 17, 17);">. The dashed lines represent the implicit prototype relationship; so, for example, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">3</font>**</sub><font style="color:rgb(17, 17, 17);">'s prototype is </font>**<font style="color:rgb(17, 17, 17);">CF</font>**<sub>**<font style="color:rgb(17, 17, 17);">p</font>**</sub><font style="color:rgb(17, 17, 17);">. The </font>[<font style="color:rgb(32, 108, 167);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">CF</font>**<font style="color:rgb(17, 17, 17);">, has two properties itself, named </font>**<font style="color:rgb(17, 17, 17);">"P1"</font>**<font style="color:rgb(17, 17, 17);"> and </font>**<font style="color:rgb(17, 17, 17);">"P2"</font>**<font style="color:rgb(17, 17, 17);">, which are not visible to </font>**<font style="color:rgb(17, 17, 17);">CF</font>**<sub>**<font style="color:rgb(17, 17, 17);">p</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">1</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">2</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">3</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">4</font>**</sub><font style="color:rgb(17, 17, 17);">, or </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">5</font>**</sub><font style="color:rgb(17, 17, 17);">. The property named </font>**<font style="color:rgb(17, 17, 17);">"CFP1"</font>**<font style="color:rgb(17, 17, 17);"> in </font>**<font style="color:rgb(17, 17, 17);">CF</font>**<sub>**<font style="color:rgb(17, 17, 17);">p</font>**</sub><font style="color:rgb(17, 17, 17);"> is shared by </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">1</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">2</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">3</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">4</font>**</sub><font style="color:rgb(17, 17, 17);">, and </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">5</font>**</sub><font style="color:rgb(17, 17, 17);"> (but not by </font>**<font style="color:rgb(17, 17, 17);">CF</font>**<font style="color:rgb(17, 17, 17);">), as are any properties found in </font>**<font style="color:rgb(17, 17, 17);">CF</font>**<sub>**<font style="color:rgb(17, 17, 17);">p</font>**</sub><font style="color:rgb(17, 17, 17);">'s implicit prototype chain that are not named </font>**<font style="color:rgb(17, 17, 17);">"q1"</font>**<font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">"q2"</font>**<font style="color:rgb(17, 17, 17);">, or </font>**<font style="color:rgb(17, 17, 17);">"CFP1"</font>**<font style="color:rgb(17, 17, 17);">. Notice that there is no implicit prototype link between </font>**<font style="color:rgb(17, 17, 17);">CF</font>**<font style="color:rgb(17, 17, 17);"> and </font>**<font style="color:rgb(17, 17, 17);">CF</font>**<sub>**<font style="color:rgb(17, 17, 17);">p</font>**</sub><font style="color:rgb(17, 17, 17);">.</font>

所有不直接包含其原型中特定属性的对象都会共享原型中该特定属性及其值。图1说明了这一点：  
CF是一个构造函数（同时也是一个对象）。通过使用new表达式创建了五个对象：cf<sub>1</sub>、cf<sub>2</sub>、cf<sub>3</sub>、cf<sub>4</sub>和cf<sub>5</sub>。每个这些对象都包含名为"q1"和"q2"的属性。虚线表示隐式的原型关系；例如，cf<sub>3</sub>的原型是CF<sub>p</sub>。构造函数CF本身有两个属性，名为"P1"和"P2"，这些属性对CF<sub>p</sub>、cf<sub>1</sub>、cf<sub>2</sub>、cf<sub>3</sub>、cf<sub>4</sub>或cf<sub>5</sub>不可见。CF<sub>p</sub>中的名为"CFP1"的属性被cf<sub>1</sub>、cf<sub>2</sub>、cf<sub>3</sub>、cf<sub>4</sub>和cf<sub>5</sub>共享（但不被CF共享），同样地，任何在CF<sub>p</sub>的隐式原型链中找到的且不名为"q1"、"q2"或"CFP1"的属性也是如此。请注意，CF与CF<sub>p</sub>之间没有隐式的原型链接。



Unlike most class-based object languages, properties can be added to objects dynamically by assigning values to them. That is, [constructors](https://tc39.es/ecma262/#constructor) are not required to name or assign values to all or any of the constructed object's properties. In the above diagram, one could add a new shared property for<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">1</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">2</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">3</font>**</sub><font style="color:rgb(17, 17, 17);">, </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">4</font>**</sub>, and<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">cf</font>**<sub>**<font style="color:rgb(17, 17, 17);">5</font>**</sub><font style="color:rgb(17, 17, 17);"> </font>by assigning a new value to the property in<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">CF</font>**<sub>**<font style="color:rgb(17, 17, 17);">p</font>**</sub><font style="color:rgb(17, 17, 17);">.</font>

与大多数基于类的对象语言不同，可以通过给对象赋值来动态地向对象添加属性。也就是说，构造函数不需要命名或为所构建对象的所有或任何属性赋值。在上面的图示中，可以通过在CF<sub>p</sub>中为该属性赋新值来为cf<sub>1</sub>、cf<sub>2</sub>、cf<sub>3</sub>、cf<sub>4</sub>和cf<sub>5</sub>添加一个新的共享属性。



Although ECMAScript objects are not inherently class-based, it is often convenient to define class-like abstractions based upon a common pattern of [constructor](https://tc39.es/ecma262/#constructor) functions, prototype objects, and methods. The ECMAScript built-in objects themselves follow such a class-like pattern. Beginning with ECMAScript 2015, the ECMAScript language includes syntactic class definitions that permit programmers to concisely define objects that conform to the same class-like abstraction pattern used by the built-in objects.

尽管ECMAScript对象本质上不是基于类的，但通常根据构造函数、原型对象和方法的通用模式来定义类似类的抽象会很方便。ECMAScript内置对象本身也遵循这种类似类的模式。从ECMAScript 2015开始，ECMAScript语言包含了语法上的类定义，允许程序员简洁地定义符合内置对象所使用的相同类似抽象模式的对象。

#### <font style="color:rgb(17, 17, 17);">4.3.2 The Strict Variant of ECMAScript ECMAScript的严格变体(严格模式)</font>
<font style="color:rgb(17, 17, 17);">The ECMAScript Language recognizes the possibility that some users of the language may wish to restrict their usage of some features available in the language. They might do so in the interests of security, to avoid what they consider to be error-prone features, to get enhanced error checking, or for other reasons of their choosing. In support of this possibility, ECMAScript defines a strict variant of the language. The strict variant of the language excludes some specific syntactic and semantic features of the regular ECMAScript language and modifies the detailed semantics of some features. The strict variant also specifies additional error conditions that must be reported by throwing error exceptions in situations that are not specified as errors by the non-strict form of the language.</font>

ECMAScript语言认识到，有些用户可能希望限制他们对语言中某些特性的使用。他们可能会出于安全考虑、避免他们认为容易出错的特性、获得增强的错误检查，或其他自选的原因而这样做。为了支持这种可能性，ECMAScript 定义了该语言的一种严格变体。严格变体排除了常规 ECMAScript 语言中的某些特定语法和语义特性，并修改了一些特性的详细语义。严格变体还规定了额外的错误条件，在非严格形式的语言未指定为错误的情况下，必须通过抛出错误异常来报告这些情况。



<font style="color:rgb(17, 17, 17);">The strict variant of ECMAScript is commonly referred to as the</font><font style="color:rgb(17, 17, 17);"> </font>_<font style="color:rgb(17, 17, 17);">strict mode</font>_<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">of the language. Strict mode selection and use of the strict mode syntax and semantics of ECMAScript is explicitly made at the level of individual</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">ECMAScript source text</font>](https://tc39.es/ecma262/#sec-source-text)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">units as described in</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">11.2.2</font>](https://tc39.es/ecma262/#sec-strict-mode-code)<font style="color:rgb(17, 17, 17);">. Because strict mode is selected at the level of a syntactic source text unit, strict mode only imposes restrictions that have local effect within such a source text unit. Strict mode does not restrict or modify any aspect of the ECMAScript semantics that must operate consistently across multiple source text units. A complete ECMAScript program may be composed of both strict mode and non-strict mode</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">ECMAScript source text</font>](https://tc39.es/ecma262/#sec-source-text)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">units. In this case, strict mode only applies when actually executing code that is defined within a strict mode source text unit.</font>

ECMAScript的严格变体通常被称为该语言的严格模式。严格模式的选择以及对 ECMAScript 严格模式语法和语义的使用，是在单个 ECMAScript 源文本单元的级别上明确指定的，如 11.2.2 节所述。由于严格模式是在语法源文本单元级别选择的，因此严格模式仅施加在该源文本单元内具有局部效果的限制。严格模式不会限制或修改必须跨多个源文本单元一致运行的 ECMAScript 语义的任何方面。一个完整的 ECMAScript 程序可以由严格模式和非严格模式的 ECMAScript 源文本单元组成。在这种情况下，严格模式仅在实际执行严格模式源文本单元中定义的代码时适用。



<font style="color:rgb(17, 17, 17);">In order to conform to this specification, an ECMAScript implementation must implement both the full unrestricted ECMAScript language and the strict variant of the ECMAScript language as defined by this specification. In addition, an implementation must support the combination of unrestricted and strict mode source text units into a single composite program.</font>

为了符合本规范，ECMAScript实现必须同时实现本规范所定义的完整的无限制ECMAScript语言及其严格变体。此外，实现还必须支持将无限制模式和严格模式的源文本单元组合成一个单一的复合程序。



### 4.4 <font style="color:rgb(17, 17, 17);">Terms and Definitions 术语及定义</font>
<font style="color:rgb(17, 17, 17);">For the purposes of this document, the following terms and definitions apply.</font>

本文档中使用以下术语和定义。

#### 4.4.1 <font style="color:rgb(17, 17, 17);">implementation-approximated 近似实现</font>
<font style="color:rgb(17, 17, 17);">an </font>[<font style="color:rgb(32, 108, 167);">implementation-approximated</font>](https://tc39.es/ecma262/#implementation-approximated)<font style="color:rgb(17, 17, 17);"> facility is defined in whole or in part by an external source but has a recommended, ideal behaviour in this specification</font>

一种通过近似实现的功能，是指其全部或部分由外部来源定义，但在本规范中有推荐的理想行为。

#### 4.4.2 <font style="color:rgb(17, 17, 17);">implementation-defined 定义实现</font>
<font style="color:rgb(17, 17, 17);">an </font>[<font style="color:rgb(32, 108, 167);">implementation-defined</font>](https://tc39.es/ecma262/#implementation-defined)<font style="color:rgb(17, 17, 17);"> facility is defined in whole or in part by an external source to this specification</font>

由本规范之外的来源全部或部分定义的一种实现定义的设施。

#### <font style="color:rgb(17, 17, 17);">4.4.3 host-defined</font>
<font style="color:rgb(17, 17, 17);">same as </font>[<font style="color:rgb(32, 108, 167);">implementation-defined</font>](https://tc39.es/ecma262/#implementation-defined)

<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">Note: Editorially, see clause </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">4.2</font>](https://tc39.es/ecma262/#sec-hosts-and-implementations)<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">.</font>

与实现定义相同

> 注：编辑上，请参见第4.2条。
>

#### 4.4.4 type
<font style="color:rgb(17, 17, 17);">set of data values as defined in clause </font>[<font style="color:rgb(32, 108, 167);">6</font>](https://tc39.es/ecma262/#sec-ecmascript-data-types-and-values)

#### <font style="color:rgb(17, 17, 17);">4.4.5 primitive value 原始值</font>
<font style="color:rgb(17, 17, 17);">member of one of the types Undefined, Null, Boolean, Number, BigInt, Symbol, or String as defined in clause </font>[<font style="color:rgb(32, 108, 167);">6</font>](https://tc39.es/ecma262/#sec-ecmascript-data-types-and-values)

<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">Note: A primitive value is a datum that is represented directly at the lowest level of the language implementation.</font>

成员属于以下类型之一：Undefined、Null、布尔值(Boolean)、数字(Number)、BigInt、符号(Symbol)或字符串(String)，这些类型在第6条中定义。

> 注：原始值是在语言实现的最低级别直接表示的数据。
>

#### 4.4.6 <font style="color:rgb(17, 17, 17);">object 对象</font>
<font style="color:rgb(17, 17, 17);">member of the type Object</font>

<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">Note: An object is a collection of properties and has a single prototype object. The prototype may be null.</font>

#### <font style="color:rgb(17, 17, 17);">4.4.7 constructor 构造函数</font>
[<font style="color:rgb(32, 108, 167);">function object</font>](https://tc39.es/ecma262/#function-object)<font style="color:rgb(17, 17, 17);"> that creates and initializes objects</font>

<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">Note: The value of a </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">'s "prototype" property is a prototype object that is used to implement inheritance and shared properties.</font><font style="color:rgb(17, 17, 17);"></font>

函数对象，用于创建和初始化对象

> 注：构造函数的“prototype”属性的值是一个原型对象，用于实现继承和共享属性。
>

#### 4.4.8 <font style="color:rgb(17, 17, 17);">prototype 原型</font>
<font style="color:rgb(17, 17, 17);">object that provides shared properties for other objects</font>

<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">Note: When a </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);"> creates an object, that object implicitly references the </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">'s "prototype" property for the purpose of resolving property references. The </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">'s "prototype" property can be referenced by the program expression</font> `constructor.prototype`,<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);"> and properties added to an object's prototype are shared, through inheritance, by all objects sharing the prototype. Alternatively, a new object may be created with an explicitly specified prototype by using the </font>`Object.create`<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);"> built-in function.</font>

提供给其他对象共享属性的对象

> 注：当构造函数创建一个对象时，该对象会隐式地引用构造函数的“原型”属性来解析属性引用。可以通过程序表达式 `constructor.prototype` 来引用构造函数的“原型”属性，并且添加到对象原型中的属性将通过继承被所有共享该原型的对象所共享。或者，也可以使用 `Object.create` 内置函数以显式指定原型的方式创建新对象。
>

#### <font style="color:rgb(17, 17, 17);">4.4.9 ordinary object 普通对象</font>
<font style="color:rgb(17, 17, 17);">object that has the default behaviour for the essential internal methods that must be supported by all objects</font>

具有所有对象必须支持的基本内部方法的默认行为的对象。

#### 4.4.10 <font style="color:rgb(17, 17, 17);">exotic object 异质对象/特殊对象</font>
<font style="color:rgb(17, 17, 17);">object that does not have the default behaviour for one or more of the essential internal methods</font>

<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">Note: Any object that is not an </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">ordinary object</font>](https://tc39.es/ecma262/#ordinary-object)<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);"> is an </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">exotic object</font>](https://tc39.es/ecma262/#exotic-object)<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">.</font>

对象的一个或多个关键内部方法不具备默认行为。

> 注：任何不是普通对象的对象都称为特殊对象。
>

#### <font style="color:rgb(17, 17, 17);">4.4.11 standard object 标准对象</font>
<font style="color:rgb(17, 17, 17);">object whose semantics are defined by this specification</font>

该对象的语义由本规范定义。

#### 4.4.12 <font style="color:rgb(17, 17, 17);">built-in object 内置对象</font>
<font style="color:rgb(17, 17, 17);">object specified and supplied by an ECMAScript implementation</font>

<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">Note: Standard built-in objects are defined in this specification. An ECMAScript implementation may specify and supply additional kinds of built-in objects.</font>

由ECMAScript实现指定和提供的对象

> 注：标准内置对象在本规范中定义。ECMAScript实现可以指定并提供其他种类的内置对象。
>

#### 4.4.13 <font style="color:rgb(17, 17, 17);">undefined value 值undefined</font>
<font style="color:rgb(17, 17, 17);">primitive value used when a variable has not been assigned a value</font>

当变量未被赋值时使用的原始值。

#### 4.4.14 <font style="color:rgb(17, 17, 17);">Undefined type Undefined类型</font>
<font style="color:rgb(17, 17, 17);">type whose sole value is the </font>**<font style="color:rgb(17, 17, 17);">undefined</font>**<font style="color:rgb(17, 17, 17);"> value</font>

类型，其唯一值是**undefined**（这样的类型用来表示一个变量已经被声明但尚未被赋值的状态）

#### <font style="color:rgb(17, 17, 17);">4.4.15 null value 值null</font>
<font style="color:rgb(17, 17, 17);">primitive value that represents the intentional absence of any object value</font>

#### <font style="color:rgb(17, 17, 17);">4.4.16 Null type Null类型</font>
<font style="color:rgb(17, 17, 17);">type whose sole value is the </font>**<font style="color:rgb(17, 17, 17);">null</font>**<font style="color:rgb(17, 17, 17);"> value</font>

#### <font style="color:rgb(17, 17, 17);">4.4.17 Boolean value 布尔值</font>
<font style="color:rgb(17, 17, 17);">member of the </font>[<font style="color:rgb(32, 108, 167);">Boolean type</font>](https://tc39.es/ecma262/#sec-ecmascript-language-types-boolean-type)

<font style="background-color:rgb(233, 251, 233);">Note: There are only two Boolean values, </font>**<font style="background-color:rgb(233, 251, 233);">true</font>**<font style="background-color:rgb(233, 251, 233);"> and </font>**<font style="background-color:rgb(233, 251, 233);">false</font>**<font style="background-color:rgb(233, 251, 233);">.</font>

布尔类型的成员

> 注：只有两个布尔值成员，**true**和**false**
>

#### <font style="color:rgb(17, 17, 17);">4.4.18 Boolean type 布尔类型</font>
<font style="color:rgb(17, 17, 17);">type consisting of the primitive values </font>**<font style="color:rgb(17, 17, 17);">true</font>**<font style="color:rgb(17, 17, 17);"> and </font>**<font style="color:rgb(17, 17, 17);">false</font>**

类型由基本值 true 和 false 组成。

#### <font style="color:rgb(17, 17, 17);">4.4.19 Boolean object 布尔对象</font>
<font style="color:rgb(17, 17, 17);">member of the </font>[<font style="color:rgb(32, 108, 167);">Object type</font>](https://tc39.es/ecma262/#sec-object-type)<font style="color:rgb(17, 17, 17);"> that is an instance of the standard built-in Boolean </font>[<font style="color:rgb(32, 108, 167);">constructor</font>](https://tc39.es/ecma262/#constructor)

<font style="background-color:rgb(233, 251, 233);">Note: A Boolean object is created by using the Boolean </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="background-color:rgb(233, 251, 233);"> in a </font>`new`<font style="background-color:rgb(233, 251, 233);"> expression, supplying a Boolean value as an argument. The resulting object has an internal slot whose value is the Boolean value. A Boolean object can be coerced to a Boolean value.</font>

属于Object类型并且是标准内置Boolean构造函数的实例

> 注：通过在`new`表达式中使用Boolean构造函数并提供一个布尔值作为参数来创建Boolean对象。生成的对象具有一个内部槽，其值为该布尔值。Boolean对象可以被强制转换为布尔值。
>

#### <font style="color:rgb(17, 17, 17);">4.4.20 String value</font>
<font style="color:rgb(17, 17, 17);">primitive value that is a </font>[<font style="color:rgb(32, 108, 167);">finite</font>](https://tc39.es/ecma262/#finite)<font style="color:rgb(17, 17, 17);"> ordered sequence of zero or more 16-bit unsigned </font>[<font style="color:rgb(32, 108, 167);">integer</font>](https://tc39.es/ecma262/#integer)<font style="color:rgb(17, 17, 17);"> values</font>

<font style="background-color:rgb(233, 251, 233);">Note: A String value is a member of the </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">String type</font>](https://tc39.es/ecma262/#sec-ecmascript-language-types-string-type)<font style="background-color:rgb(233, 251, 233);">. Each </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">integer</font>](https://tc39.es/ecma262/#integer)<font style="background-color:rgb(233, 251, 233);"> value in the sequence usually represents a single 16-bit unit of UTF-16 text. However, ECMAScript does not place any restrictions or requirements on the values except that they must be 16-bit unsigned </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">integers</font>](https://tc39.es/ecma262/#integer)<font style="background-color:rgb(233, 251, 233);">.</font>

这是一个基本值，表示由零个或多个16位无符号整数组成的有限有序序列。

> 注：字符串值是字符串类型的一个成员。序列中的每个整数值通常代表UTF-16文本的一个16位单元。然而，ECMAScript对这些值没有任何限制或要求，除了它们必须是16位无符号整数。
>

#### <font style="color:rgb(17, 17, 17);">4.4.21 String type</font>
<font style="color:rgb(17, 17, 17);">set of all possible String values</font>

所有可能的字符串值的集合

#### <font style="color:rgb(17, 17, 17);">4.4.22 String object</font>
<font style="color:rgb(17, 17, 17);">member of the </font>[<font style="color:rgb(32, 108, 167);">Object type</font>](https://tc39.es/ecma262/#sec-object-type)<font style="color:rgb(17, 17, 17);"> that is an instance of the standard built-in String </font>[<font style="color:rgb(32, 108, 167);">constructor</font>](https://tc39.es/ecma262/#constructor)

<font style="background-color:rgb(233, 251, 233);">Note: A String object is created by using the String </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="background-color:rgb(233, 251, 233);"> in a </font>`new`<font style="background-color:rgb(233, 251, 233);"> expression, supplying a String value as an argument. The resulting object has an internal slot whose value is the String value. A String object can be coerced to a String value by calling the String </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="background-color:rgb(233, 251, 233);"> as a function (</font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">22.1.1.1</font>](https://tc39.es/ecma262/#sec-string-constructor-string-value)<font style="background-color:rgb(233, 251, 233);">).</font>

对象类型的一个成员，它是标准内置的String构造函数的实例。

> 注：通过在new表达式中使用String构造函数并提供一个字符串值作为参数来创建String对象。生成的对象有一个内部槽位，其值为该字符串值。可以通过将String构造函数作为函数调用来将String对象强制转换为字符串值（22.1.1.1）。
>

#### <font style="color:rgb(17, 17, 17);">4.4.23 Number value</font>
<font style="color:rgb(17, 17, 17);">primitive value corresponding to a double-precision 64-bit binary format </font>[<font style="color:rgb(32, 108, 167);">IEEE 754-2019</font>](https://tc39.es/ecma262/#sec-bibliography)<font style="color:rgb(17, 17, 17);"> value</font>

<font style="background-color:rgb(233, 251, 233);">Note: A Number value is a member of the </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">Number type</font>](https://tc39.es/ecma262/#sec-ecmascript-language-types-number-type)<font style="background-color:rgb(233, 251, 233);"> and is a direct representation of a number.</font>

与双精度64位二进制格式IEEE 754-2019值相对应的原始值  
注：Number值是Number类型的一个成员，是数字的直接表示。

#### <font style="color:rgb(17, 17, 17);">4.4.24 Number type</font>
<font style="color:rgb(17, 17, 17);">set of all possible Number values including </font>**<font style="color:rgb(17, 17, 17);">NaN</font>**<font style="color:rgb(17, 17, 17);"> (“not a number”), </font>**<font style="color:rgb(17, 17, 17);">+∞</font>**<sub><font style="color:rgb(17, 17, 17);">𝔽</font></sub><font style="color:rgb(17, 17, 17);"> (positive infinity), and </font>**<font style="color:rgb(17, 17, 17);">-∞</font>**<sub><font style="color:rgb(17, 17, 17);">𝔽</font></sub><font style="color:rgb(17, 17, 17);"> (negative infinity)</font>

所有可能的数字值的集合，包括NaN（“非数字”）、+∞𝔽（正无穷大）和-∞𝔽（负无穷大）。

#### <font style="color:rgb(17, 17, 17);">4.4.25 Number object</font>
<font style="color:rgb(17, 17, 17);">member of the </font>[<font style="color:rgb(32, 108, 167);">Object type</font>](https://tc39.es/ecma262/#sec-object-type)<font style="color:rgb(17, 17, 17);"> that is an instance of the standard built-in Number </font>[<font style="color:rgb(32, 108, 167);">constructor</font>](https://tc39.es/ecma262/#constructor)

<font style="background-color:rgb(233, 251, 233);">Note: A Number object is created by using the Number </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="background-color:rgb(233, 251, 233);"> in a </font>`new`<font style="background-color:rgb(233, 251, 233);"> expression, supplying a Number value as an argument. The resulting object has an internal slot whose value is the Number value. A Number object can be coerced to a Number value by calling the Number </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructor</font>](https://tc39.es/ecma262/#constructor)<font style="background-color:rgb(233, 251, 233);"> as a function (</font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">21.1.1.1</font>](https://tc39.es/ecma262/#sec-number-constructor-number-value)<font style="background-color:rgb(233, 251, 233);">).</font>

属于Object类型的一个成员，它是标准内置Number构造函数的实例。

> 注：通过在new表达式中使用Number构造函数并提供一个数字值作为参数来创建Number对象。生成的对象有一个内部槽位，其值为该数字值。可以通过将Number构造函数作为函数调用来将Number对象强制转换为数字值（21.1.1.1）。
>

#### <font style="color:rgb(17, 17, 17);">4.4.26 Infinity</font>
<font style="color:rgb(17, 17, 17);">Number value that is the positive infinite Number value</font>

数值，表示正无穷大的数值。

#### <font style="color:rgb(17, 17, 17);">4.4.27 NaN</font>
<font style="color:rgb(17, 17, 17);">Number value that is an </font>[<font style="color:rgb(32, 108, 167);">IEEE 754-2019</font>](https://tc39.es/ecma262/#sec-bibliography)<font style="color:rgb(17, 17, 17);"> NaN (“not a number”) value</font>

数值是符合IEEE 754-2019标准的NaN（“非数字”）值。

#### <font style="color:rgb(17, 17, 17);">4.4.28 BigInt value</font>
<font style="color:rgb(17, 17, 17);">primitive value corresponding to an arbitrary-precision </font>[<font style="color:rgb(32, 108, 167);">integer</font>](https://tc39.es/ecma262/#integer)<font style="color:rgb(17, 17, 17);"> value</font>

与任意精度整数值相对应的原始值

#### <font style="color:rgb(17, 17, 17);">4.4.29 BigInt type</font>
<font style="color:rgb(17, 17, 17);">set of all possible BigInt values</font>

所有可能的BigInt值的集合

#### <font style="color:rgb(17, 17, 17);">4.4.30 BigInt object</font>
<font style="color:rgb(17, 17, 17);">member of the </font>[<font style="color:rgb(32, 108, 167);">Object type</font>](https://tc39.es/ecma262/#sec-object-type)<font style="color:rgb(17, 17, 17);"> that is an instance of the standard built-in BigInt </font>[<font style="color:rgb(32, 108, 167);">constructor</font>](https://tc39.es/ecma262/#constructor)

标准内置 BigInt 构造函数的实例，属于 Object 类型的成员。

#### <font style="color:rgb(17, 17, 17);">4.4.31 Symbol value</font>
<font style="color:rgb(17, 17, 17);">primitive value that represents a unique, non-String Object </font>[<font style="color:rgb(32, 108, 167);">property key</font>](https://tc39.es/ecma262/#property-key)

表示唯一且非字符串的对象属性键的原始值。

#### <font style="color:rgb(17, 17, 17);">4.4.32 Symbol type</font>
<font style="color:rgb(17, 17, 17);">set of all possible Symbol values</font>

所有可能的符号值的集合

#### <font style="color:rgb(17, 17, 17);">4.4.33 Symbol object</font>
<font style="color:rgb(17, 17, 17);">member of the </font>[<font style="color:rgb(32, 108, 167);">Object type</font>](https://tc39.es/ecma262/#sec-object-type)<font style="color:rgb(17, 17, 17);"> that is an instance of the standard built-in Symbol </font>[<font style="color:rgb(32, 108, 167);">constructor</font>](https://tc39.es/ecma262/#constructor)

标准内置Symbol构造函数的实例的对象类型成员  
译注：这里的意思是指某个对象是通过JavaScript中的标准内置`Symbol()`构造函数创建出来的实例。在JavaScript中，`Symbol`是一种原始数据类型，用于生成唯一的标识符。当你使用`Symbol()`构造函数时，它会返回一个新的、独一无二的`Symbol`值。如果一个对象是由这个构造函数产生的，那么这个对象就可以被描述为"标准内置Symbol构造函数的实例"。不过，需要注意的是，直接由`Symbol`构造函数创建的结果实际上是一个`symbol`类型的值，而不是一个对象；但可以通过`Object()`将其转换成对象形式。

#### <font style="color:rgb(17, 17, 17);">4.4.34 function</font>
<font style="color:rgb(17, 17, 17);">member of the </font>[<font style="color:rgb(32, 108, 167);">Object type</font>](https://tc39.es/ecma262/#sec-object-type)<font style="color:rgb(17, 17, 17);"> that may be invoked as a subroutine</font>

<font style="background-color:rgb(233, 251, 233);">Note: In addition to its properties, a function contains executable code and state that determine how it behaves when invoked. A function's code may or may not be written in ECMAScript.</font>

可以作为子程序调用的对象类型成员

> 注：除了其属性外，函数还包含可执行代码和状态，这些决定了它被调用时的行为。函数的代码可以是也可以不是用ECMAScript编写的。
>

#### <font style="color:rgb(17, 17, 17);">4.4.35 built-in function 内置函数</font>
<font style="color:rgb(17, 17, 17);">built-in object that is a function</font>

<font style="background-color:rgb(233, 251, 233);">Note: Examples of built-in functions include </font>`parseInt`<font style="background-color:rgb(233, 251, 233);"> and </font>`Math.exp`<font style="background-color:rgb(233, 251, 233);">. A </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">host</font>](https://tc39.es/ecma262/#host)<font style="background-color:rgb(233, 251, 233);"> or implementation may provide additional built-in functions that are not described in this specification.</font>

内置对象，即函数。

> 注意：内置函数的例子包括 `parseInt` 和 `Math.exp`。宿主环境或实现可能提供本规范中未描述的其他内置函数。
>

#### <font style="color:rgb(17, 17, 17);">4.4.36 built-in constructor 内置构造函数</font>
<font style="color:rgb(17, 17, 17);">built-in function that is a </font>[<font style="color:rgb(32, 108, 167);">constructor</font>](https://tc39.es/ecma262/#constructor)

<font style="background-color:rgb(233, 251, 233);">Note: Examples of built-in </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructors</font>](https://tc39.es/ecma262/#constructor)<font style="background-color:rgb(233, 251, 233);"> include </font>`**<font style="background-color:rgb(233, 251, 233);">Object</font>**`<font style="background-color:rgb(233, 251, 233);"> and </font>`**<font style="background-color:rgb(233, 251, 233);">Function</font>**`<font style="background-color:rgb(233, 251, 233);">. A </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">host</font>](https://tc39.es/ecma262/#host)<font style="background-color:rgb(233, 251, 233);"> or implementation may provide additional built-in </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">constructors</font>](https://tc39.es/ecma262/#constructor)<font style="background-color:rgb(233, 251, 233);"> that are not described in this specification.</font>

内置的构造函数

> 注：内置构造函数的例子包括 Object 和 Function。宿主或实现可能提供本规范中未描述的其他内置构造函数。
>

#### <font style="color:rgb(17, 17, 17);">4.4.37 property 属性</font>
<font style="color:rgb(17, 17, 17);">part of an object that associates a key (either a String value or a Symbol value) and a value</font>

<font style="background-color:rgb(233, 251, 233);">Note: Depending upon the form of the property the value may be represented either directly as a data value (a primitive value, an object, or a </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">function object</font>](https://tc39.es/ecma262/#function-object)<font style="background-color:rgb(233, 251, 233);">) or indirectly by a pair of accessor functions.</font>

对象的一部分，它将一个键（字符串值或符号值）与一个值关联起来。

> 注：根据属性的形式，该值可以直接表示为数据值（原始值、对象或函数对象），也可以通过一对访问器函数间接表示。
>

#### <font style="color:rgb(17, 17, 17);">4.4.38 method</font>
<font style="color:rgb(17, 17, 17);">function that is the value of a property</font>

<font style="background-color:rgb(233, 251, 233);">Note：When a function is called as a method of an object, the object is passed to the function as its </font>**<font style="background-color:rgb(233, 251, 233);">this</font>**<font style="background-color:rgb(233, 251, 233);"> value.</font>

函数作为属性的值

> 注：当一个函数被作为对象的方法调用时，该对象会作为`this`值传递给这个函数。
>

#### <font style="color:rgb(17, 17, 17);">4.4.39 built-in method 内置方法</font>
<font style="color:rgb(17, 17, 17);">method that is a built-in function</font>

<font style="background-color:rgb(233, 251, 233);">Note: Standard built-in methods are defined in this specification. A </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">host</font>](https://tc39.es/ecma262/#host)<font style="background-color:rgb(233, 251, 233);"> or implementation may provide additional built-in methods that are not described in this specification.</font>

方法即为内置函数

> 注：标准的内置方法在此规范中定义。宿主或实现方可以提供本规范中未描述的额外内置方法。
>

#### <font style="color:rgb(17, 17, 17);">4.4.40 attribute 特性</font>
<font style="color:rgb(17, 17, 17);">internal value that defines some characteristic of a property</font>

内部值，用于定义属性的某个特征。

#### <font style="color:rgb(17, 17, 17);">4.4.41 own property</font>
<font style="color:rgb(17, 17, 17);">property that is directly contained by its object</font>

直接由其对象包含的属性

#### <font style="color:rgb(17, 17, 17);">4.4.42 inherited property</font>
<font style="color:rgb(17, 17, 17);">property of an object that is not an own property but is a property (either own or inherited) of the object's prototype</font>

对象的一个属性，这个属性不是对象自身的属性，而是对象原型（无论是自身拥有还是继承来的）的属性。



### <font style="color:rgb(17, 17, 17);">4.5 本规范的组成 Organization of This Specification</font>
<font style="color:rgb(17, 17, 17);">The remainder of this specification is organized as follows:</font>

<font style="color:rgb(17, 17, 17);">Clause</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">5</font>](https://tc39.es/ecma262/#sec-notational-conventions)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">defines the notational conventions used throughout the specification.</font>

<font style="color:rgb(17, 17, 17);">Clauses</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">6</font>](https://tc39.es/ecma262/#sec-ecmascript-data-types-and-values)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">through</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">10</font>](https://tc39.es/ecma262/#sec-ordinary-and-exotic-objects-behaviours)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">define the execution environment within which ECMAScript programs operate.</font>

<font style="color:rgb(17, 17, 17);">Clauses</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">11</font>](https://tc39.es/ecma262/#sec-ecmascript-language-source-code)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">through</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">17</font>](https://tc39.es/ecma262/#sec-error-handling-and-language-extensions)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">define the actual ECMAScript programming language including its syntactic encoding and the execution semantics of all language features.</font>

<font style="color:rgb(17, 17, 17);">Clauses</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">18</font>](https://tc39.es/ecma262/#sec-ecmascript-standard-built-in-objects)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">through</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">28</font>](https://tc39.es/ecma262/#sec-reflection)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">define the ECMAScript standard library. They include the definitions of all of the standard objects that are available for use by ECMAScript programs as they execute.</font>

<font style="color:rgb(17, 17, 17);">Clause </font>[<font style="color:rgb(32, 108, 167);">29</font>](https://tc39.es/ecma262/#sec-memory-model)<font style="color:rgb(17, 17, 17);"> describes the memory consistency model of accesses on SharedArrayBuffer-backed memory and methods of the Atomics object.</font><font style="color:rgb(17, 17, 17);"></font>

本规范的其余部分组织如下：  
第5条定义了整个规范中使用的标记约定。  
**<font style="color:#DF2A3F;">第6至10条定义了ECMAScript程序运行的执行环境。  
</font>****<font style="color:#DF2A3F;">第11至17条定义了实际的ECMAScript编程语言，包括其语法编码和所有语言特性的执行语义。  
</font>****<font style="color:#DF2A3F;">第18至28条定义了ECMAScript标准库。它们包含了ECMAScript程序在执行过程中可用的所有标准对象的定义。</font>**  
第29条描述了基于SharedArrayBuffer的内存访问的记忆一致性模型以及Atomics对象的方法。



## 5 符号约定 Notational Conventions
### <font style="color:rgb(17, 17, 17);">5.1 Syntactic and Lexical Grammars</font>
#### <font style="color:rgb(17, 17, 17);">5.1.1 上下文无关文法 Context-Free Grammars </font>
<font style="color:rgb(17, 17, 17);">A </font>_<font style="color:rgb(17, 17, 17);">context-free grammar</font>_<font style="color:rgb(17, 17, 17);"> consists of a number of </font>_<font style="color:rgb(17, 17, 17);">productions</font>_<font style="color:rgb(17, 17, 17);">. Each production has an abstract symbol called a </font>_<font style="color:rgb(17, 17, 17);">nonterminal</font>_<font style="color:rgb(17, 17, 17);"> as its </font>_<font style="color:rgb(17, 17, 17);">left-hand side</font>_<font style="color:rgb(17, 17, 17);">, and a sequence of zero or more nonterminal and </font>_<font style="color:rgb(17, 17, 17);">terminal</font>_<font style="color:rgb(17, 17, 17);"> symbols as its </font>_<font style="color:rgb(17, 17, 17);">right-hand side</font>_<font style="color:rgb(17, 17, 17);">. For each grammar, the terminal symbols are drawn from a specified alphabet.</font>

上下文无关文法由多个产生式组成。每个产生式左边是一个称为非终结符的抽象符号，右边是由零个或多个非终结符和终结符组成的序列。对于每种文法，其终结符都来自一个指定的字母表。



<font style="color:rgb(17, 17, 17);">A</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">chain production</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">is a production that has exactly one nonterminal symbol on its right-hand side along with zero or more terminal symbols.</font>

链式产生式是指在其右侧仅有一个非终结符号以及零个或多个终结符号的产生式。



<font style="color:rgb(17, 17, 17);">Starting from a sentence consisting of a single distinguished nonterminal, called the goal symbol, a given context-free grammar specifies a </font>_<font style="color:rgb(17, 17, 17);">language</font>_<font style="color:rgb(17, 17, 17);">, namely, the (perhaps infinite) set of possible sequences of terminal symbols that can result from repeatedly replacing any nonterminal in the sequence with a right-hand side of a production for which the nonterminal is the left-hand side.</font>

从一个仅包含一个特定非终结符（称为目标符号）的句子开始，给定的上下文无关文法定义了一种语言，即通过反复将序列中的任何非终结符替换为该非终结符作为左部的产生式的右部所能得到的所有可能的终结符序列的集合（这个集合可能是无限的）。



#### <font style="color:rgb(17, 17, 17);">5.1.2 词法文法和正则表达式语法 The Lexical and RegExp Grammars </font>
<font style="color:rgb(17, 17, 17);">A </font>_<font style="color:rgb(17, 17, 17);">lexical grammar</font>_<font style="color:rgb(17, 17, 17);"> for ECMAScript is given in clause </font>[<font style="color:rgb(32, 108, 167);">12</font>](https://tc39.es/ecma262/#sec-ecmascript-language-lexical-grammar)<font style="color:rgb(17, 17, 17);">. This grammar has as its terminal symbols Unicode code points that conform to the rules for </font>[_<font style="color:rgb(51, 51, 51);">SourceCharacter</font>_](https://tc39.es/ecma262/#prod-SourceCharacter)<font style="color:rgb(17, 17, 17);"> defined in </font>[<font style="color:rgb(32, 108, 167);">11.1</font>](https://tc39.es/ecma262/#sec-source-text)<font style="color:rgb(17, 17, 17);">. It defines a set of productions, starting from the </font>[<font style="color:rgb(32, 108, 167);">goal symbol</font>](https://tc39.es/ecma262/#sec-context-free-grammars)<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">InputElementDiv</font>_](https://tc39.es/ecma262/#prod-InputElementDiv)<font style="color:rgb(17, 17, 17);">, </font>[_<font style="color:rgb(51, 51, 51);">InputElementTemplateTail</font>_](https://tc39.es/ecma262/#prod-InputElementTemplateTail)<font style="color:rgb(17, 17, 17);">, </font>[_<font style="color:rgb(51, 51, 51);">InputElementRegExp</font>_](https://tc39.es/ecma262/#prod-InputElementRegExp)<font style="color:rgb(17, 17, 17);">, </font>[_<font style="color:rgb(51, 51, 51);">InputElementRegExpOrTemplateTail</font>_](https://tc39.es/ecma262/#prod-InputElementRegExpOrTemplateTail)<font style="color:rgb(17, 17, 17);">, or </font>[_<font style="color:rgb(51, 51, 51);">InputElementHashbangOrRegExp</font>_](https://tc39.es/ecma262/#prod-InputElementHashbangOrRegExp)<font style="color:rgb(17, 17, 17);">, that describe how sequences of such code points are translated into a sequence of input elements.</font>

ECMAScript的词法文法在第12条中给出。该文法的终结符号是符合11.1节中定义的SourceCharacter规则的Unicode码点。它定义了一组产生式，从目标符号InputElementDiv、InputElementTemplateTail、InputElementRegExp、InputElementRegExpOrTemplateTail或InputElementHashbangOrRegExp开始，描述了这些码点序列是如何被转换成输入元素序列的。



<font style="color:rgb(17, 17, 17);">Input elements other than white space and comments form the terminal symbols for the syntactic grammar for ECMAScript and are called ECMAScript </font>_<font style="color:rgb(17, 17, 17);">tokens</font>_<font style="color:rgb(17, 17, 17);">. These tokens are the </font>[<font style="color:rgb(32, 108, 167);">reserved words</font>](https://tc39.es/ecma262/#sec-keywords-and-reserved-words)<font style="color:rgb(17, 17, 17);">, identifiers, literals, and punctuators of the ECMAScript language. Moreover, line terminators, although not considered to be tokens, also become part of the stream of input elements and guide the process of automatic semicolon insertion (</font>[<font style="color:rgb(32, 108, 167);">12.10</font>](https://tc39.es/ecma262/#sec-automatic-semicolon-insertion)<font style="color:rgb(17, 17, 17);">). Simple white space and single-line comments are discarded and do not appear in the stream of input elements for the syntactic grammar. A </font>[_<font style="color:rgb(51, 51, 51);">MultiLineComment</font>_](https://tc39.es/ecma262/#prod-MultiLineComment)<font style="color:rgb(17, 17, 17);"> (that is, a comment of the form </font>`**/***`<font style="color:rgb(17, 17, 17);">…</font>`***/**`**<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">regardless of whether it spans more than one line) is likewise simply discarded if it contains no line terminator; but if a </font>[_<font style="color:rgb(51, 51, 51);">MultiLineComment</font>_](https://tc39.es/ecma262/#prod-MultiLineComment)<font style="color:rgb(17, 17, 17);"> contains one or more line terminators, then it is replaced by a single line terminator, which becomes part of the stream of input elements for the syntactic grammar.</font>

除了空白字符和注释之外的输入元素构成了ECMAScript语法的终结符，并被称为ECMAScript标记。这些标记是ECMAScript语言中的保留字、标识符、字面量和标点符号。此外，尽管行终止符不被视为标记，但它们也成为了输入元素流的一部分，并指导自动分号插入的过程（12.10）。简单的空白字符和单行注释将被丢弃，不会出现在语法分析的输入元素流中。多行注释（即形式为/_…_/的注释，无论它是否跨越多行）如果其中不包含行终止符，则同样会被简单地丢弃；但如果一个多行注释包含一个或多个行终止符，则该注释会被替换为一个单独的行终止符，这个行终止符将成为语法分析输入元素流的一部分。



<font style="color:rgb(17, 17, 17);">A</font><font style="color:rgb(17, 17, 17);"> </font>_<font style="color:rgb(17, 17, 17);">RegExp grammar</font>_<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">for ECMAScript is given in</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">22.2.1</font>](https://tc39.es/ecma262/#sec-patterns)<font style="color:rgb(17, 17, 17);">. This grammar also has as its terminal symbols the code points as defined by</font><font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">SourceCharacter</font>_](https://tc39.es/ecma262/#prod-SourceCharacter)<font style="color:rgb(17, 17, 17);">. It defines a set of productions, starting from the</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">goal symbol</font>](https://tc39.es/ecma262/#sec-context-free-grammars)<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">Pattern</font>_](https://tc39.es/ecma262/#prod-Pattern)<font style="color:rgb(17, 17, 17);">, that describe how sequences of code points are translated into regular expression patterns.</font>

<font style="color:rgb(17, 17, 17);">Productions of the lexical and RegExp grammars are distinguished by having two colons “</font>**<font style="color:rgb(17, 17, 17);">::</font>**<font style="color:rgb(17, 17, 17);">” as separating punctuation. The lexical and RegExp grammars share some productions.</font>

ECMAScript 的正则表达式语法在 22.2.1 节中给出。该语法的终结符是 SourceCharacter 定义的代码点。它定义了一组以目标符号 Pattern 开始的产生式，描述了代码点序列如何被转换成正则表达式模式。  
词法和正则表达式语法的产生式通过使用两个冒号“::”作为分隔标点来加以区分。词法和正则表达式语法共享一些产生式。

#### <font style="color:rgb(17, 17, 17);">5.1.3 数值字符串语法 The Numeric String Grammar </font>
<font style="color:rgb(17, 17, 17);">A </font>_<font style="color:rgb(17, 17, 17);">numeric string grammar</font>_<font style="color:rgb(17, 17, 17);"> appears in </font>[<font style="color:rgb(32, 108, 167);">7.1.4.1</font>](https://tc39.es/ecma262/#sec-tonumber-applied-to-the-string-type)<font style="color:rgb(17, 17, 17);">. It has as its terminal symbols </font>[_<font style="color:rgb(51, 51, 51);">SourceCharacter</font>_](https://tc39.es/ecma262/#prod-SourceCharacter)<font style="color:rgb(17, 17, 17);">, and is used for translating Strings into numeric values starting from the </font>[<font style="color:rgb(32, 108, 167);">goal symbol</font>](https://tc39.es/ecma262/#sec-context-free-grammars)<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">StringNumericLiteral</font>_](https://tc39.es/ecma262/#prod-StringNumericLiteral)<font style="color:rgb(17, 17, 17);"> (which is similar to but distinct from the </font>[<font style="color:rgb(32, 108, 167);">lexical grammar for numeric literals</font>](https://tc39.es/ecma262/#sec-literals-numeric-literals)<font style="color:rgb(17, 17, 17);">).</font>

<font style="color:rgb(17, 17, 17);">Productions of the numeric string grammar are distinguished by having three colons “</font>**<font style="color:rgb(17, 17, 17);">:::</font>**<font style="color:rgb(17, 17, 17);">” as punctuation, and are never used for parsing source text.</font>

数值字符串语法出现在7.1.4.1节中。它的终结符是SourceCharacter，用于将字符串从目标符号StringNumericLiteral开始转换为数值（这与数值字面量的词法语法相似但不同）。  
数值字符串语法的产生式通过使用三个冒号“:::”作为标点来区分，并且从不用于解析源文本。

#### <font style="color:rgb(17, 17, 17);">5.1.4  句法语法 The Syntactic Grammar</font>
<font style="color:rgb(17, 17, 17);">The </font>_<font style="color:rgb(17, 17, 17);">syntactic grammar</font>_<font style="color:rgb(17, 17, 17);"> for ECMAScript is given in clauses </font>[<font style="color:rgb(32, 108, 167);">13</font>](https://tc39.es/ecma262/#sec-ecmascript-language-expressions)<font style="color:rgb(17, 17, 17);"> through </font>[<font style="color:rgb(32, 108, 167);">16</font>](https://tc39.es/ecma262/#sec-ecmascript-language-scripts-and-modules)<font style="color:rgb(17, 17, 17);">. This grammar has ECMAScript tokens defined by the lexical grammar as its terminal symbols (</font>[<font style="color:rgb(32, 108, 167);">5.1.2</font>](https://tc39.es/ecma262/#sec-lexical-and-regexp-grammars)<font style="color:rgb(17, 17, 17);">). It defines a set of productions, starting from two alternative </font>[<font style="color:rgb(32, 108, 167);">goal symbols</font>](https://tc39.es/ecma262/#sec-context-free-grammars)<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">Script</font>_](https://tc39.es/ecma262/#prod-Script)<font style="color:rgb(17, 17, 17);"> and </font>[_<font style="color:rgb(51, 51, 51);">Module</font>_](https://tc39.es/ecma262/#prod-Module)<font style="color:rgb(17, 17, 17);">, that describe how sequences of tokens form syntactically correct independent components of ECMAScript programs.</font>

<font style="color:rgb(17, 17, 17);">When a stream of code points is to be parsed as an ECMAScript</font><font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">Script</font>_](https://tc39.es/ecma262/#prod-Script)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">or</font><font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">Module</font>_](https://tc39.es/ecma262/#prod-Module)<font style="color:rgb(17, 17, 17);">, it is first converted to a stream of input elements by repeated application of the lexical grammar; this stream of input elements is then parsed by a single application of the syntactic grammar. The input stream is syntactically in error if the tokens in the stream of input elements cannot be parsed as a single instance of the goal nonterminal (</font>[_<font style="color:rgb(51, 51, 51);">Script</font>_](https://tc39.es/ecma262/#prod-Script)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">or</font><font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">Module</font>_](https://tc39.es/ecma262/#prod-Module)<font style="color:rgb(17, 17, 17);">), with no tokens left over.</font>

ECMAScript的句法语法在第13至16条中给出。该语法将由词法语法定义的ECMAScript记号作为其终结符号（5.1.2）。它定义了一组产生式，从两个可选的目标符号Script和Module开始，描述了这些记号序列如何构成ECMAScript程序中语法正确的独立组件。  
当一串代码点需要被解析为ECMAScript Script或Module时，首先通过反复应用词法语法将其转换为输入元素流；然后这个输入元素流通过一次句法语法的应用被解析。如果输入元素流中的记号不能作为一个单独的目标非终结符（Script或Module）实例被解析，并且没有剩余的记号，则认为输入流在句法上是错误的。



<font style="color:rgb(17, 17, 17);">When a parse is successful, it constructs a</font><font style="color:rgb(17, 17, 17);"> </font>_<font style="color:rgb(17, 17, 17);">parse tree</font>_<font style="color:rgb(17, 17, 17);">, a rooted tree structure in which each node is a</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">Parse Node</font><font style="color:rgb(17, 17, 17);">. Each Parse Node is an</font><font style="color:rgb(17, 17, 17);"> </font>_<font style="color:rgb(17, 17, 17);">instance</font>_<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">of a symbol in the grammar; it represents a span of the source text that can be derived from that symbol. The root node of the parse tree, representing the whole of the source text, is an instance of the parse's</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">goal symbol</font>](https://tc39.es/ecma262/#sec-context-free-grammars)<font style="color:rgb(17, 17, 17);">. When a Parse Node is an instance of a nonterminal, it is also an instance of some production that has that nonterminal as its left-hand side. Moreover, it has zero or more</font><font style="color:rgb(17, 17, 17);"> </font>_<font style="color:rgb(17, 17, 17);">children</font>_<font style="color:rgb(17, 17, 17);">, one for each symbol on the production's right-hand side: each child is a Parse Node that is an instance of the corresponding symbol.</font>

<font style="color:rgb(17, 17, 17);">New Parse Nodes are instantiated for each invocation of the parser and never reused between parses even of identical source text. Parse Nodes are considered the same Parse Node if and only if they represent the same span of source text, are instances of the same grammar symbol, and resulted from the same parser invocation.</font>

当解析成功时，它会构建一个解析树，这是一个有根的树结构，其中每个节点都是一个解析节点。每个解析节点是语法中某个符号的一个实例；它代表可以从该符号派生出的源文本的一部分。解析树的根节点代表整个源文本，是解析的目标符号的一个实例。当一个解析节点是非终结符的实例时，它也是某个以该非终结符为左侧符号的产生式的实例。此外，它有零个或多个子节点，对应于产生式右侧的每个符号：每个子节点都是相应符号的一个解析节点。  
每次调用解析器时都会为新创建的解析节点实例化，并且即使是对相同的源文本进行解析，这些节点也不会在不同的解析之间重用。只有当解析节点表示相同的源文本部分、是相同语法符号的实例并且来自同一解析器调用时，才认为它们是同一个解析节点。



<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">Note 1：Parsing the same String multiple times will lead to different Parse Nodes. For example, consider: Each call to </font>`eval`<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);"> converts the value of </font>`str`<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);"> into </font>[<font style="color:rgb(32, 108, 167);background-color:rgb(233, 251, 233);">ECMAScript source text</font>](https://tc39.es/ecma262/#sec-source-text)<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);"> and performs an independent parse that creates its own separate tree of Parse Nodes. The trees are distinct even though each parse operates upon a source text that was derived from the same String value.</font>

> 注1：多次解析同一个字符串将会导致生成不同的解析节点。例如，请考虑以下情况：
>
> 每次调用 `eval` 都会将字符串 `str` 的值转换为 ECMAScript 源文本，并执行独立的解析以创建自己的解析节点树。即使每个解析操作基于的源文本都源自同一个字符串值，这些解析树也是不同的。
>

```plain
let str = "1 + 1;";
eval(str);
eval(str);
```

<font style="color:rgb(17, 17, 17);background-color:rgb(233, 251, 233);">Note 2：Parse Nodes are specification artefacts, and implementations are not required to use an analogous data structure.</font>

> 注2：解析节点只是规范中的概念性产物，实现并不需要使用类似的数据结构。
>



<font style="color:rgb(17, 17, 17);">Productions of the syntactic grammar are distinguished by having just one colon “</font>**<font style="color:rgb(17, 17, 17);">:</font>**<font style="color:rgb(17, 17, 17);">” as punctuation.</font>

<font style="color:rgb(17, 17, 17);">The syntactic grammar as presented in clauses </font>[<font style="color:rgb(32, 108, 167);">13</font>](https://tc39.es/ecma262/#sec-ecmascript-language-expressions)<font style="color:rgb(17, 17, 17);"> through </font>[<font style="color:rgb(32, 108, 167);">16</font>](https://tc39.es/ecma262/#sec-ecmascript-language-scripts-and-modules)<font style="color:rgb(17, 17, 17);"> is not a complete account of which token sequences are accepted as a correct ECMAScript </font>[_<font style="color:rgb(51, 51, 51);">Script</font>_](https://tc39.es/ecma262/#prod-Script)<font style="color:rgb(17, 17, 17);"> or </font>[_<font style="color:rgb(51, 51, 51);">Module</font>_](https://tc39.es/ecma262/#prod-Module)<font style="color:rgb(17, 17, 17);">. Certain additional token sequences are also accepted, namely, those that would be described by the grammar if only semicolons were added to the sequence in certain places (such as before line terminator characters). Furthermore, certain token sequences that are described by the grammar are not considered acceptable if a line terminator character appears in certain “awkward”places.</font>

<font style="color:rgb(17, 17, 17);">In certain cases, in order to avoid ambiguities, the syntactic grammar uses generalized productions that permit token sequences that do not form a valid ECMAScript</font><font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">Script</font>_](https://tc39.es/ecma262/#prod-Script)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">or</font><font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">Module</font>_](https://tc39.es/ecma262/#prod-Module)<font style="color:rgb(17, 17, 17);">. For example, this technique is used for object literals and object destructuring patterns. In such cases a more restrictive</font><font style="color:rgb(17, 17, 17);"> </font>_<font style="color:rgb(17, 17, 17);">supplemental grammar</font>_<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">is provided that further restricts the acceptable token sequences. Typically, an</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">early error</font>](https://tc39.es/ecma262/#early-error)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">rule will then state that, in certain contexts, "</font><font style="color:rgb(33, 131, 121);">P</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">must cover</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">an</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">N</font><font style="color:rgb(17, 17, 17);">", where</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">P</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">is a Parse Node (an instance of the generalized production) and</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">N</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">is a nonterminal from the supplemental grammar. This means:</font>

1. <font style="color:rgb(17, 17, 17);">The sequence of tokens originally matched by</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">P</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">is parsed again using</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">N</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">as the</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">goal symbol</font>](https://tc39.es/ecma262/#sec-context-free-grammars)<font style="color:rgb(17, 17, 17);">. If</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">N</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">takes grammatical parameters, then they are set to the same values used when</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">P</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">was originally parsed.</font>
2. <font style="color:rgb(17, 17, 17);">If the sequence of tokens can be parsed as a single instance of</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">N</font><font style="color:rgb(17, 17, 17);">, with no tokens left over, then:</font>
    1. <font style="color:rgb(17, 17, 17);">We refer to that instance of</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">N</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">(a Parse Node, unique for a given</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">P</font><font style="color:rgb(17, 17, 17);">) as "the</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">N</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">that is</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">covered</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">by</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">P</font><font style="color:rgb(17, 17, 17);">".</font>
    2. <font style="color:rgb(17, 17, 17);">All Early Error rules for</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">N</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">and its derived productions also apply to the</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">N</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">that is covered by</font><font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(33, 131, 121);">P</font><font style="color:rgb(17, 17, 17);">.</font>
3. <font style="color:rgb(17, 17, 17);">Otherwise (if the parse fails), it is an early Syntax Error.</font>

句法语法的产生式通过只有一个冒号“:”作为标点来区分。  
在第13至16条中呈现的句法语法并不是对哪些标记序列可以被接受为正确的ECMAScript脚本或模块的完整描述。某些额外的标记序列也被接受，即那些如果在某些位置（例如行终止符之前）添加分号后能符合语法要求的序列。此外，如果行终止符出现在某些“尴尬”的位置，即使这些标记序列符合语法要求，也不会被认为是可接受的。  
在某些情况下，为了避免歧义，句法语法使用了泛化的产生式，允许一些不构成有效ECMAScript脚本或模块的标记序列。例如，这种技术用于对象字面量和对象解构模式。在这种情况下，会提供一个更为严格的补充语法来进一步限制可接受的标记序列。通常，一条早期错误规则将声明，在某些上下文中，“P必须覆盖N”，其中P是解析节点（泛化产生式的实例），而N是补充语法中的非终结符。这意味着：

1. 由P最初匹配的标记序列将再次以N为目标符号进行解析。如果N需要语法参数，则这些参数设置为与P最初解析时相同的值。
2. 如果该标记序列能够被解析为单个N实例，并且没有剩余的标记，则：  
a. 我们称那个N实例（对于给定的P是唯一的解析节点）为“被P覆盖的N”。  
b. N及其派生产生式的所有早期错误规则也适用于被P覆盖的N。
3. 否则（如果解析失败），则是一个早期语法错误。

#### 5.1.5 <font style="color:rgb(17, 17, 17);">Grammar Notation</font>
##### <font style="color:rgb(17, 17, 17);">5.1.5.1 Terminal Symbols</font>
<font style="color:rgb(17, 17, 17);">In the ECMAScript grammars, some terminal symbols are shown in </font>`**fixed-width**`<font style="color:rgb(17, 17, 17);"> font. These are to appear in a source text exactly as written. All terminal symbol code points specified in this way are to be understood as the appropriate Unicode code points from the Basic Latin block, as opposed to any similar-looking code points from other Unicode ranges. A code point in a terminal symbol cannot be expressed by a </font>`**\**`<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">UnicodeEscapeSequence</font>_](https://tc39.es/ecma262/#prod-UnicodeEscapeSequence)<font style="color:rgb(17, 17, 17);">.</font>

<font style="color:rgb(17, 17, 17);">In grammars whose terminal symbols are individual Unicode code points (i.e., the lexical, RegExp, and numeric string grammars), a contiguous run of multiple fixed-width code points appearing in a production is a simple shorthand for the same sequence of code points, written as standalone terminal symbols.</font>

在ECMAScript的语法中，一些终结符号以等宽字体显示。这些符号应完全按照所写的形式出现在源文本中。所有以这种方式指定的终结符号代码点都应理解为来自基本拉丁文区（Basic Latin block）的适当Unicode代码点，而不是来自其他Unicode范围内的任何外观相似的代码点。终结符号中的一个代码点不能通过\ Unicode转义序列来表示。  
在那些终结符号是个别Unicode代码点（即词法、正则表达式和数值字符串语法）的语法中，在产生式中连续出现的多个等宽代码点是一个简单的简写形式，代表同样的代码点序列，这些代码点作为独立的终结符号书写。



<font style="color:rgb(17, 17, 17);">For example, the production:</font>

[_<font style="color:rgb(51, 51, 51);">HexIntegerLiteral</font>_](https://tc39.es/ecma262/#prod-grammar-notation-HexIntegerLiteral)<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">::</font>**<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">0x</font>**<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">HexDigits</font>_](https://tc39.es/ecma262/#prod-HexDigits)

<font style="color:rgb(17, 17, 17);">is a shorthand for:</font>

[_<font style="color:rgb(51, 51, 51);">HexIntegerLiteral</font>_](https://tc39.es/ecma262/#prod-grammar-notation-HexIntegerLiteral)<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">::</font>**<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">0</font>**<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">x</font>**<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">HexDigits</font>_](https://tc39.es/ecma262/#prod-HexDigits)

<font style="color:rgb(17, 17, 17);"></font>

<font style="color:rgb(17, 17, 17);">In contrast, in the syntactic grammar, a contiguous run of fixed-width code points is a single terminal symbol.</font>

<font style="color:rgb(17, 17, 17);">Terminal symbols come in two other forms:</font>

+ <font style="color:rgb(17, 17, 17);">In the lexical and RegExp grammars, Unicode code points without a conventional printed representation are instead shown in the form "<ABBREV>" where "ABBREV" is a mnemonic for the code point or set of code points. These forms are defined in</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">Unicode Format-Control Characters</font>](https://tc39.es/ecma262/#sec-unicode-format-control-characters)<font style="color:rgb(17, 17, 17);">,</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">White Space</font>](https://tc39.es/ecma262/#sec-white-space)<font style="color:rgb(17, 17, 17);">, and</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">Line Terminators</font>](https://tc39.es/ecma262/#sec-line-terminators)<font style="color:rgb(17, 17, 17);">.</font>
+ <font style="color:rgb(17, 17, 17);">In the syntactic grammar, certain terminal symbols (e.g. </font>[_<font style="color:rgb(51, 51, 51);">IdentifierName</font>_](https://tc39.es/ecma262/#prod-IdentifierName)<font style="color:rgb(17, 17, 17);"> and </font>[_<font style="color:rgb(51, 51, 51);">RegularExpressionLiteral</font>_](https://tc39.es/ecma262/#prod-RegularExpressionLiteral)<font style="color:rgb(17, 17, 17);">) are shown in italics, as they refer to the nonterminals of the same name in the lexical grammar.</font>

相比之下，在句法语法中，连续的固定宽度代码点被视为一个单一的终结符。  
终结符还有另外两种形式：

+ 在词法和正则表达式语法中，没有传统打印表示的Unicode代码点以"<缩写>"的形式显示，其中"缩写"是该代码点或一组代码点的记忆助词。这些形式在Unicode格式控制字符、空白字符和行终止符中有定义。
+ 在句法语法中，某些终结符（例如IdentifierName和RegularExpressionLiteral）以斜体显示，因为它们指的是词法语法中同名的非终结符。



##### 5.1.5.2 <font style="color:rgb(17, 17, 17);">Nonterminal Symbols and Productions</font>
<font style="color:rgb(17, 17, 17);">Nonterminal symbols are shown in </font>_<font style="color:rgb(17, 17, 17);">italic</font>_<font style="color:rgb(17, 17, 17);"> type. The definition of a nonterminal (also called a “production”) is introduced by the name of the nonterminal being defined followed by one or more colons. (The number of colons indicates to which grammar the production belongs.) One or more alternative right-hand sides for the nonterminal then follow on succeeding lines. For example, the syntactic definition:</font>

非终结符号以斜体显示。非终结符的定义（也称为“产生式”）由被定义的非终结符名称后跟一个或多个冒号引入。（冒号的数量表示该产生式属于哪个文法。）随后，在接下来的行中给出该非终结符的一个或多个可选的右部。例如，语法定义如下： 



[_<font style="color:rgb(51, 51, 51);">WhileStatement</font>_](https://tc39.es/ecma262/#prod-grammar-notation-WhileStatement)<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">:</font>**

**<font style="color:rgb(17, 17, 17);">while</font>**<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">(</font>**<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">Expression</font>_](https://tc39.es/ecma262/#prod-Expression)<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">)</font>**<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">Statement</font>_](https://tc39.es/ecma262/#prod-Statement)



<font style="color:rgb(17, 17, 17);">states that the nonterminal </font>[_<font style="color:rgb(51, 51, 51);">WhileStatement</font>_](https://tc39.es/ecma262/#prod-grammar-notation-WhileStatement)<font style="color:rgb(17, 17, 17);"> represents the token </font>`**while**`<font style="color:rgb(17, 17, 17);">, followed by a left parenthesis token, followed by an </font>[_<font style="color:rgb(51, 51, 51);">Expression</font>_](https://tc39.es/ecma262/#prod-Expression)<font style="color:rgb(17, 17, 17);">, followed by a right parenthesis token, followed by a </font>[_<font style="color:rgb(51, 51, 51);">Statement</font>_](https://tc39.es/ecma262/#prod-Statement)<font style="color:rgb(17, 17, 17);">. The occurrences of </font>[_<font style="color:rgb(51, 51, 51);">Expression</font>_](https://tc39.es/ecma262/#prod-Expression)<font style="color:rgb(17, 17, 17);"> and </font>[_<font style="color:rgb(51, 51, 51);">Statement</font>_](https://tc39.es/ecma262/#prod-Statement)<font style="color:rgb(17, 17, 17);"> are themselves nonterminals. As another example, the syntactic definition:</font>

说明非终结符 WhileStatement 代表的是 token `while`，后面跟着一个左括号 token，接着是一个 Expression（表达式），然后是一个右括号 token，最后是一个 Statement（语句）。这里的 Expression 和 Statement 本身也是非终结符。再举一个例子，语法定义： 



[_<font style="color:rgb(51, 51, 51);">ArgumentList</font>_](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList)<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">:</font>**

_<font style="color:rgb(51, 51, 51);">       </font>_[_<font style="color:rgb(51, 51, 51);">AssignmentExpression</font>_](https://tc39.es/ecma262/#prod-AssignmentExpression)

[_<font style="color:rgb(51, 51, 51);">ArgumentList</font>_](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList)<font style="color:rgb(17, 17, 17);"> </font>**<font style="color:rgb(17, 17, 17);">,</font>**<font style="color:rgb(17, 17, 17);"> </font>[_<font style="color:rgb(51, 51, 51);">AssignmentExpression</font>_](https://tc39.es/ecma262/#prod-AssignmentExpression)



<font style="color:rgb(17, 17, 17);">states that an </font>[_<font style="color:rgb(51, 51, 51);">ArgumentList</font>_](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList)<font style="color:rgb(17, 17, 17);"> may represent either a single </font>[_<font style="color:rgb(51, 51, 51);">AssignmentExpression</font>_](https://tc39.es/ecma262/#prod-AssignmentExpression)<font style="color:rgb(17, 17, 17);"> or an </font>[_<font style="color:rgb(51, 51, 51);">ArgumentList</font>_](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList)<font style="color:rgb(17, 17, 17);">, followed by a comma, followed by an </font>[_<font style="color:rgb(51, 51, 51);">AssignmentExpression</font>_](https://tc39.es/ecma262/#prod-AssignmentExpression)<font style="color:rgb(17, 17, 17);">. This definition of </font>[_<font style="color:rgb(51, 51, 51);">ArgumentList</font>_](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList)<font style="color:rgb(17, 17, 17);"> is recursive, that is, it is defined in terms of itself. The result is that an </font>[_<font style="color:rgb(51, 51, 51);">ArgumentList</font>_](https://tc39.es/ecma262/#prod-grammar-notation-ArgumentList)<font style="color:rgb(17, 17, 17);"> may contain any positive number of arguments, separated by commas, where each argument expression is an </font>[_<font style="color:rgb(51, 51, 51);">AssignmentExpression</font>_](https://tc39.es/ecma262/#prod-AssignmentExpression)<font style="color:rgb(17, 17, 17);">. Such recursive definitions of nonterminals are common.  
</font><font style="color:rgb(17, 17, 17);">说明 ArgumentList 可以表示单个 AssignmentExpression，或者是一个 ArgumentList 后跟一个逗号再后跟一个 AssignmentExpression。这种对 ArgumentList 的定义是递归的，也就是说，它是用自身来定义的。结果就是 ArgumentList 可以包含任意正数个参数，这些参数由逗号分隔，并且每个参数表达式都是一个 AssignmentExpression。这种非终结符的递归定义是很常见的。  
</font>