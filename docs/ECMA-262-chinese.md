个人翻译，仅供参考



ECMA-262草案/2025-02-27

# ECMAScript2025语言规范
## <font style="color:rgb(17, 17, 17);">关于本规范</font>
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

## Introduction 介绍
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

数十名来自许多组织的个人为Ecma TC39中的这一版及以前版本的发展做出了非常重要的贡献。此外，一个支持TC39的ECMAScript工作的并且充满活力的社区已经形成。这个社区审查了无数草案，提交了数千份错误报告，进行了实现试验，贡献了测试套件，并向全球开发者社区普及了关于ECMAScript的知识。遗憾的是，没法在这里列出并感谢每一位为此付出努力的人和组织。  
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

## Scope 范围
<font style="color:rgb(17, 17, 17);">This Standard defines the ECMAScript 2025 general-purpose programming language.</font>

<font style="color:rgb(17, 17, 17);">本标准定义了ECMAScript 2025通用编程语言。</font>

<font style="color:rgb(17, 17, 17);"></font>

## <font style="color:rgb(17, 17, 17);">Conformance 符合性</font>
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


## 规范参考
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

## <font style="color:rgb(17, 17, 17);">Overview 概述</font>
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

### <font style="color:rgb(17, 17, 17);">Web Scripting 网页脚本</font>
<font style="color:rgb(17, 17, 17);">A web browser provides an ECMAScript </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);"> for client-side computation including, for instance, objects that represent windows, menus, pop-ups, dialog boxes, text areas, anchors, frames, history, cookies, and input/output. Further, the </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);"> provides a means to attach scripting code to events such as change of focus, page and image loading, unloading, error and abort, selection, form submission, and mouse actions. Scripting code appears within the HTML and the displayed page is a combination of user interface elements and fixed and computed text and images. The scripting code is reactive to user interaction, and there is no need for a main program.</font>

网页浏览器为客户端计算提供了一个ECMAScript宿主环境，其中包括表示窗口、菜单、弹出框、对话框、文本区域、锚点、框架、历史记录、cookie以及输入/输出的对象。此外，宿主环境还提供了一种方式，可以将脚本代码附加到诸如焦点变化、页面和图像加载、卸载、错误和中止、选择、表单提交以及鼠标动作等事件上。脚本代码会出现在HTML中，显示的页面是用户界面元素与固定和计算出的文本及图像的组合。脚本代码能够响应用户的交互，并且不需要一个主程序。



<font style="color:rgb(17, 17, 17);">A web server provides a different</font><font style="color:rgb(17, 17, 17);"> </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);"> </font><font style="color:rgb(17, 17, 17);">for server-side computation including objects representing requests, clients, and files; and mechanisms to lock and share data. By using browser-side and server-side scripting together, it is possible to distribute computation between the client and server while providing a customized user interface for a Web-based application.</font>

网页服务器为服务器端计算提供了一个不同的主机环境，其中包括代表请求、客户端和文件的对象；以及锁定和共享数据的机制。通过同时使用浏览器端和服务器端脚本，可以将计算分布在客户端和服务器之间，同时为基于Web的应用程序提供定制化的用户界面。



<font style="color:rgb(17, 17, 17);">Each Web browser and server that supports ECMAScript supplies its own </font>[<font style="color:rgb(32, 108, 167);">host environment</font>](https://tc39.es/ecma262/#host-environment)<font style="color:rgb(17, 17, 17);">, completing the ECMAScript execution environment.</font>

每个支持ECMAScript的Web浏览器和服务器都提供了自己的宿主环境，从而完成了ECMAScript的执行环境。

### <font style="color:rgb(17, 17, 17);">Hosts and Implementations </font>宿主与实现
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

### <font style="color:rgb(17, 17, 17);">ECMAScript Overview ECMAScript概述</font>
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

#### <font style="color:rgb(17, 17, 17);">Objects 对象</font>
Even though ECMAScript includes syntax for class definitions, ECMAScript objects are not fundamentally class-based such as those in C++, Smalltalk, or Java. Instead objects may be created in various ways including via a literal notation or via [constructors](https://tc39.es/ecma262/#constructor) which create objects and then execute code that initializes all or part of them by assigning initial values to their properties. Each [constructor](https://tc39.es/ecma262/#constructor) is a function that has a property named "prototype" that is used to implement prototype-based inheritance and shared properties. Objects are created by using [constructors](https://tc39.es/ecma262/#constructor) in new expressions; for example, `new Date(2009, 11)` creates a new Date object. Invoking a [constructor](https://tc39.es/ecma262/#constructor) without using new has consequences that depend on the [constructor](https://tc39.es/ecma262/#constructor). For example, `Date()` produces a string representation of the current date and time rather than an object.

尽管ECMAScript包含类定义的语法，但ECMAScript对象本质上并不是基于类的，不像C++、Smalltalk或Java中的那些对象。相反，可以通过多种方式创建对象，包括使用字面量表示法或通过构造函数来创建对象，这些构造函数创建对象后会执行代码，通过给它们的属性赋初始值来初始化全部或部分对象。每个构造函数都是一个具有名为“prototype”的属性的函数，这个属性用于实现基于原型的继承和共享属性。对象是通过在new表达式中使用构造函数创建的；例如，new Date(2009, 11) 创建一个新的Date对象。如果不使用new调用构造函数，则结果取决于具体的构造函数。例如，Date() 会产生当前日期和时间的字符串表示形式，而不是一个对象。



Every object created by a [constructor](https://tc39.es/ecma262/#constructor) has an implicit reference (called the object's prototype) to the value of its [constructor](https://tc39.es/ecma262/#constructor)'s "prototype" property. Furthermore, a prototype may have a non-null implicit reference to its prototype, and so on; this is called the prototype chain. When a reference is made to a property in an object, that reference is to the property of that name in the first object in the prototype chain that contains a property of that name. In other words, first the object mentioned directly is examined for such a property; if that object contains the named property, that is the property to which the reference refers; if that object does not contain the named property, the prototype for that object is examined next; and so on.

每个由构造函数创建的对象都有一个隐式引用（称为对象的原型）指向其构造函数的“prototype”属性的值。此外，一个原型可以有一个非空的隐式引用来指向它的原型，以此类推；这被称为原型链。当引用对象中的某个属性时，该引用实际上是指向原型链中第一个包含该名称属性的对象中的该属性。换句话说，首先检查直接提到的对象是否存在这样的属性；如果该对象包含这个命名的属性，则引用就指向这个属性；如果该对象不包含这个命名的属性，则接下来检查该对象的原型；依此类推。  

