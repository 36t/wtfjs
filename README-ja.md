# What the f\*ck JavaScript?

[![WTFPL 2.0][license-image]][license-url]
[![NPM version][npm-image]][npm-url]
[![Patreon][patreon-image]][patreon-url]
[![Buy Me A Coffee][bmc-image]][bmc-url]

<!-- > A list of funny and tricky JavaScript examples -->

> 面白くてトリッキーなJavaScriptのサンプルリスト 

<!-- JavaScript is a great language. It has a simple syntax, large ecosystem and, what is most important, a great community. -->

JavaScriptは素晴らしい言語です。シンプルな構文、大規模なエコシステム、そして何よりも重要なのは、素晴らしいコミュニティです。

<!-- At the same time, we all know that JavaScript is quite a funny language with tricky parts. Some of them can quickly turn our everyday job into hell, and some of them can make us laugh out loud. -->

同時に、JavaScriptがトリッキーな部分を持つ、非常に面白い言語であることも周知の事実です。その中には、私たちの日常の仕事をあっという間に地獄に変えてしまうものもあれば、大笑いしてしまうものもあります。

<!-- The original idea for WTFJS belongs to [Brian Leroux](https://twitter.com/brianleroux). This list is highly inspired by his talk [**“WTFJS”** at dotJS 2012](https://www.youtube.com/watch?v=et8xNAc2ic8): -->

WTFJSの原案は[Brian Leroux](https://twitter.com/brianleroux)氏によるものです。本書のリストは[dotJS 2012での彼の講演 **"WTFJS"**](https://www.youtube.com/watch?v=et8xNAc2ic8)に強く影響を受けています。


[![dotJS 2012 - Brian Leroux - WTFJS](https://img.youtube.com/vi/et8xNAc2ic8/0.jpg)](https://www.youtube.com/watch?v=et8xNAc2ic8)

# Node Packaged Manuscript

<!-- You can install this handbook using `npm`. Just run: -->

このハンドブックは`npm`を使ってインストールできます。実行するだけです。

```
$ npm install -g wtfjs
```

<!-- You should be able to run `wtfjs` at the command line now. This will open the manual in your selected `$PAGER`. Otherwise, you may continue reading on here. -->

これでコマンドラインで`wtfjs`を実行できるはずです。これで、選択した`$PAGER`でマニュアルが開かれます。それ以外の場合は、本書で読み進めることができます。

<!-- The source is available here: <https://github.com/denysdovhan/wtfjs> -->

ソースはこちらからご覧いただけます。 https://github.com/denysdovhan/wtfjs

<!-- # Translations -->

# 翻訳

<!-- Currently, there are these translations of **wtfjs**: -->

現在、**wtfjs**の翻訳は以下のとおりです。

- [中文版](./README-zh-cn.md)
- [हिंदी](./README-hi.md)
- [Français](./README-fr-fr.md)
- [Português do Brasil](./README-pt-br.md)
- [Polski](./README-pl-pl.md)
- [Italiano](./README-it-it.md)
- [Russian](https://habr.com/ru/company/mailru/blog/335292/) (on Habr.com)
- [한국어](./README-kr.md)

<!-- [**Help translating to your language**][tr-request] -->

[**翻訳を支援する**][tr-request]

[tr-request]: https://github.com/denysdovhan/wtfjs/blob/master/CONTRIBUTING.md#translations

<!-- **Note:** Translations are maintained by their translators. They may not contain every example, and existing examples may be outdated. -->

**注意：** 翻訳は翻訳者によって管理されています。すべての例が含まれているわけではありませんし、掲載例が古くなっている可能性もあります。

<!-- prettier-ignore-start -->
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
# Table of Contents

- [💪🏻 動機](#-動機)
- [✍🏻 表記について](#-表記について)
- [👀 サンプルリスト](#-サンプルリスト)
  - [`[]` is equal `![]`](#-is-equal-)
  - [`true` is not equal `![]`, but not equal `[]` too](#true-is-not-equal--but-not-equal--too)
  - [true is false](#true-is-false)
  - [baNaNa](#banana)
  - [`NaN` is not a `NaN`](#nan-is-not-a-nan)
  - [`Object.is()` and `===` weird cases](#objectis-and--weird-cases)
  - [It's a fail](#its-a-fail)
  - [`[]` is truthy, but not `true`](#-is-truthy-but-not-true)
  - [`null` is falsy, but not `false`](#null-is-falsy-but-not-false)
  - [`document.all` is an object, but it is undefined](#documentall-is-an-object-but-it-is-undefined)
  - [Minimal value is greater than zero](#minimal-value-is-greater-than-zero)
  - [function is not a function](#function-is-not-a-function)
  - [Adding arrays](#adding-arrays)
  - [Trailing commas in array](#trailing-commas-in-array)
  - [Array equality is a monster](#array-equality-is-a-monster)
  - [`undefined` and `Number`](#undefined-and-number)
  - [`parseInt` is a bad guy](#parseint-is-a-bad-guy)
  - [Math with `true` and `false`](#math-with-true-and-false)
  - [HTML comments are valid in JavaScript](#html-comments-are-valid-in-javascript)
  - [`NaN` is ~~not~~ a number](#nan-is-not-a-number)
  - [`[]` and `null` are objects](#-and-null-are-objects)
  - [Magically increasing numbers](#magically-increasing-numbers)
  - [Precision of `0.1 + 0.2`](#precision-of-01--02)
  - [Patching numbers](#patching-numbers)
  - [Comparison of three numbers](#comparison-of-three-numbers)
  - [Funny math](#funny-math)
  - [Addition of RegExps](#addition-of-regexps)
  - [Strings aren't instances of `String`](#strings-arent-instances-of-string)
  - [Calling functions with backticks](#calling-functions-with-backticks)
  - [Call call call](#call-call-call)
  - [A `constructor` property](#a-constructor-property)
  - [Object as a key of object's property](#object-as-a-key-of-objects-property)
  - [Accessing prototypes with `__proto__`](#accessing-prototypes-with-__proto__)
  - [`` `${{Object}}` ``](#-object-)
  - [Destructuring with default values](#destructuring-with-default-values)
  - [Dots and spreading](#dots-and-spreading)
  - [Labels](#labels)
  - [Nested labels](#nested-labels)
  - [Insidious `try..catch`](#insidious-trycatch)
  - [Is this multiple inheritance?](#is-this-multiple-inheritance)
  - [A generator which yields itself](#a-generator-which-yields-itself)
  - [A class of class](#a-class-of-class)
  - [Non-coercible objects](#non-coercible-objects)
  - [Tricky arrow functions](#tricky-arrow-functions)
  - [Arrow functions can not be a constructor](#arrow-functions-can-not-be-a-constructor)
  - [`arguments` and arrow functions](#arguments-and-arrow-functions)
  - [Tricky return](#tricky-return)
  - [Chaining assignments on object](#chaining-assignments-on-object)
  - [Accessing object properties with arrays](#accessing-object-properties-with-arrays)
  - [Null and Relational Operators](#null-and-relational-operators)
  - [`Number.toFixed()` display different numbers](#numbertofixed-display-different-numbers)
  - [`Math.max()` less than `Math.min()`](#mathmax-less-than-mathmin)
  - [Comparing `null` to `0`](#comparing-null-to-0)
  - [Same variable redeclaration](#same-variable-redeclaration)
  - [Default behavior Array.prototype.sort()](#default-behavior-arrayprototypesort)
  - [resolve() won't return Promise instance](#resolve-wont-return-promise-instance)
  - [`{}{}` is undefined](#-is-undefined)
  - [`min` is greater than `max`](#min-is-greater-than-max)
  - [`arguments` binding](#arguments-binding)
  - [An `alert` from hell](#an-alert-from-hell)
  - [An infinite timeout](#an-infinite-timeout)
  - [A `setTimeout` object](#a-settimeout-object)
  - [Double dot](#double-dot)
  - [Extra Newness](#extra-newness)
  - [Why you should use semicolons](#why-you-should-use-semicolons)
  - [Split a string by a space](#split-a-string-by-a-space)
  - [A stringified string](#a-stringified-string)
  - [Non-strict comparison of a number to `true`](#non-strict-comparison-of-a-number-to-true)
- [📚 Other resources](#-other-resources)
- [🤝 支援](#-支援)
- [🎓 License](#-license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->
<!-- prettier-ignore-end -->

<!-- # 💪🏻 Motivation -->

# 💪🏻 動機

<!-- > Just for fun
>
> &mdash; _[**“Just for Fun: The Story of an Accidental Revolutionary”**](https://en.wikipedia.org/wiki/Just_for_Fun), Linus Torvalds_ -->

> ただ楽しんでください。
>
> &mdash; _[**“Just for Fun: The Story of an Accidental Revolutionary”**](https://en.wikipedia.org/wiki/Just_for_Fun), Linus Torvalds_

<!-- The primary goal of this list is to collect some crazy examples and explain how they work, if possible. Just because it's fun to learn something that we didn't know before. -->

このリストの主な目的は、いくつかのクレイジーな例を集めて、可能であればそれらがどのように機能するか説明することです。 今まで知らなかったことを学ぶのは楽しいものです。

<!-- If you are a beginner, you can use these notes to get a deeper dive into JavaScript. I hope these notes will motivate you to spend more time reading the specification. -->

あなたがJavaScriptの初心者であれば、本書を使用してJavaScriptをより深く理解できます。本書が、JavaScriptの仕様書を読む際、もっと時間をかけようという動機になれば幸いです。

<!-- If you are a professional developer, you can consider these examples as a great reference for all of the quirks and unexpected edges of our beloved JavaScript. -->

あなたがJavaScriptのプロの開発者であれば、本書の例は、私たちの愛するJavaScriptのすべての癖や予期しない挙動の優れたリファレンスと考えることができます。

<!-- In any case, just read this. You're probably going to find something new. -->

とにかく本書を読んでみてください。きっと何か新しい発見があるはずです。

<!-- > **⚠️ Note:** If you enjoy reading this document, please, [consider supporting the author of this collection](#-supporting). -->

> **⚠️注意：** このドキュメントを読んで楽しむことができたら、[このコレクションの作者を支援を検討してください。](#-支援)


# ✍🏻 表記について

<!-- **`// ->`** is used to show the result of an expression. For example: -->

**`// ->`** は、式の結果を表す場合に使用します。例えば、次のようになります。

```js
1 + 1; // -> 2
```

<!-- **`// >`** means the result of `console.log` or another output. For example: -->

**`// >`** は、`console.log`の結果やその他の出力の意味で使用します。例えば、次のようになります。

```js
console.log("hello, world!"); // > hello, world!
```

<!-- **`//`** is just a comment used for explanations. Example: -->

**`//`** は式を説明するコメントに使用します。例えば、次のようになります。

<!-- ```js
// Assigning a function to foo constant
const foo = function() {};
``` -->

```js
// 定数fooに関数を代入
const foo = function() {};
```

# 👀 サンプルリスト

## `[]`と`![]`は等しい

<!-- Array is equal not array: -->

配列`[]`は配列ではない`![]`に等しいです。

```js
[] == ![]; // -> true
```

### 💡 解説

<!-- The abstract equality operator converts both sides to numbers to compare them, and both sides become the number `0` for different reasons. Arrays are truthy, so on the right, the opposite of a truthy value is `false`, which is then coerced to `0`. On the left, however, an empty array is coerced to a number without becoming a boolean first, and empty arrays are coerced to `0`, despite being truthy. -->

等価演算子`==`は、両辺を数値に暗黙的に型変換して比較します。上記の場合、両辺はそれぞれ違う理由で数値の`0`になります。配列は真偽値なので、右辺では真偽値の反対は`false`であり、これは`0`に暗黙的に型変換されます。しかし左辺では、空の配列は最初に真偽値にならずに数値に暗黙的に型変換されます。空の配列は真偽値であるにもかかわらず`0`になります。

<!-- Here is how this expression simplifies: -->

上記を簡略化すると、次のようになります。

```js
+[] == +![];
0 == +false;
0 == 0;
true;
```

<!-- See also [`[]` is truthy, but not `true`](#-is-truthy-but-not-true). -->

関連：[`[]`は真だが`true`ではない](#-`[]`は真だが`true`ではない)

- [**12.5.9** Logical NOT Operator (`!`)](https://www.ecma-international.org/ecma-262/#sec-logical-not-operator)
- [**7.2.15** Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison)

<!-- ## `true` is not equal `![]`, but not equal `[]` too -->

## `true`は`![]`と等しくないが、`[]`とも等しくない

<!-- Array is not equal `true`, but not Array is not equal `true` too;
Array is equal `false`, not Array is equal `false` too: -->

配列`[]`は`true`と等しくありませんが、配列の論理否定`![]`も`true`と等しくありません。配列`[]`は`false`と等しいですが、配列の論理否定`![]`も`false`と等しいです。

```js
true == []; // -> false
true == ![]; // -> false

false == []; // -> true
false == ![]; // -> true
```

### 💡 解説

```js
true == []; // -> false
true == ![]; // -> false

// JavaScriptの仕様によると

true == []; // -> false

toNumber(true); // -> 1
toNumber([]); // -> 0

1 == 0; // -> false

true == ![]; // -> false

![]; // -> false

true == false; // -> false
```

```js
false == []; // -> true
false == ![]; // -> true

// JavaScriptの仕様によると

false == []; // -> true

toNumber(false); // -> 0
toNumber([]); // -> 0

0 == 0; // -> true

false == ![]; // -> true

![]; // -> false

false == false; // -> true
```

- [**7.2.15** Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison)

<!-- ## true is false -->

## 真は偽です

```js
!!"false" == !!"true"; // -> true
!!"false" === !!"true"; // -> true
```

### 💡 解説

<!-- Consider this step-by-step: -->

順を追って考えてみましょう。

```js
// trueは'真'であり、1の値（数字）で表され、文字列の'true'はNaNです
true == "true"; // -> false
false == "false"; // -> false

// 文字列の'false'は空の文字列ではないので、'真'になります
!!"false"; // -> true
!!"true"; // -> true
```

- [**7.2.15** Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison)

## baNaNa（バナナ）

```js
"b" + "a" + +"a" + "a"; // -> 'baNaNa'
```

<!-- This is an old-school joke in JavaScript, but remastered. Here's the original one: -->

こののコードはJavaScriptの古いジョークですが、リマスターされています。オリジナルは下記のコードです。

```js
"foo" + +"bar"; // -> 'fooNaN'
```

### 💡 解説

<!-- The expression is evaluated as `'foo' + (+'bar')`, which converts `'bar'` to not a number. -->

式は`'foo' + (+'bar')`として評価し、`'bar'`を数字でないものに変換します。

- [**12.8.3** The Addition Operator (`+`)](https://www.ecma-international.org/ecma-262/#sec-addition-operator-plus)
- [12.5.6 Unary + Operator](https://www.ecma-international.org/ecma-262/#sec-unary-plus-operator)

<!-- ## `NaN` is not a `NaN` -->

## `NaN`は`NaN`ではありません

```js
NaN === NaN; // -> false
```

### 💡 解説

<!-- The specification strictly defines the logic behind this behavior: -->

仕様では、この動作のロジックを厳密に定義しています。

<!-- > 1. If `Type(x)` is different from `Type(y)`, return **false**.
> 2. If `Type(x)` is Number, then
>    1. If `x` is **NaN**, return **false**.
>    2. If `y` is **NaN**, return **false**.
>    3. … … …
>
> &mdash; [**7.2.14** Strict Equality Comparison](https://www.ecma-international.org/ecma-262/#sec-strict-equality-comparison) -->

> 1. `Type(x)`が`Type(y)`と異なる場合、**false**を返す
> 2. `Type(x)`が数字で
>    1. `x`が**NaN**の場合、**false**を返す
>    2. `y`が**NaN**の場合、**false**を返す
>    3. … … …
>
> &mdash; [**7.2.14** Strict Equality Comparison](https://www.ecma-international.org/ecma-262/#sec-strict-equality-comparison)


<!-- Following the definition of `NaN` from the IEEE: -->

IEEEの`NaN`の定義に従っています。

> Four mutually exclusive relations are possible: less than, equal, greater than, and unordered. The last case arises when at least one operand is NaN. Every NaN shall compare unordered with everything, including itself.
>
> &mdash; [“What is the rationale for all comparisons returning false for IEEE754 NaN values?”](https://stackoverflow.com/questions/1565164/1573715#1573715) at StackOverflow

<!-->
TODO: 翻訳
4つの相互に排他的な関係が可能です：より小さい、等しい、より大きい、および順序付けされていません。 最後のケースは、少なくとも1つのオペランドがNaNの場合に発生します。 すべてのNaNは、それ自体を含むすべてのものと順序付けられていないものを比較するものとします。

less than、equal、greater than、unorderedの4つの相互に排他的な関係が可能です。最後のケースは、少なくとも1つのオペランドがNaNの場合に発生します。 すべてのNaNは、それ自体を含むすべてのものと`順序付けられていないもの(unordered)`を比較するものとします。
-->

<!-- ## `Object.is()` and `===` weird cases -->

## `Object.is()`と`===`の奇妙な事例

<!-- `Object.is()` determines if two values have the same value or not. It works similar to the `===` operator but there are a few weird cases: -->

`Object.is()`は、 2つの値が[同一値](https://developer.mozilla.org/ja/docs/Web/JavaScript/Equality_comparisons_and_sameness)であるかどうかを判定します．これは厳密等価演算子`===`と似たような働きをしますが，いくつかの奇妙な事例があります．

```javascript
Object.is(NaN, NaN); // -> true
NaN === NaN; // -> false

Object.is(-0, 0); // -> false
-0 === 0; // -> true

Object.is(NaN, 0 / 0); // -> true
NaN === 0 / 0; // -> false
```

### 💡 解説

<!-- In JavaScript lingo, `NaN` and `NaN` are the same value but they're not strictly equal. `NaN === NaN` being false is apparently due to historical reasons so it would probably be better to accept it as it is. -->

JavaScriptの用語で`NaN`と`NaN`は同一値ですが、厳密には同じではありません。`NaN === NaN` が`false`なのは歴史的な理由によるものらしいので、そのまま受け入れたほうがいいかもしれません。

<!-- Similarly, `-0` and `0` are strictly equal, but they're not the same value. -->

同様に、`-0`と`0`は厳密には等しいのですが、同一値ではありません。

<!-- For more details about `NaN === NaN`, see the above case. -->

`NaN === NaN`については、前の章を参照してください。

- [Here are the TC39 specs about Object.is](https://tc39.es/ecma262/#sec-object.is)
- [Equality comparisons and sameness](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness) on MDN

<!-- ## It's a fail -->

## 失敗です

<!-- You would not believe, but … -->

結果が信じられないかもしれませんが。。。

```js
(![] + [])[+[]] +
  (![] + [])[+!+[]] +
  ([![]] + [][[]])[+!+[] + [+[]]] +
  (![] + [])[!+[] + !+[]];
// -> 'fail'（失敗）
```

### 💡 解説

<!-- By breaking that mass of symbols into pieces, we notice that the following pattern occurs often: -->

サンプルコードで多用している記号の塊をバラバラにしてみると、次のパターンが多いことに気がつきます。

```js
![] + []; // -> 'false'
![]; // -> false
```

<!-- So we try adding `[]` to `false`. But due to a number of internal function calls (`binary + Operator` -> `ToPrimitive` -> `[[DefaultValue]]`) we end up converting the right operand to a string: -->

そこで、 `[]`を `false`に追加してみます。 しかし、いくつかの内部関数の呼びだし（`binary + Operator`->` ToPrimitive`-> `[[DefaultValue]]`）により、結局、右のオペランドを文字列に変換してしまいます。

```js
![] + [].toString(); // 'false'
```

<!-- Thinking of a string as an array we can access its first character via `[0]`: -->

文字列を配列と考えると、`[0]` で一文字目の文字`f`にアクセスできます。

```js
"false"[0]; // -> 'f'
```

<!-- The rest is obvious, but the `i` is tricky. The `i` in `fail` is grabbed by generating the string `'falseundefined'` and grabbing the element on index `['10']`. -->

ここまでの解説が分かれば、残りの文字（`a`、`l`）は明白です。ただし`i`の文字は厄介です。 `fail`の`i`は、最初に文字列 `'falseundefined'`を生成し、`['10']`で文字`a`にアクセスしています。

<!-- More examples: -->

その他の例。

```js
+![]          // -> 0
+!![]         // -> 1
!![]          // -> true
![]           // -> false
[][[]]        // -> undefined
+!![] / +![]  // -> Infinity
[] + {}       // -> "[object Object]"
+{}           // -> NaN
```

- [Brainfuck beware: JavaScript is after you!](http://patriciopalladino.com/blog/2012/08/09/non-alphanumeric-javascript.html)
- [Writing a sentence without using the Alphabet](https://bluewings.github.io/en/writing-a-sentence-without-using-the-alphabet/#weird-javascript-generator) — generate any phrase using JavaScript

<!-- ## `[]` is truthy, but not `true` -->

## `[]`は真だが`true`ではない

<!-- An array is a truthy value, however, it's not equal to `true`. -->

配列`[]`は真ですが、`true`とは等しくありません。

```js
!![]       // -> true
[] == true // -> false
```

### 💡 解説

<!-- Here are links to the corresponding sections in the ECMA-262 specification: -->

ECMA-262の仕様をご覧ください。

- [**12.5.9** Logical NOT Operator (`!`)](https://www.ecma-international.org/ecma-262/#sec-logical-not-operator)
- [**7.2.15** Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison)

<!-- ## `null` is falsy, but not `false` -->

## `null`は偽だが`false`ではない

<!-- Despite the fact that `null` is a falsy value, it's not equal to `false`. -->

`null`は偽の値であるにもかかわらず、`false`とは等しくありません。

```js
!!null; // -> false
null == false; // -> false
```

<!-- At the same time, other falsy values, like `0` or `''` are equal to `false`. -->

同時に、`0`や`''`のような他の偽の値は、`false`と等しいです。

```js
0 == false; // -> true
"" == false; // -> true
```

### 💡 解説

<!-- The explanation is the same as for previous example. Here's the corresponding link: -->

[先程の例](#`[]`は真だが`true`ではない)と同じ解説になります。

- [**7.2.15** Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison)

<!-- ## `document.all` is an object, but it is undefined -->

## `document.all` はオブジェクトだが未定義

<!-- > ⚠️ This is part of the Browser API and won't work in a Node.js environment ⚠️ -->

> ⚠️ これはBrowser APIの一部で、Node.js環境では動作しません ⚠️

<!-- Despite the fact that `document.all` is an array-like object and it gives access to the DOM nodes in the page, it responds to the `typeof` function as `undefined`. -->

`document.all`は配列のようなオブジェクトで、ページ内のDOMノードにアクセスできるにもかかわらず、`typeof`演算子を使用すると`undefined`を返します。

```js
document.all instanceof Object; // -> true
typeof document.all; // -> 'undefined'
```

<!-- At the same time, `document.all` is not equal to `undefined`. -->

同時に、`document.all`は`undefined`と等しくありません。

```js
document.all === undefined; // -> false
document.all === null; // -> false
```

<!-- But at the same time: -->

しかし、同時に`document.all`は`null`と等しいです。

```js
document.all == null; // -> true
```

### 💡 解説

<!-- > `document.all` used to be a way to access DOM elements, in particular with old versions of IE. While it has never been a standard it was broadly used in the old age JS code. When the standard progressed with new APIs (such as `document.getElementById`) this API call became obsolete and the standard committee had to decide what to do with it. Because of its broad use they decided to keep the API but introduce a willful violation of the JavaScript specification.
> The reason why it responds to `false` when using the [Strict Equality Comparison](https://www.ecma-international.org/ecma-262/#sec-strict-equality-comparison) with `undefined` while `true` when using the [Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison) is due to the willful violation of the specification that explicitly allows that.
>
> &mdash; [“Obsolete features - document.all”](https://html.spec.whatwg.org/multipage/obsolete.html#dom-document-all) at WhatWG - HTML spec
> &mdash; [“Chapter 4 - ToBoolean - Falsy values”](https://github.com/getify/You-Dont-Know-JS/blob/0d79079b61dad953bbfde817a5893a49f7e889fb/types%20%26%20grammar/ch4.md#falsy-objects) at YDKJS - Types & Grammar -->

> `document.all` は、特に古いバージョンのInternet Explorerで、DOM要素にアクセスするための方法でした。これはInternet Explorerの独自実装で、古い時代のJSコードで広く使われていました。規格が新しいAPI（`document.getElementById`など）の登場で、このAPIは時代遅れになり、規格委員会はこれをどうするか決めなければなりませんでした。広く使われていたため、APIを残すことにしましたが、JavaScriptの仕様に対する故意の違反を導入することになりました。
>  [厳密等価演算子（`===`）](https://www.ecma-international.org/ecma-262/#sec-strict-equality-comparison)を用いた`undefined`との比較で`false`を返し、[等価演算子 (`==`) ](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison)を用いた`undefined`との比較で`true`を返す理由は、それを明示的に許可する仕様に故意に違反しているためです。
>
> &mdash; [“Obsolete features - document.all”](https://html.spec.whatwg.org/multipage/obsolete.html#dom-document-all) at WhatWG - HTML spec<br>
> &mdash; [“Chapter 4 - ToBoolean - Falsy values”](https://github.com/getify/You-Dont-Know-JS/blob/0d79079b61dad953bbfde817a5893a49f7e889fb/types%20%26%20grammar/ch4.md#falsy-objects) at YDKJS - Types & Grammar

<!-- ## Minimal value is greater than zero -->

## 最小値は0より大きい

<!-- `Number.MIN_VALUE` is the smallest number, which is greater than zero: -->

`Number.MIN_VALUE`は、0より大きい最小の数値である。

```js
Number.MIN_VALUE > 0; // -> true
```

### 💡 解説

<!-- > `Number.MIN_VALUE` is `5e-324`, i.e. the smallest positive number that can be represented within float precision, i.e. that's as close as you can get to zero. It defines the best resolution that floats can give you.
>
> Now the overall smallest value is `Number.NEGATIVE_INFINITY` although it's not really numeric in a strict sense.
>
> &mdash; [“Why is `0` less than `Number.MIN_VALUE` in JavaScript?”](https://stackoverflow.com/questions/26614728/why-is-0-less-than-number-min-value-in-javascript) at StackOverflow -->


> `Number.MIN_VALUE`は`5e-324`、すなわち浮動小数点の精度で表すことができる最も小さな正の数値です。つまり、0に限りなく近い値です。これは浮動小数点が提供できる最高の解像度を定義します。
>
> 厳密な意味では数値ではありませんが、全体としての最も小さい数値は`Number.NEGATIVE_INFINITY`になります。
>
> &mdash; [“Why is `0` less than `Number.MIN_VALUE` in JavaScript?”](https://stackoverflow.com/questions/26614728/why-is-0-less-than-number-min-value-in-javascript) at StackOve

- [**20.1.2.9** Number.MIN_VALUE](https://www.ecma-international.org/ecma-262/#sec-number.min_value)

<!-- ## function is not a function -->

## 関数は関数ではない

<!-- > ⚠️ A bug present in V8 v5.5 or lower (Node.js <=7) ⚠️ -->

> ⚠️ V8 v5.5以下に存在するバグになります（Node.js <= 7）⚠️

<!-- All of you know about the annoying _undefined is not a function_, but what about this? -->

_未定義は関数ではない_ という厄介なものをご存知だと思いますが、これはどうでしょうか？

```js
// nullを継承するクラスの宣言
class Foo extends null {}
// -> [Function: Foo]

new Foo() instanceof null;
// > TypeError: function is not a function
// >     at … … …
```

### 💡 解説

<!-- This is not a part of the specification. It's just a bug that has now been fixed, so there shouldn't be a problem with it in the future. -->

これは仕様の一部ではなく、単なるバグで現在は修正されているので、今後は問題がないはずです。

<!-- ### Super constructor null of Foo is not a constructor -->

### Fooのスーパーコンストラクタnullはコンストラクタではない

<!-- It's continuation of story with previous bug in modern environment (tested with Chrome 71 and Node.js v11.8.0). -->

このバグを、最新の環境（Chrome 71およびNode.js v11.8.0でテスト）で確認しました。

```js
class Foo extends null {}
new Foo() instanceof null;
// > TypeError: Super constructor null of Foo is not a constructor
```

### 💡 解説

<!-- This is not a bug because: -->

これはバグではありません。

```js
Object.getPrototypeOf(Foo.prototype); // -> null
```

<!-- If the class has no constructor the call from prototype chain. But in the parent has no constructor. Just in case, I’ll clarify that `null` is an object: -->

クラスにコンストラクタがない場合、プロトタイプチェーンから呼び出します。しかし、親クラスにはコンストラクタがありません。念のため、`null`はオブジェクトであることを明記しておきます。

```js
typeof null === "object";
```

<!-- Therefore, you can inherit from it (although in the world of the OOP for such terms would have beaten me). So you can't call the null constructor. If you change this code: -->

<!-- TODO: -->
そのため、継承が可能です（このような用語のOOPの世界では、私は負けてしまいますが）。なので、nullのコンストラクタを呼び出すことはできません。このコードを変更してみます。

```js
class Foo extends null {
  constructor() {
    console.log("something");
  }
}
```

<!-- You see the error: -->

エラーが表示されます。

```
ReferenceError: Must call super constructor in derived class before accessing 'this' or returning from derived constructor
```

<!-- And if you add `super`: -->

そして、`super`を使用すると、

```js
class Foo extends null {
  constructor() {
    console.log(111);
    super();
  }
}
```

<!-- JS throws an error: -->

JavaScriptがエラーを起こします。

```
TypeError: Super constructor null of Foo is not a constructor
```

- [An explanation of this issue](https://github.com/denysdovhan/wtfjs/pull/102#discussion_r259143582) by [@geekjob](https://github.com/geekjob)

<!-- ## Adding arrays -->

## 配列の追加

<!-- What if you try to add two arrays? -->

2つの配列を足すとどうなるでしょうか？

```js
[1, 2, 3] + [4, 5, 6]; // -> '1,2,34,5,6'
```

### 💡 解説

<!-- The concatenation happens. Step-by-step, it looks like this: -->

連結が起こります。順を追って説明すると、次のようになります。

```js
[1, 2, 3] +
  [4, 5, 6][
    // toString()メソッドが呼び出される
    (1, 2, 3)
  ].toString() +
  [4, 5, 6].toString();
// 連結
"1,2,3" + "4,5,6";
// ->
("1,2,34,5,6");
```

<!-- ## Trailing commas in array -->

## 末尾のカンマ

<!-- You've created an array with 4 empty elements. Despite all, you'll get an array with three elements, because of trailing commas: -->

次のコードは4つの空の要素を持つ配列を作成しました。しかし末尾にカンマが存在するため、3つの要素を持つ配列になってしまいます。

```js
let a = [, , ,];
a.length; // -> 3
a.toString(); // -> ',,'
```

### 💡 解説

<!-- > **Trailing commas** (sometimes called "final commas") can be useful when adding new elements, parameters, or properties to JavaScript code. If you want to add a new property, you can simply add a new line without modifying the previously last line if that line already uses a trailing comma. This makes version-control diffs cleaner and editing code might be less troublesome.
>
> &mdash; [Trailing commas](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Trailing_commas) at MDN -->

> **末尾のカンマ**（「最後のカンマ」と呼ばれることもあります）は、JavaScriptのコードに新しい要素、パラメータ、プロパティを追加する際に役立ちます。 新しいプロパティを追加する場合、その行ですでに末尾のカンマが使用されていれば、単に新しい行を追加するだけで済みます。これにより、バージョン管理の差分がきれいになり、コードの編集の手間が減るかもしれません。
>
> &mdash; [末尾のカンマ](https://developer.mozilla.org/ja/docs/Web/JavaScript/Reference/Trailing_commas) at MDN

<!-- ## Array equality is a monster -->

## 配列の比較は化け物

<!-- Array equality is a monster in JS, as you can see below: -->

次のように、JavaScriptの配列の比較は化け物のようです。

```js
[] == ''   // -> true
[] == 0    // -> true
[''] == '' // -> true
[0] == 0   // -> true
[0] == ''  // -> false
[''] == 0  // -> true

[null] == ''      // true
[null] == 0       // true
[undefined] == '' // true
[undefined] == 0  // true

[[]] == 0  // true
[[]] == '' // true

[[[[[[]]]]]] == '' // true
[[[[[[]]]]]] == 0  // true

[[[[[[ null ]]]]]] == 0  // true
[[[[[[ null ]]]]]] == '' // true

[[[[[[ undefined ]]]]]] == 0  // true
[[[[[[ undefined ]]]]]] == '' // true
```

### 💡 解説

<!-- You should watch very carefully for the above examples! The behaviour is described in section [**7.2.15** Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison) of the specification. -->

上記の例は非常に注意して見る必要があります！この動作は、仕様の[**7.2.15** Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison)に記載されています。

<!-- ## `undefined` and `Number` -->

## `undefined`と`Number`

<!-- If we don't pass any arguments into the `Number` constructor, we'll get `0`. The value `undefined` is assigned to formal arguments when there are no actual arguments, so you might expect that `Number` without arguments takes `undefined` as a value of its parameter. However, when we pass `undefined`, we will get `NaN`. -->


`Number`のコンストラクタに何も引数を渡さなければ`0`を返します。
`undefined`は実際の引数がないときに形式的な引数に割り当てられるので、引数のない`Number`は引数の値として`undefined`を取ると思うかもしれません。
しかし、引数に`undefined`を渡すと`NaN`が返ってきます。

```js
Number(); // -> 0
Number(undefined); // -> NaN
```

### 💡 解説

<!-- According to the specification: -->

仕様によると、

<!-- 1. If no arguments were passed to this function's invocation, let `n` be `+0`.
2. Else, let `n` be ? `ToNumber(value)`.
3. In case of `undefined`, `ToNumber(undefined)` should return `NaN`. -->

1. `Number`の呼び出し時、引数が渡されなかった場合、引数`n`は`+0`とします。
2. そうでなければ`n`は`ToNumber(value)` となります。
3. 引数が`undefined`の場合、`ToNumber(undefined)` は`NaN` を返さなくてはなりません。

<!-- Here's the corresponding section: -->

仕様の該当箇所はこちらです。

- [**20.1.1** The Number Constructor](https://www.ecma-international.org/ecma-262/#sec-number-constructor)
- [**7.1.3** ToNumber(`argument`)](https://www.ecma-international.org/ecma-262/#sec-tonumber)

<!-- ## `parseInt` is a bad guy -->

## `parseInt`は悪いヤツ

<!-- `parseInt` is famous by its quirks: -->

`parseInt`は奇妙な癖で有名です。

```js
parseInt("f*ck"); // -> NaN
parseInt("f*ck", 16); // -> 15
```

<!-- **💡 Explanation:** This happens because `parseInt` will continue parsing character-by-character until it hits a character it doesn't know. The `f` in `'f*ck'` is the hexadecimal digit `15`. -->

**💡 解説** これは、`parseInt`が知らない文字にヒットするまで1文字ずつ解析を続けるために発生します。`'f*ck'`の`f`は16進数の`15`です。

<!-- Parsing `Infinity` to integer is something… -->

`Infinity`を整数に解析するのは、どうなんだろう。。。

```js
//
parseInt("Infinity", 10); // -> NaN
// ...
parseInt("Infinity", 18); // -> NaN...
parseInt("Infinity", 19); // -> 18
// ...
parseInt("Infinity", 23); // -> 18...
parseInt("Infinity", 24); // -> 151176378
// ...
parseInt("Infinity", 29); // -> 385849803
parseInt("Infinity", 30); // -> 13693557269
// ...
parseInt("Infinity", 34); // -> 28872273981
parseInt("Infinity", 35); // -> 1201203301724
parseInt("Infinity", 36); // -> 1461559270678...
parseInt("Infinity", 37); // -> NaN
```

<!-- Be careful with parsing `null` too: -->

`null`の解析にも注意が必要です。

```js
parseInt(null, 24); // -> 23
```

<!-- **💡 Explanation:** -->

**💡 解説**

<!-- > It's converting `null` to the string `"null"` and trying to convert it. For radixes 0 through 23, there are no numerals it can convert, so it returns NaN. At 24, `"n"`, the 14th letter, is added to the numeral system. At 31, `"u"`, the 21st letter, is added and the entire string can be decoded. At 37 on there is no longer any valid numeral set that can be generated and `NaN` is returned.
>
> &mdash; [“parseInt(null, 24) === 23… wait, what?”](https://stackoverflow.com/questions/6459758/parseintnull-24-23-wait-what) at StackOverflow -->

> `null`をまずは文字列`"null"`に変換して、基数に変換しようとしています。0から23までの基数では、変換できる数字がないので、NaNを返します。24では、14番目の文字である`"n"`が数学的記数法に追加されます。31では、21番目の文字である`"u"`が追加され、文字列全体をデコードできます。37以降では、生成できる有効な数字がなくなり`NaN`が返されます。
>
> &mdash; [“parseInt(null, 24) === 23… wait, what?”](https://stackoverflow.com/questions/6459758/parseintnull-24-23-wait-what) at StackOverflow

<!-- Don't forget about octals: -->

忘れてはいけないのが8進法です。

```js
parseInt("06"); // 6
parseInt("08"); // 8 ECMAScript 5をサポートしている場合
parseInt("08"); // 0 ECMAScript 5をサポートしていない場合
```

<!-- **💡 Explanation:** If the input string begins with "0", radix is eight (octal) or 10 (decimal). Exactly which radix is chosen is implementation-dependent. ECMAScript 5 specifies that 10 (decimal) is used, but not all browsers support this yet. For this reason always specify a radix when using `parseInt`. -->

**💡 解説** 入力文字列が"0"で始まる場合、基数は8（8進法）または10（10進法）となります。どの基数を選択するかは、正確にはブラウザの実装に依存します。ECMAScript 5では10（10進法）を採用していますが、すべてのブラウザがまだECMAScript 5をサポートしているわけではありません。このため、`parseInt`を使用するときは、必ず基数を指定してください。

<!-- `parseInt` always convert input to string: -->

`parseInt` は、常に入力を文字列に変換します。

```js
parseInt({ toString: () => 2, valueOf: () => 1 }); // -> 2
Number({ toString: () => 2, valueOf: () => 1 }); // -> 1
```

<!-- Be careful while parsing floating point values -->

浮動小数点値の解析時の注意点

```js
parseInt(0.000001); // -> 0
parseInt(0.0000001); // -> 1
parseInt(1 / 1999999); // -> 5
```

<!-- **💡 Explanation:** `ParseInt` takes a string argument and returns an integer of the specified radix. `ParseInt` also strips anything after and including the first non-digit in the string parameter. `0.000001` is converted to a string `"0.000001"` and the `parseInt` returns `0`. When `0.0000001` is converted to a string it is treated as `"1e-7"` and hence `parseInt` returns `1`. `1/1999999` is interpreted as `5.00000250000125e-7` and `parseInt` returns `5`. -->

**💡 解説** `ParseInt`は文字列の引数を取り、指定された基数の整数を返します。また、`ParseInt`は文字列の引数に含まれる最初の非数字以降をすべて除外します。`0.000001`は文字列`"0.000001"`に変換され、`parseInt`は`0`を返します。`0.0000001`が文字列に変換されると`"1e-7"`として扱われるので，`parseInt`は`1`を返します。`1/1999999`は `5.00000250000125e-7`として解析され，`parseInt` は`5`を返します。

<!-- ## Math with `true` and `false` -->

## `true`と`false`を使用した数学

<!-- Let's do some math: -->

ちょっと計算してみましょう。

```js
true + true; // -> 2
(true + true) * (true + true) - true; // -> 3
```

<!-- Hmmm… 🤔 -->

うーん 🤔

### 💡 解説

<!-- We can coerce values to numbers with the `Number` constructor. It's quite obvious that `true` will be coerced to `1`: -->

数値を数字に変換するには、`Number`コンストラクタを使用します。`Number`を使用して`true`を変換した場合、`1`に変換されることは明らかです。

```js
Number(true); // -> 1
```

<!-- The unary plus operator attempts to convert its value into a number. It can convert string representations of integers and floats, as well as the non-string values `true`, `false`, and `null`. If it cannot parse a particular value, it will evaluate to `NaN`. That means we can coerce `true` to `1` easier: -->

単項プラス演算子`+`は、対象の値を数値に変換しようとします。整数や浮動小数点の文字列表現や、文字列以外の値である`true`、`false`、`null`を変換できます。特定の値を解析できない場合は、`NaN`と評価されます。つまり、`true`を`1`に変換するのは簡単です。

```js
+true; // -> 1
```

<!-- When you're performing addition or multiplication, the `ToNumber` method is invoked. According to the specification, this method returns: -->

加算や乗算を行う際には、`ToNumber`メソッドが呼び出されます。仕様によると、このメソッドは以下を返します。

<!-- > If `argument` is **true**, return **1**. If `argument` is **false**, return **+0**. -->

> `引数`が**true**の場合、**1**を返す。`引数`が**false**の場合、**+0**を返す。

<!-- That's why we can add boolean values as regular numbers and get correct results. -->

そのため、ブーリアンの値を通常の数値として追加しても、正しい結果が得られるのです。

<!-- Corresponding sections: -->

<!-- TODO: -->
対応するセクション：

- [**12.5.6** Unary `+` Operator](https://www.ecma-international.org/ecma-262/#sec-unary-plus-operator)
- [**12.8.3** The Addition Operator (`+`)](https://www.ecma-international.org/ecma-262/#sec-addition-operator-plus)
- [**7.1.3** ToNumber(`argument`)](https://www.ecma-international.org/ecma-262/#sec-tonumber)

<!-- ## HTML comments are valid in JavaScript -->

## HTMLのコメントはJavaScriptで有効

<!-- You will be impressed, but `<!--` (which is known as HTML comment) is a valid comment in JavaScript. -->

感動すると思いますが、`<!--`（HTMLのコメントとして知られています）は、JavaScriptでは有効なコメントです。

```js
// 有効なコメント
<!-- valid comment too
```

### 💡 解説

<!-- Impressed? HTML-like comments were intended to allow browsers that didn't understand the `<script>` tag to degrade gracefully. These browsers, e.g. Netscape 1.x are no longer popular. So there is really no point in putting HTML comments in your script tags anymore. -->

感動しましたか？HTMlのコメントは、`<script>`タグを理解できないブラウザが支障をきたさないよう、HTMLのコメントを囲んだ部分を機能させないことを目的としています。対象のブラウザ、例えばNetscape1.xなどは、もう普及していません。ですから、HTMLのコメントをscriptタグに入れる意味はもうありません

<!-- Since Node.js is based on the V8 engine, HTML-like comments are supported by the Node.js runtime too. Moreover, they're a part of the specification: -->

Node.jsはV8エンジンをベースにしているので、HTMLのコメントはNode.jsのランタイムでもサポートされています。さらに、それらは仕様の一部でもあります。

- [**B.1.3** HTML-like Comments](https://www.ecma-international.org/ecma-262/#sec-html-like-comments)

<!-- ## `NaN` is ~~not~~ a number -->

## `Nan`は数字~~ではない~~

<!-- Type of `NaN` is a `'number'`: -->

`NaN`の型は`number`です。

```js
typeof NaN; // -> 'number'
```

### 💡 解説

<!-- Explanations of how `typeof` and `instanceof` operators work: -->

<!-- TODO: -->
次のドキュメントで`typeof` と `instanceof` 演算子がどのように機能するかを解説しています。

- [**12.5.5** The `typeof` Operator](https://www.ecma-international.org/ecma-262/#sec-typeof-operator)
- [**12.10.4** Runtime Semantics: InstanceofOperator(`O`,`C`)](https://www.ecma-international.org/ecma-262/#sec-instanceofoperator)

<!-- ## `[]` and `null` are objects -->

## `[]`と`null`はオブジェクト

```js
typeof []; // -> 'object'
typeof null; // -> 'object'

// however
null instanceof Object; // false
```

### 💡 解説

<!-- The behavior of `typeof` operator is defined in this section of the specification: -->

`typeof`演算子の挙動は、仕様の次の章で定義されています。

- [**12.5.5** The `typeof` Operator](https://www.ecma-international.org/ecma-262/#sec-typeof-operator)

<!-- According to the specification, the `typeof` operator returns a string according to [Table 35: `typeof` Operator Results](https://www.ecma-international.org/ecma-262/#table-35). For `null`, ordinary, standard exotic and non-standard exotic objects, which do not implement `[[Call]]`, it returns the string `"object"`. -->

仕様によると、`typeof`演算子は[Table 35: `typeof` Operator Results](https://www.ecma-international.org/ecma-262/#table-35)に従って文字列を返します。`null`、普通のオブジェクト、標準的なエキゾチックオブジェクト、非標準的なエキゾチックなオブジェクトのうち、`[[Call]]`を実装していないものについては、`"object"`という文字列を返します。

<!-- However, you can check the type of an object by using the `toString` method. -->

しかし，オブジェクトの型を確認するには，`toString`メソッドを使います。

```js
Object.prototype.toString.call([]);
// -> '[object Array]'

Object.prototype.toString.call(new Date());
// -> '[object Date]'

Object.prototype.toString.call(null);
// -> '[object Null]'
```

<!-- ## Magically increasing numbers -->

## 魔法のように増える数字

```js
999999999999999; // -> 999999999999999
9999999999999999; // -> 10000000000000000

10000000000000000; // -> 10000000000000000
10000000000000000 + 1; // -> 10000000000000000
10000000000000000 + 1.1; // -> 10000000000000002
```

### 💡 解説

<!-- This is caused by IEEE 754-2008 standard for Binary Floating-Point Arithmetic. At this scale, it rounds to the nearest even number. Read more: -->

これは、IEEE 754-2008 standard for Binary Floating-Point Arithmeticによるものです。この範囲では、最も近い偶数に丸められます。

- [**6.1.6** The Number Type](https://www.ecma-international.org/ecma-262/#sec-ecmascript-language-types-number-type)
- [IEEE 754](https://ja.wikipedia.org/wiki/IEEE_754) Wikipedia（日本語）

<!-- ## Precision of `0.1 + 0.2` -->

## `0.1 + 0.2`の精度

<!-- A well-known joke. An addition of `0.1` and `0.2` is deadly precise: -->

よくあるジョークです。`0.1`と`0.2`の足し算は、死ぬほど正確です。

```js
0.1 + 0.2; // -> 0.30000000000000004
0.1 + 0.2 === 0.3; // -> false
```

### 💡 解説

<!-- The answer for the [”Is floating point math broken?”](https://stackoverflow.com/questions/588004/is-floating-point-math-broken) question on StackOverflow: -->

次はStackOverflowの[”Is floating point math broken?”](https://stackoverflow.com/questions/588004/is-floating-point-math-broken)の質問に対する回答です。

<!-- > The constants `0.2` and `0.3` in your program will also be approximations to their true values. It happens that the closest `double` to `0.2` is larger than the rational number `0.2` but that the closest `double` to `0.3` is smaller than the rational number `0.3`. The sum of `0.1` and `0.2` winds up being larger than the rational number `0.3` and hence disagreeing with the constant in your code. -->

> プログラム中の定数`0.2`と`0.3`も、真の値に近似の値になります。`0.2`に最も近い`double`は有理数`0.2`よりも大きく、`0.3`に最も近い `double`は有理数`0.3`よりも小さい、ということが起こります。`0.1`と`0.2`の合計は有理数`0.3`よりも大きくなり、コード内の定数とは一致しません。

<!-- This problem is so known that there is even a website called [0.30000000000000004.com](http://0.30000000000000004.com/). It occurs in every language that uses floating-point math, not just JavaScript. -->

この問題は、[0.30000000000000004.com](http://0.30000000000000004.com/)というサイトがあるくらい有名な問題です。JavaScriptに限らず、浮動小数点演算を使うすべての言語で発生します。

<!-- ## Patching numbers -->

## パッチ番号

<!-- You can add your own methods to wrapper objects like `Number` or `String`. -->

`Number`や`String`などのラッパーオブジェクトに独自のメソッドを追加できます。

```js
Number.prototype.isOne = function() {
  return Number(this) === 1;
};

(1.0).isOne(); // -> true
(1).isOne(); // -> true
(2.0).isOne(); // -> false
(7).isOne(); // -> false
```

### 💡 解説

<!-- Obviously, you can extend the `Number` object like any other object in JavaScript. However, it's not recommended if the behavior of the defined method is not a part of the specification. Here is the list of `Number`'s properties: -->

もちろん、JavaScriptの他のオブジェクトと同じように、`Number`オブジェクトを拡張できます。しかし、定義されたメソッドの動作が仕様の一部でない場合はお勧めしません。 `Number`のプロパティのリストは次のとおりです。

- [**20.1** Number Objects](https://www.ecma-international.org/ecma-262/#sec-number-objects)

<!-- ## Comparison of three numbers -->

## 3つの数字の比較

```js
1 < 2 < 3; // -> true
3 > 2 > 1; // -> false
```

### 💡 解説

<!-- Why does this work that way? Well, the problem is in the first part of an expression. Here's how it works: -->

なぜこのような結果になるのでしょうか？それは、式の最初の部分に問題があるからです。その仕組みは次のとおりです。

```js
1 < 2 < 3; // 1 < 2 -> true
true < 3; // true -> 1
1 < 3; // -> true

3 > 2 > 1; // 3 > 2 -> true
true > 1; // true -> 1
1 > 1; // -> false
```

<!-- We can fix this with _Greater than or equal operator (`>=`)_: -->

この問題は、_大なりイコール演算子（`>=`）_ で解決できます。

```js
3 > 2 >= 1; // true
```

<!-- Read more about Relational operators in the specification: -->

関係演算子の仕様の詳細は、次のドキュメントをご覧ください。

- [**12.10** Relational Operators](https://www.ecma-international.org/ecma-262/#sec-relational-operators)

<!-- ## Funny math -->

## おかしな数学

<!-- Often the results of arithmetic operations in JavaScript might be quite unexpected. Consider these examples: -->

JavaScriptでの算術演算の結果は、しばしば思いがけない結果になることがあります。次の例を考えてみましょう。

```js
 3  - 1  // -> 2
 3  + 1  // -> 4
'3' - 1  // -> 2
'3' + 1  // -> '31'

'' + '' // -> ''
[] + [] // -> ''
{} + [] // -> 0
[] + {} // -> '[object Object]'
{} + {} // -> '[object Object][object Object]'

'222' - -'111' // -> 333

[4] * [4]       // -> 16
[] * []         // -> 0
[4, 4] * [4, 4] // NaN
```

### 💡 解説

<!-- What's happening in the first four examples? Here's a small table to understand addition in JavaScript: -->

最初の4つの例では何が起こっているのでしょうか？ここでは、JavaScriptで足し算を理解するための小さな表を用意しました。

```
Number  + Number  -> 足し算
Boolean + Number  -> 足し算
Boolean + Boolean -> 足し算
Number  + String  -> 連結
String  + Boolean -> 連結
String  + String  -> 連結
```

<!-- What about other examples? A `ToPrimitive` and `ToString` methods are being implicitly called for `[]` and `{}` before addition. Read more about evaluation process in the specification: -->

他の例ではどうでしょうか？`ToPrimitive`と`ToString` のメソッドが、追加の前に`[]`と`{}`に対して暗黙のうちに呼び出されています。評価処理については、仕様をご覧ください。

- [**12.8.3** The Addition Operator (`+`)](https://www.ecma-international.org/ecma-262/#sec-addition-operator-plus)
- [**7.1.1** ToPrimitive(`input` [,`PreferredType`])](https://www.ecma-international.org/ecma-262/#sec-toprimitive)
- [**7.1.12** ToString(`argument`)](https://www.ecma-international.org/ecma-262/#sec-tostring)

Notably, `{} + []` here is the exception. The reason why it differs from `[] + {}` is that, without parenthesis, it is interpreted as a code block and then a unary +, converting `[]` into a number. It sees the following:

```js
{
  // a code block here
}
+[]; // -> 0
```

<!-- To get the same output as `[] + {}` we can wrap it in parenthesis. -->

`[] + {}`と同じ出力を得るためには、括弧で囲むことができます。

```js
({} + []); // -> [object Object]
```

<!-- ## Addition of RegExps -->

## RegExpsの追加

<!-- Did you know you can add numbers like this? -->

次のように、数字を加算ができることを知っていましたか？

```js
// Patch a toString method
RegExp.prototype.toString =
  function() {
    return this.source;
  } /
  7 /
  -/5/; // -> 2
```

### 💡 解説

- [**21.2.5.10** get RegExp.prototype.source](https://www.ecma-international.org/ecma-262/#sec-get-regexp.prototype.source)

<!-- ## Strings aren't instances of `String` -->

## 文字列は `String` のインスタンスではありません

```js
"str"; // -> 'str'
typeof "str"; // -> 'string'
"str" instanceof String; // -> false
```

### 💡 解説

<!-- The `String` constructor returns a string: -->

`String`のコンストラクタは文字列を返します。

```js
typeof String("str"); // -> 'string'
String("str"); // -> 'str'
String("str") == "str"; // -> true
```

<!-- Let's try with a `new`: -->

では、`new`で試してみます。

```js
new String("str") == "str"; // -> true
typeof new String("str"); // -> 'object'
```

<!-- Object? What's that? -->

オブジェクト？何なのでしょうか？

```js
new String("str"); // -> [String: 'str']
```

<!-- More information about the String constructor in the specification: -->

`String`コンストラクタについての仕様の詳細はこちらのドキュメントをご覧ください。

- [**21.1.1** The String Constructor](https://www.ecma-international.org/ecma-262/#sec-string-constructor)

<!-- ## Calling functions with backticks -->

## バックティック文字を使った関数の呼び出し

<!-- Let's declare a function which logs all params into the console: -->

すべての引数を出力する関数を定義してみましょう。

```js
function f(...args) {
  return args;
}
```

<!-- No doubt, you know you can call this function like this: -->

間違いなく、あなたはこの関数を次のように呼び出せることを知っています。

```js
f(1, 2, 3); // -> [ 1, 2, 3 ]
```

<!-- But did you know you can call any function with backticks? -->

しかし、任意の関数をバックティック文字で呼び出せることを知っていましたか？

```js
f`true is ${true}, false is ${false}, array is ${[1, 2, 3]}`;
// -> [ [ 'true is ', ', false is ', ', array is ', '' ],
// ->   true,
// ->   false,
// ->   [ 1, 2, 3 ] ]
```

### 💡 解説

Well, this is not magic at all if you're familiar with _Tagged template literals_. In the example above, `f` function is a tag for template literal. Tags before template literal allow you to parse template literals with a function. The first argument of a tag function contains an array of string values. The remaining arguments are related to the expressions. Example:


_タグ付きテンプレートリテラル_ に慣れている人にとっては、これは全然魔法ではありません。上の例では、関数`f`がテンプレートリテラルのタグになっています。テンプレートリテラルの前のタグは、テンプレートリテラルを関数で解析できます。タグ関数の最初の引数には，文字列値の配列が入ります。残りの引数は式に関連しています。

```js
function template(strings, ...keys) {
  // do something with strings and keys…
}
```

<!-- This is the [magic behind](http://mxstbr.blog/2016/11/styled-components-magic-explained/) famous library called [💅 styled-components](https://www.styled-components.com/), which is popular in the React community. -->

これは、Reactコミュニティで有名な[💅 styled-components](https://www.styled-components.com/)というライブラリの[魔法](http://mxstbr.blog/2016/11/styled-components-magic-explained/)です。

<!-- Link to the specification: -->

仕様へのリンクです。

- [**12.3.7** Tagged Templates](https://www.ecma-international.org/ecma-262/#sec-tagged-templates)

<!-- ## Call call call -->

## コール コール コール

<!-- > Found by [@cramforce](http://twitter.com/cramforce) -->

> 発見者：[@cramforce](http://twitter.com/cramforce)

```js
console.log.call.call.call.call.call.apply(a => a, [1, 2]);
```

### 💡 解説

Attention, it could break your mind! Try to reproduce this code in your head: we're applying the `call` method using the `apply` method. Read more:

ご注意ください。あなたの心を壊すかもしれません！このコードを頭の中で再現してみてください。`call`メソッドを`apply`メソッドを使って適用しています。

もっと読む：

- [**19.2.3.3** Function.prototype.call(`thisArg`, ...`args`)](https://www.ecma-international.org/ecma-262/#sec-function.prototype.call)
- [**19.2.3.1 ** Function.prototype.apply(`thisArg`, `argArray`)](https://www.ecma-international.org/ecma-262/#sec-function.prototype.apply)

<!-- ## A `constructor` property -->

## `constructor`のプロパティ

```js
const c = "constructor";
c[c][c]('console.log("WTF?")')(); // > WTF?
```

### 💡 解説

<!-- Let's consider this example step-by-step: -->

上記のサンプルコードを、順を追って考えてみます。

<!-- ```js
// Declare a new constant which is a string 'constructor'
const c = "constructor";

// c is a string
c; // -> 'constructor'

// Getting a constructor of string
c[c]; // -> [Function: String]

// Getting a constructor of constructor
c[c][c]; // -> [Function: Function]

// Call the Function constructor and pass
// the body of new function as an argument
c[c][c]('console.log("WTF?")'); // -> [Function: anonymous]

// And then call this anonymous function
// The result is console-logging a string 'WTF?'
c[c][c]('console.log("WTF?")')(); // > WTF?
``` -->

```js
// 文字列 'constructor' の新しい定数を宣言
const c = "constructor";

// c は文字列
c; // -> 'constructor'

// 文字列のコンストラクタの取得
c[c]; // -> [Function: String]

// コンストラクタのコンストラクタを取得
c[c][c]; // -> [Function: Function]

// 関数のコンストラクタを呼び出し、新しい関数の本体を引数として渡す
c[c][c]('console.log("WTF?")'); // -> [Function: anonymous]

// そして、この匿名関数を呼び出す
// 結果はconsole.logで文字列 'WTF?' を出力
c[c][c]('console.log("WTF?")')(); // > WTF?
```

<!-- An `Object.prototype.constructor` returns a reference to the `Object` constructor function that created the instance object. In case with strings it is `String`, in case with numbers it is `Number` and so on. -->

`Object.prototype.constructor`は、インスタンスオブジェクトを生成した`Object`コンストラクタ関数への参照を返します。文字列の場合は`String`、数字の場合は`Number`になります。

- [`Object.prototype.constructor`](https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/constructor) at MDN
- [**19.1.3.1** Object.prototype.constructor](https://www.ecma-international.org/ecma-262/#sec-object.prototype.constructor)

<!-- ## Object as a key of object's property -->

## オブジェクトのプロパティのキーとしてのオブジェクト

```js
{ [{}]: {} } // -> { '[object Object]': {} }
```

### 💡 解説

<!-- Why does this work so? Here we're using a _Computed property name_. When you pass an object between those brackets, it coerces object to a string, so we get the property key `'[object Object]'` and the value `{}`. -->

なぜこのような動作になるのでしょうか？ここでは、_Computed property names_ を使用しています。括弧`[]`の間にオブジェクトを渡すと、オブジェクトが文字列に変換されため、プロパティキー`'[object Object]'`と値`{}`を返します。

<!-- We can make "brackets hell" like this: -->

次のように「括弧地獄」を作ることができます。

```js
({ [{}]: { [{}]: {} } }[{}][{}]); // -> {}

// structure:
// {
//   '[object Object]': {
//     '[object Object]': {}
//   }
// }
```

<!-- Read more about object literals here: -->

オブジェクトリテラルの詳細はこちらのドキュメントをご覧ください。

- [Object initializer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer) at MDN
- [**12.2.6** Object Initializer](http://www.ecma-international.org/ecma-262/6.0/#sec-object-initializer)

<!-- ## Accessing prototypes with `__proto__` -->

## `__proto__` でプロトタイプにアクセスする

<!-- As we know, primitives don't have prototypes. However, if we try to get a value of `__proto__` for primitives, we would get this: -->

ご存知のように、プリミティブにはプロトタイプがありません。しかし、プリミティブの `__proto__` の値を取得しようとすると、次のようになります。

```js
(1).__proto__.__proto__.__proto__; // -> null
```

### 💡 解説

<!-- This happens because when something doesn't have a prototype, it will be wrapped into a wrapper object using the `ToObject` method. So, step-by-step: -->

この挙動は、プロトタイプを持たない場合は`ToObject`メソッドを使ってラッパーオブジェクトにラッピングされるために起こります。順を追ってみてみます。

```js
(1).__proto__; // -> [Number: 0]
(1).__proto__.__proto__; // -> {}
(1).__proto__.__proto__.__proto__; // -> null
```

<!-- Here is more information about `__proto__`: -->

`__proto__`の詳細はこちらのドキュメントをご覧ください。

- [**B.2.2.1** Object.prototype.**proto**](https://www.ecma-international.org/ecma-262/#sec-object.prototype.__proto__)
- [**7.1.13** ToObject(`argument`)](https://www.ecma-international.org/ecma-262/#sec-toobject)

## `` `${{Object}}` ``

<!-- What is the result of the expression below? -->

下の式の結果はどうなりますか？

```js
`${{ Object }}`;
```

<!-- The answer is: -->

答えはこちら。

```js
// -> '[object Object]'
```

### 💡 解説

<!-- We defined an object with a property `Object` using _Shorthand property notation_: -->

_Shorthand property notation_ を利用し、プロパティ `Object` を持つオブジェクトを定義しました。

```js
{
  Object: Object;
}
```

<!-- Then we've passed this object to the template literal, so the `toString` method calls for that object. That's why we get the string `'[object Object]'`. -->

そして、このオブジェクトをテンプレートリテラルに渡しているので、`toString`メソッドはそのオブジェクトを呼び出しています。これが、文字列 `'[object Object]'を返す理由です。

- [**12.2.9** Template Literals](https://www.ecma-international.org/ecma-262/#sec-template-literals)
- [Object initializer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer) at MDN

<!-- ## Destructuring with default values -->

## デフォルト値を使った分割代入

<!-- Consider this example: -->

次の例を考えてみてください。

```js
let x,
  { x: y = 1 } = { x };
y;
```

<!-- The example above is a great task for an interview. What the value of `y`? The answer is: -->

上の例は、面接時の素晴らしい課題になります。`y`の値は何になりますか？

答えはこちら。

```js
// -> 1
```

### 💡 解説

```js
let x,
  { x: y = 1 } = { x };
y;
//  ↑       ↑           ↑    ↑
//  1       3           2    4
```

<!-- With the example above: -->

上の例だと：

<!-- 1. We declare `x` with no value, so it's `undefined`.
2. Then we pack the value of `x` into the object property `x`.
3. Then we extract the value of `x` using destructuring and want to assign it to `y`. If the value is not defined, then we're going to use `1` as the default value.
4. Return the value of `y`. -->

1. `x`は初期値無しで宣言しているので`undefined`になります。
2. そして、`x`の値をオブジェクトのプロパティ`x`に代入します。
3. そして、分割代入を使って`x`の値を抽出し、それを`y`に代入します。値が定義されていない場合は、デフォルト値として`1`が入ります。
4. `y`の値を返します。

- [Object initializer](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Object_initializer) at MDN

<!-- ## Dots and spreading -->

## ドットとスプレッド

<!-- Interesting examples could be composed with spreading of arrays. Consider this: -->

面白い例は、配列のスプレッド構文で構成されています。こちらを考えてみましょう。

```js
[...[..."..."]].length; // -> 3
```

### 💡 解説

<!-- Why `3`? When we use the [spread operator](http://www.ecma-international.org/ecma-262/6.0/#sec-array-initializer), the `@@iterator` method is called, and the returned iterator is used to obtain the values to be iterated. The default iterator for string spreads a string into characters. After spreading, we pack these characters into an array. Then we spread this array again and pack it back to an array. -->

どうして`3`になるのでしょうか？
[スプレッド構文](http://www.ecma-international.org/ecma-262/6.0/#sec-array-initializer)を使うと、`@@iterator`メソッドが呼び出され、返されたイテレータを使って反復して値を取得します。
文字列のデフォルトのイテレータは、文字列を文字にスプレッドします。スプレッドした後，これらの文字を配列に代入します。そして、この配列を再びスプレットし、再び配列に代入します。

<!-- A `'...'` string consists with three `.` characters, so the length of resulting array is `3`. -->

`...`の文字列は3つの`.`で構成されているので、配列の長さは`3`となります。

<!-- Now, step-by-step: -->

順を追ってみます。

```js
[...'...']             // -> [ '.', '.', '.' ]
[...[...'...']]        // -> [ '.', '.', '.' ]
[...[...'...']].length // -> 3
```

<!-- Obviously, we can spread and wrap the elements of an array as many times as we want: -->

もちろん、配列の要素を何度でもスプレットしたりラップできます。

<!-- ```js
[...'...']                 // -> [ '.', '.', '.' ]
[...[...'...']]            // -> [ '.', '.', '.' ]
[...[...[...'...']]]       // -> [ '.', '.', '.' ]
[...[...[...[...'...']]]]  // -> [ '.', '.', '.' ]
// and so on …
``` -->

```js
[...'...']                 // -> [ '.', '.', '.' ]
[...[...'...']]            // -> [ '.', '.', '.' ]
[...[...[...'...']]]       // -> [ '.', '.', '.' ]
[...[...[...[...'...']]]]  // -> [ '.', '.', '.' ]
// などなど …
```

## Labels

## ラベル

<!-- Not many programmers know about labels in JavaScript. They are kind of interesting: -->

JavaScriptのラベルを知っているプログラマーは少ないと思います。ラベルはすこし面白いです。

```js
foo: {
  console.log("first");
  break foo;
  console.log("second");
}

// > first
// -> undefined
```

### 💡 解説

<!-- The labeled statement is used with `break` or `continue` statements. You can use a label to identify a loop, and then use the `break` or `continue` statements to indicate whether a program should interrupt the loop or continue its execution. -->

ラベル付き文は、`break`文や`continue`文と一緒に使います。ラベルを使ってループを識別し、`break`文や`continue`文を使って、プログラムがループを中断すべきか、実行を継続すべきかを明示できます。

<!-- In the example above, we identify a label `foo`. After that `console.log('first');` executes and then we interrupt the execution. -->

上の例では、まずラベル`foo`を識別し、`console.log('first');`を実行した後、処理を中断します。

<!-- Read more about labels in JavaScript: -->

ラベルの仕様の詳細は、次のドキュメントをご覧ください。

- [**13.13** Labelled Statements](https://tc39.github.io/ecma262/#sec-labelled-statements)
- [Labeled statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label) at MDN

<!-- ## Nested labels -->

## 入れ子のレベル

```js
a: b: c: d: e: f: g: 1, 2, 3, 4, 5; // -> 5
```

### 💡 解説

<!-- Similar to previous examples, follow these links: -->

これまでの例と同様、次のドキュメントをご覧ください。

- [**12.16** Comma Operator (`,`)](https://www.ecma-international.org/ecma-262/#sec-comma-operator)
- [**13.13** Labelled Statements](https://tc39.github.io/ecma262/#sec-labelled-statements)
- [Labeled statements](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label) at MDN

<!-- ## Insidious `try..catch` -->

## 狡猾な`try..catch`

<!-- What will this expression return? `2` or `3`? -->

次の式は`2`か`3`のどちらを返すでしょうか？

```js
(() => {
  try {
    return 2;
  } finally {
    return 3;
  }
})();
```

<!-- The answer is `3`. Surprised? -->

答えは`3`になります。驚きましたか？

### 💡 解説

- [**13.15** The `try` Statement](https://www.ecma-international.org/ecma-262/#sec-try-statement)

<!-- ## Is this multiple inheritance? -->

## これは多重継承ですか？

<!-- Take a look at the example below: -->

下の例をご覧ください。

```js
new class F extends (String, Array) {}(); // -> F []
```

<!-- Is this a multiple inheritance? Nope. -->

これは多重継承ですか？いいえ、そうではありません。

### 💡 解説

<!-- The interesting part is the value of the `extends` clause (`(String, Array)`). The grouping operator always returns its last argument, so `(String, Array)` is actually just `Array`. That means we've just created a class which extends `Array`. -->

面白いのは、`extends`キーワードの値「`(String, Array)`」です。グループ化演算子は常に最後の引数を返すので、`(String, Array)`は実際には単に`Array`になります。つまり、`Array`を拡張したクラスを作成したことになります。

- [**14.5** Class Definitions](https://www.ecma-international.org/ecma-262/#sec-class-definitions)
- [**12.16** Comma Operator (`,`)](https://www.ecma-international.org/ecma-262/#sec-comma-operator)

<!-- ## A generator which yields itself -->

## 自分自身をyieldするジェネレーター

<!-- Consider this example of a generator which yields itself: -->

自分自身をyieldするジェネレーターを考えてみます。

```js
(function* f() {
  yield f;
})().next();
// -> { value: [GeneratorFunction: f], done: false }
```

<!-- As you can see, the returned value is an object with its `value` equal to `f`. In that case, we can do something like this: -->

お分かりのように、戻り値は`f`に等しい`value`プロパティを持ったオブジェクトになります。これは、次のようにできます。

```js
(function* f() {
  yield f;
})()
  .next()
  .value()
  .next()(
    // -> { value: [GeneratorFunction: f], done: false }

    // そして再び
    function* f() {
      yield f;
    }
  )()
  .next()
  .value()
  .next()
  .value()
  .next()(
    // -> { value: [GeneratorFunction: f], done: false }

    // そして再び
    function* f() {
      yield f;
    }
  )()
  .next()
  .value()
  .next()
  .value()
  .next()
  .value()
  .next();
// -> { value: [GeneratorFunction: f], done: false }

// などなど
// …
```

### 💡 解説

<!-- To understand why this works that way, read these sections of the specification: -->

なぜこのように機能するかを理解するには、仕様の次のドキュメントをご覧ください。

- [**25** Control Abstraction Objects](https://www.ecma-international.org/ecma-262/#sec-control-abstraction-objects)
- [**25.3** Generator Objects](https://www.ecma-international.org/ecma-262/#sec-generator-objects)

<!-- ## A class of class -->

## クラスのクラス

<!-- Consider this obfuscated syntax playing: -->

次の難解な構文を考えてみましょう。

```js
typeof new class {
  class() {}
}(); // -> 'object'
```

<!-- It seems like we're declaring a class inside of class. Should be an error, however, we get the string `'object'`. -->

一見、クラスの中でクラスを宣言しているように見えます。エラーになるはずですが、文字列`'object'`を取得しています。

### 💡 解説

<!-- Since ECMAScript 5 era, _keywords_ are allowed as _property names_. So think about it as this simple object example: -->

ECMAScript 5の時代から、_キーワード_ は _プロパティ名_ として認められています。<!-- なので、-->以下の単純なオブジェクトを例として考えてみてください。

```js
const foo = {
  class: function() {}
};
```

<!-- And ES6 standardized shorthand method definitions. Also, classes can be anonymous. So if we drop `: function` part, we're going to get: -->

ES6ではショートハンドメソッドの定義を標準化しました。あわせて、クラスは匿名にできます。 
なので、`: function`の部分を削除すると、次のようになります。

```js
class {
  class() {}
}
```

<!-- The result of a default class is always a simple object. And its typeof should return `'object'`. -->

デフォルトのクラスの結果は常に単純なオブジェクトです。そして、typeof演算子は`'object'`を返さなければなりません。

<!-- Read more here: -->

詳細は以下のドキュメントをご覧ください。

- [**14.3** Method Definitions](https://www.ecma-international.org/ecma-262/#sec-method-definitions)
- [**14.5** Class Definitions](https://www.ecma-international.org/ecma-262/#sec-class-definitions)

## Non-coercible objects

With well-known symbols, there's a way to get rid of type coercion. Take a look:

```js
function nonCoercible(val) {
  if (val == null) {
    throw TypeError("nonCoercible should not be called with null or undefined");
  }

  const res = Object(val);

  res[Symbol.toPrimitive] = () => {
    throw TypeError("Trying to coerce non-coercible object");
  };

  return res;
}
```

Now we can use this like this:

```js
// objects
const foo = nonCoercible({ foo: "foo" });

foo * 10; // -> TypeError: Trying to coerce non-coercible object
foo + "evil"; // -> TypeError: Trying to coerce non-coercible object

// strings
const bar = nonCoercible("bar");

bar + "1"; // -> TypeError: Trying to coerce non-coercible object
bar.toString() + 1; // -> bar1
bar === "bar"; // -> false
bar.toString() === "bar"; // -> true
bar == "bar"; // -> TypeError: Trying to coerce non-coercible object

// numbers
const baz = nonCoercible(1);

baz == 1; // -> TypeError: Trying to coerce non-coercible object
baz === 1; // -> false
baz.valueOf() === 1; // -> true
```

### 💡 Explanation:

- [A gist by Sergey Rubanov](https://gist.github.com/chicoxyzzy/5dd24608e886adf5444499896dff1197)
- [**6.1.5.1** Well-Known Symbols](https://www.ecma-international.org/ecma-262/#sec-well-known-symbols)

## Tricky arrow functions

Consider the example below:

```js
let f = () => 10;
f(); // -> 10
```

Okay, fine, but what about this:

```js
let f = () => {};
f(); // -> undefined
```

### 💡 Explanation:

You might expect `{}` instead of `undefined`. This is because the curly braces are part of the syntax of the arrow functions, so `f` will return undefined. It is however possible to return the `{}` object directly from an arrow function, by enclosing the return value with brackets.

```js
let f = () => ({});
f(); // -> {}
```

## Arrow functions can not be a constructor

Consider the example below:

```js
let f = function() {
  this.a = 1;
};
new f(); // -> f { 'a': 1 }
```

Now, try do to the same with an arrow function:

```js
let f = () => {
  this.a = 1;
};
new f(); // -> TypeError: f is not a constructor
```

### 💡 Explanation:

Arrow functions cannot be used as constructors and will throw an error when used with new. Because has a lexical `this`, and do not have a `prototype` property, so it would not make much sense.

## `arguments` and arrow functions

Consider the example below:

```js
let f = function() {
  return arguments;
};
f("a"); // -> { '0': 'a' }
```

Now, try do to the same with an arrow function:

```js
let f = () => arguments;
f("a"); // -> Uncaught ReferenceError: arguments is not defined
```

### 💡 Explanation:

Arrow functions are a lightweight version of regular functions with a focus on being short and lexical `this`. At the same time arrow functions do not provide a binding for the `arguments` object. As a valid alternative use the `rest parameters` to achieve the same result:

```js
let f = (...args) => args;
f("a");
```

- [Arrow functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) at MDN.

## Tricky return

`return` statement is also tricky. Consider this:

<!-- prettier-ignore-start -->
```js
(function() {
  return
  {
    b: 10;
  }
})(); // -> undefined
```
<!-- prettier-ignore-end -->

### 💡 Explanation:

`return` and the returned expression must be in the same line:

```js
(function() {
  return {
    b: 10
  };
})(); // -> { b: 10 }
```

This is because of a concept called Automatic Semicolon Insertion, which automagically inserts semicolons after most newlines. In the first example, there is a semicolon inserted between the `return` statement and the object literal, so the function returns `undefined` and the object literal is never evaluated.

- [**11.9.1** Rules of Automatic Semicolon Insertion](https://www.ecma-international.org/ecma-262/#sec-rules-of-automatic-semicolon-insertion)
- [**13.10** The `return` Statement](https://www.ecma-international.org/ecma-262/#sec-return-statement)

## Chaining assignments on object

```js
var foo = { n: 1 };
var bar = foo;

foo.x = foo = { n: 2 };

foo.x; // -> undefined
foo; // -> {n: 2}
bar; // -> {n: 1, x: {n: 2}}
```

From right to left, `{n: 2}` is assigned to foo, and the result of this assignment `{n: 2}` is assigned to foo.x, that's why bar is `{n: 1, x: {n: 2}}` as bar is a reference to foo. But why foo.x is undefined while bar.x is not ?

### 💡 Explanation:

Foo and bar references the same object `{n: 1}`, and lvalues are resolved before assignations. `foo = {n: 2}` is creating a new object, and so foo is updated to reference that new object. The trick here is foo in `foo.x = ...` as a lvalue was resolved beforehand and still reference the old `foo = {n: 1}` object and update it by adding the x value. After that chain assignments, bar still reference the old foo object, but foo reference the new `{n: 2}` object, where x is not existing.

It's equivalent to:

```js
var foo = { n: 1 };
var bar = foo;

foo = { n: 2 }; // -> {n: 2}
bar.x = foo; // -> {n: 1, x: {n: 2}}
// bar.x point to the address of the new foo object
// it's not equivalent to: bar.x = {n: 2}
```

## Accessing object properties with arrays

```js
var obj = { property: 1 };
var array = ["property"];

obj[array]; // -> 1
```

What about pseudo-multidimensional arrays?

```js
var map = {};
var x = 1;
var y = 2;
var z = 3;

map[[x, y, z]] = true;
map[[x + 10, y, z]] = true;

map["1,2,3"]; // -> true
map["11,2,3"]; // -> true
```

### 💡 Explanation:

The brackets `[]` operator converts the passed expression using `toString`. Converting a one-element array to a string is akin to converting the contained element to the string:

```js
["property"].toString(); // -> 'property'
```

## Null and Relational Operators

```js
null > 0; // false
null == 0; // false

null >= 0; // true
```

### 💡 Explanation:

Long story short, if `null` is less than `0` is `false`, then `null >= 0` is `true`. Read in-depth explanation for this [here](https://blog.campvanilla.com/javascript-the-curious-case-of-null-0-7b131644e274).

## `Number.toFixed()` display different numbers

`Number.toFixed()` can behave a bit strange in different browsers. Check out this example:

```js
(0.7875).toFixed(3);
// Firefox: -> 0.787
// Chrome: -> 0.787
// IE11: -> 0.788
(0.7876).toFixed(3);
// Firefox: -> 0.788
// Chrome: -> 0.788
// IE11: -> 0.788
```

### 💡 Explanation:

While your first instinct may be that IE11 is correct and Firefox/Chrome are wrong, the reality is that Firefox/Chrome are more directly obeying standards for numbers (IEEE-754 Floating Point), while IE11 is minutely disobeying them in (what is probably) an effort to give clearer results.

You can see why this occurs with a few quick tests:

```js
// Confirm the odd result of rounding a 5 down
(0.7875).toFixed(3); // -> 0.787
// It looks like it's just a 5 when you expand to the
// limits of 64-bit (double-precision) float accuracy
(0.7875).toFixed(14); // -> 0.78750000000000
// But what if you go beyond the limit?
(0.7875).toFixed(20); // -> 0.78749999999999997780
```

Floating point numbers are not stored as a list of decimal digits internally, but through a more complicated methodology that produces tiny inaccuracies that are usually rounded away by toString and similar calls, but are actually present internally.

In this case, that "5" on the end was actually an extremely tiny fraction below a true 5. Rounding it at any reasonable length will render it as a 5... but it is actually not a 5 internally.

IE11, however, will report the value input with only zeros appended to the end even in the toFixed(20) case, as it seems to be forcibly rounding the value to reduce the troubles from hardware limits.

See for reference `NOTE 2` on the ECMA-262 definition for `toFixed`.

- [**20.1.3.3** Number.prototype.toFixed (`fractionDigits`)](https://www.ecma-international.org/ecma-262//#sec-number.prototype.tofixed)

## `Math.max()` less than `Math.min()`

```js
Math.min(1, 4, 7, 2); // -> 1
Math.max(1, 4, 7, 2); // -> 7
Math.min(); // -> Infinity
Math.max(); // -> -Infinity
Math.min() > Math.max(); // -> true
```

### 💡 Explanation:

- [Why is Math.max() less than Math.min()?](https://charlieharvey.org.uk/page/why_math_max_is_less_than_math_min) by Charlie Harvey

## Comparing `null` to `0`

The following expressions seem to introduce a contradiction:

```js
null == 0; // -> false
null > 0; // -> false
null >= 0; // -> true
```

How can `null` be neither equal to nor greater than `0`, if `null >= 0` is actually `true`? (This also works with less than in the same way.)

### 💡 Explanation:

The way these three expressions are evaluated are all different and are responsible for producing this unexpected behavior.

First, the abstract equality comparison `null == 0`. Normally, if this operator can't compare the values on either side properly, it converts both to numbers and compares the numbers. Then, you might expect the following behavior:

```js
// This is not what happens
(null == 0 + null) == +0;
0 == 0;
true;
```

However, according to a close reading of the spec, the number conversion doesn't actually happen on a side that is `null` or `undefined`. Therefore, if you have `null` on one side of the equal sign, the other side must be `null` or `undefined` for the expression to return `true`. Since this is not the case, `false` is returned.

Next, the relational comparison `null > 0`. The algorithm here, unlike that of the abstract equality operator, _will_ convert `null` to a number. Therefore, we get this behavior:

```js
null > 0
+null = +0
0 > 0
false
```

Finally, the relational comparison `null >= 0`. You could argue that this expression should be the result of `null > 0 || null == 0`; if this were the case, then the above results would mean that this would also be `false`. However, the `>=` operator in fact works in a very different way, which is basically to take the opposite of the `<` operator. Because our example with the greater than operator above also holds for the less than operator, that means this expression is actually evaluated like so:

```js
null >= 0;
!(null < 0);
!(+null < +0);
!(0 < 0);
!false;
true;
```

- [**7.2.12** Abstract Relational Comparison](https://www.ecma-international.org/ecma-262/#sec-abstract-relational-comparison)
- [**7.2.15** Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison)

## Same variable redeclaration

JS allows to redeclare variables:

```js
a;
a;
// This is also valid
a, a;
```

Works also in strict mode:

```js
var a, a, a;
var a;
var a;
```

### 💡 Explanation:

All definitions are merged into one definition.

- [**13.3.2** Variable Statement](https://www.ecma-international.org/ecma-262/#sec-variable-statement)

## Default behavior Array.prototype.sort()

Imagine that you need to sort an array of numbers.

```js
[10, 1, 3].sort(); // -> [ 1, 10, 3 ]
```

### 💡 Explanation:

The default sort order is built upon converting the elements into strings, then comparing their sequences of UTF-16 code units values.

- [**22.1.3.25** Array.prototype.sort ( comparefn )](https://www.ecma-international.org/ecma-262/#sec-array.prototype.sort)

### Hint

Pass `compareFn` if you try to sort anything but string.

```js
[10, 1, 3].sort((a, b) => a - b); // -> [ 1, 3, 10 ]
```

## resolve() won't return Promise instance

```js
const theObject = {
  a: 7
};
const thePromise = new Promise((resolve, reject) => {
  resolve(theObject);
}); // Promise instance object

thePromise.then(value => {
  console.log(value === theObject); // > true
  console.log(value); // > { a: 7 }
});
```

The `value` which is resolved from `thePromise` is exactly `theObject`.

How about input another `Promise` into the `resolve` function?

```js
const theObject = new Promise((resolve, reject) => {
  resolve(7);
}); // Promise instance object
const thePromise = new Promise((resolve, reject) => {
  resolve(theObject);
}); // Promise instance object

thePromise.then(value => {
  console.log(value === theObject); // > false
  console.log(value); // > 7
});
```

### 💡 Explanation:

> This function flattens nested layers of promise-like objects (e.g. a promise that resolves to a promise that resolves to something) into a single layer.

- [Promise.resolve() on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/resolve)

The specification is [ECMAScript 25.6.1.3.2 Promise Resolve Functions](https://tc39.es/ecma262/#sec-promise-resolve-functions). But it is not quite human-friendly.

## `{}{}` is undefined

Write them in the console. They will return the value defined in the last object.

```js
{}{}; // -> undefined
{}{}{}; // -> undefined
{}{}{}{}; // -> undefined
{foo: 'bar'}{}; // -> 'bar'
{}{foo: 'bar'}; // -> 'bar'
{}{foo: 'bar'}{}; // -> 'bar'
{a: 'b'}{c:' d'}{}; // -> 'd'
{a: 'b', c: 'd'}{}; // > SyntaxError: Unexpected token ':'
({}{}); // > SyntaxError: Unexpected token '{'
```

### 💡 Explanation:

When inspecting each `{}`, they returns undefined. If you inspect `{foo: 'bar'}{}`, you will find `{foo: 'bar'}` is `'bar'`.

There are two meanings for `{}`: an object or a block. For example, the `{}` in `() => {}` means block. So we need to use `() => ({}`) to return an object.

Let's use `{foo: 'bar'}` as a block. Write this snippet in your console:

```js
if (true) {
  foo: "bar";
} // -> 'bar'
```

Surprisingly, it behaviors the same! You can guess here that `{foo: 'bar'}{}` is a block.

## `min` is greater than `max`

I find this example hilarious:

```js
Math.min() > Math.max(); // -> true
Math.min() < Math.max(); // -> false
```

### 💡 Explanation:

This is a simple one. Let's consider each part of this expression separately:

```js
Math.min(); // -> Infinity
Math.max(); // -> -Infinity
Infinity > -Infinity; // -> true
```

Why so? Well, `Math.max()` is not the same thing as `Number.MAX_VALUE`. It does not return the largest possible number.

`Math.max` takes arguments, tries to convert the to numbers, compares each one and then returns the largest remaining. If no arguments are given, the result is −∞. If any value is `NaN`, the result is `NaN`.

The opposite is happening for `Math.min`. `Math.min` returns ∞, if no arguments are given.

- [**15.8.2.11** Math.max](https://262.ecma-international.org/5.1/#sec-15.8.2.11)
- [**15.8.2.11** Math.min](https://262.ecma-international.org/5.1/#sec-15.8.2.12)
- [Why is `Math.max()` less than `Math.min()`?](https://charlieharvey.org.uk/page/why_math_max_is_less_than_math_min)

## `arguments` binding

Consider this function:

```js
function a(x) {
  arguments[0] = "hello";
  console.log(x);
}

a(); // > undefined
a(1); // > "hello"
```

### 💡 Explanation:

`arguments` is an Array-like object that contains the values of the arguments passed to that function. When no arguments are passed, then there's no `x` to override.

- [The arguments object](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments) on MDN

## An `alert` from hell

This on is literally from hell:

```js
[666]["\155\141\160"]["\143\157\156\163\164\162\165\143\164\157\162"](
  "\141\154\145\162\164(666)"
)(666); // alert(666)
```

### 💡 Explanation:

This one is based on octal escape sequences and multiple strings.

Any character with a character code lower than 256 (i.e. any character in the extended ASCII range) can be escaped using its octal-encoded character code, prefixed with `\`. An example above is basically and `alert` ecoded by octal escape sequances.

- [Martin Kleppe tweet about it](https://twitter.com/aemkei/status/897172907222237185)
- [JavaScript character escape sequences](https://mathiasbynens.be/notes/javascript-escapes#octal)
- [Multi-Line JavaScript Strings](https://davidwalsh.name/multiline-javascript-strings)

## An infinite timeout

Guess what would happen if we set an infinite timeout?

```js
setTimeout(() => console.log("called"), Infinity); // -> <timeoutId>
// > 'called'
```

It will executed immediately instead of infinity delay.

### 💡 Explanation:

Usually, runtime stores the delay as a 32-bit signed integer internally. This causes an integer overflow, resulting in the timeout being executed immediately.

For example, in Node.js we will get this warning:

```
(node:1731) TimeoutOverflowWarning: Infinity does not fit into a 32-bit signed integer.
Timeout duration was set to 1.
(Use `node --trace-warnings ...` to show where the warning was created)
```

- [WindowOrWorkerGlobalScope.setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout) on MDN
- [Node.js Documentation on Timers](https://nodejs.org/api/timers.html#timers_settimeout_callback_delay_args)
- [Timers](https://www.w3.org/TR/2011/WD-html5-20110525/timers.html) on W3C

## A `setTimeout` object

Guess what would happen if we set an callback that's not a function to `setTimeout`?

```js
setTimeout(123, 100); // -> <timeoutId>
// > 'called'
```

This is fine.

```js
setTimeout('{a: 1}', 100); // -> <timeoutId>
// > 'called'
```

This is also fine.

```js
setTimeout({a: 1}, 100); // -> <timeoutId>
// > 'Uncaught SyntaxError: Unexpected identifier               setTimeout (async) (anonymous) @ VM__:1'
```

This throws an **SyntaxError**.

Note that this can easily happen if your function returns an object and you call it here instead of passing it! What if the content - policy is set to `self`?

```js
setTimeout(123, 100); // -> <timeoutId>
// > console.error("[Report Only] Refused to evaluate a string as JavaScript because 'unsafe-eval' is not an allowed source of script in the following Content Security Policy directive: "script-src 'report-sample' 'self' ")
```

The console refuses to run it at all!

### 💡 Explanation:

`WindowOrWorkerGlobalScope.setTimeout()` can be called with `code` as first argument, which will be passed on to `eval`, which is bad. Eval will coerce her input to String, and evaluate what is produced, so Objects becomes `'[object Object]'` which has hmmm ...  an `'Unexpected identifier'`!

- [eval()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval) on MDN (don't use this)
- [WindowOrWorkerGlobalScope.setTimeout()](https://developer.mozilla.org/en-US/docs/Web/API/WindowOrWorkerGlobalScope/setTimeout) on MDN
- [Content Security Policy](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy)
- [Timers](https://www.w3.org/TR/2011/WD-html5-20110525/timers.html) on W3C

## Double dot

Let's try to coerce a number to a string:

```js
27.toString() // > Uncaught SyntaxError: Invalid or unexpected token
```

Maybe we should try with two dots?

```js
27..toString(); // -> '27'
```

But why doesn't first example work?

### 💡 Explanation:

It's just a language grammar limitation.

The `.` character presents an ambiguity. It can be understood to be the member operator, or a decimal, depending on its placement.

The specification's interpretation of the `.` character in that particular position is that it will be a decimal. This is defined by the numeric literal syntax of ECMAScript.

You must always use parenthesis or an addition dot to make such expression valid.

```js
(27).toString(); // -> '27'
// or
27..toString(); // -> '27'
```

- [Usage of toString in JavaScript](https://stackoverflow.com/questions/6853865/usage-of-tostring-in-javascript/6853910#6853910) on StackOverflow
- [Why does 10..toString() work, but 10.toString() does not?](https://stackoverflow.com/questions/13149282/why-does-10-tostring-work-but-10-tostring-does-not/13149301#13149301)

## Extra Newness

I present this as an oddity for your amusement.

```js
class Foo extends Function {
  constructor(val) {
    super();
    this.prototype.val = val;
  }
}

new new Foo(":D")().val; // -> ':D'
```

### 💡 Explanation:

Constructors in JavaScript are just functions with some special treatment. By extending Function using the class syntax you create a class that, when instantiated, is now a function, which you can then additionally instantiate.

While not exhaustively tested, I believe the last statement can be analyzed thus:

```js
new new Foo(":D")().val(new newFooInstance()).val;
veryNewFooInstance.val;
// -> ':D'
```

As a tiny addendum, doing `new Function('return "bar";')` of course creates a function with the body `return "bar";`. Since `super()` in the constructor of our `Foo` class is calling `Function`'s constructor, it should come as no surprise now to see that we can additionally manipulate things in there.

```js
class Foo extends Function {
  constructor(val) {
    super(`
      this.val = arguments[0];
    `);
    this.prototype.val = val;
  }
}

var foo = new new Foo(":D")("D:");
foo.val; // -> 'D:'
delete foo.val; // remove the instance prop 'val', deferring back to the prototype's 'val'.
foo.val; // -> ':D'
```

- [Class Extends Function: Extra Newness](https://github.com/denysdovhan/wtfjs/issues/78)

## Why you should use semicolons

Writing some standard JavaScript… and then BOOM!

```js
class SomeClass {
  ["array"] = []
  ["string"] = "str"
}

new SomeClass().array; // -> 'str'
```

What the …?

### 💡 Explanation:

Once again, this is all thanks to the Automatic Semicolon Insertion.

An example above is basically the same as:

```js
class SomeClass {
  ["array"] = ([]["string"] = "str");
}
```

You basically assign a string `str` into an `array` property.

- [An original tweet with an example](https://twitter.com/SeaRyanC/status/1148726605222535168) by Ryan Cavanaugh
- [TC39 meeting when they debated about it](https://github.com/tc39/notes/blob/master/meetings/2017-09/sept-26.md)

## Split a string by a space

Have you ever tried to split a string by a space?

```js
"".split(""); // -> []
// but…
"".split(" "); // -> [""]
```

### 💡 Explanation:

This is expected behaviour. It's responsibility is to divide the input string every time a separator occurs in that input string. When you pass in an empty string it'll never find a separator and thus return that string.

Let's quote the specification:

> The substrings are determined by searching from left to right for occurrences of `separator`; these occurrences are not part of any String in the returned array, but serve to divide up the String value.

- [**22.1.3.21** String.prototype.split](https://tc39.es/ecma262/#sec-string.prototype.split)
- [An original tween with an example](https://twitter.com/SeaRyanC/status/1331656278104440833) by Ryan Cavanaugh
- [A tween with an explanation](https://twitter.com/kl13nt/status/1331742810932916227?s=20) by Nabil Tharwat

## A stringified string

This caused a bug that I've been solving for a few days:

```js
JSON.stringify("production") === "production"; // -> false
```

### 💡 Explanation:

Let's see what `JSON.stringify` is returning:

```js
JSON.stringify("production"); // -> '"production"'
```

It is actually a stringified string, so it's true:

```js
'"production"' === "production"; // -> false
```

- [ECMA-404 The JSON Data Interchange Standard.](https://www.json.org/json-en.html)

## Non-strict comparison of a number to `true`

```js
1 == true; // -> true
// but…
Boolean(1.1); // -> true
1.1 == true; // -> false
```

### 💡 Explanation:

According to the specification:

> The comparison x == y, where x and y are values, produces true or false. Such a comparison is performed as follows:
>
> 4. If `Type(x)` is Number and `Type(y)` is String, return the result of the comparison `x == ! ToNumber(y)`.

So this comparison is performed like this:

```js
1 == true;
1 == Number(true);
1 == 1; // -> true
// but…
1.1 == true;
1.1 == Number(true);
1.1 == 1; // -> false
```

- [**7.2.15** Abstract Equality Comparison](https://262.ecma-international.org/11.0/index.html#sec-abstract-equality-comparison)

# 📚 Other resources

- [wtfjs.com](http://wtfjs.com/) — a collection of those very special irregularities, inconsistencies and just plain painfully unintuitive moments for the language of the web.
- [Wat](https://www.destroyallsoftware.com/talks/wat) — A lightning talk by Gary Bernhardt from CodeMash 2012
- [What the... JavaScript?](https://www.youtube.com/watch?v=2pL28CcEijU) — Kyle Simpsons talk for Forward 2 attempts to “pull out the crazy” from JavaScript. He wants to help you produce cleaner, more elegant, more readable code, then inspire people to contribute to the open source community.
- [Zeros in JavaScript](http://zero.milosz.ca/) — a comparison table of `==`, `===`, `+` and `*` in JavaScript.

# 🤝 支援

Hi! I work on this project in my spare time, in addition to my primary job. I hope you enjoy reading it. If you do, please, consider supporting me 🙏.

Every single donation is important. Your donation is gonna make a clear statement: My work is valued.

**🙏 Thank you for your support! 🙏**

| Service          |                     Link                     |                                                                   Action                                                                   |
| ---------------- | :------------------------------------------: | :----------------------------------------------------------------------------------------------------------------------------------------: |
| **Patreon**      |        [Become a patron][patreon-url]        | <a href="https://patreon.com/denysdovhan"><img src="https://c5.patreon.com/external/logo/become_a_patron_button@2x.png" width="120px"></a> |
| **BuyMeACoffee** |     [Buy me a cup of ☕️ or 🥤][bmc-url]     |    <a href="https://buymeacoffee.com/denysdovhan"><img src="https://cdn.buymeacoffee.com/buttons/default-black.png" width="120px"></a>     |
| **Bitcoin**      |     `1EJsKs6rPsqa7QLoVLpe3wgcdL9Q8WmDxE`     |      <img src="https://user-images.githubusercontent.com/3459374/107130426-0ae4f800-68d6-11eb-9b86-15bf33467615.png" width="120px"/>       |
| **Ethereum**     | `0x6aF39C917359897ae6969Ad682C14110afe1a0a1` |      <img src="https://user-images.githubusercontent.com/3459374/107130370-55b24000-68d5-11eb-93f5-075355c7fcd4.png" width="120px"/>       |

> **⚠️ Note:** I live in Ukraine and services like PayPal and Stripe don't work with Ukrainian bank accounts. This means there's no way for me to set up GitHub Sponsors, OpenCollective, or services relied on them. Sorry, those are the only ways you can support me for now.

# 🎓 License

[![CC 4.0][license-image]][license-url]

&copy; [Denys Dovhan](http://denysdovhan.com)

[license-url]: http://www.wtfpl.net
[license-image]: https://img.shields.io/badge/License-WTFPL%202.0-lightgrey.svg?style=flat-square
[npm-url]: https://npmjs.org/package/wtfjs
[npm-image]: https://img.shields.io/npm/v/wtfjs.svg?style=flat-square
[patreon-url]: https://patreon.com/denysdovhan
[patreon-image]: https://img.shields.io/badge/support-patreon-F96854.svg?style=flat-square
[bmc-url]: https://patreon.com/denysdovhan
[bmc-image]: https://img.shields.io/badge/support-buymeacoffee-222222.svg?style=flat-square
