## if文

**_if文_**はプログラミングでもっとも頻繁に使われる制御文です。**_if文_**は条件式が偽となる場合はブロック内の処理をスキップし、真となる場合のみブロック内の処理を実行します。**_if文_**の制御フローは以下の図のようなイメージになります。

![Flowchart if](./images/flow-if.png)

## if文の構文

**_if文_**の基本構文は次のようになります。

```js
if (条件式) {
  文；
  文;
  文;
}
```
サンプルコードを見てみましょう。

```js
let a = 3;

if (a > 0) {
  //trueの時に実行
  console.log(a); // 3
}
```

**_if文_**を実行すると「(条件式)」の中に書かれた式が評価され、判定結果が`true`の場合に
その後ろに続くブロック「{}」の中に記述された命令文が実行されます。ブロックの末尾にセミコロンは必要ありません。制御文でブロック内の処理式を書く際は見通しをよくするために**インデント**を入れておくと良いでしょう。

ブロックは通常必要ですが、実行したい文が一つだけの場合は次のようにブロック無しで記述することもできます。

```
if(条件式) 文;
```

- サンプルコード

```js
if (true) console.log("true"); // true
```

if文ブロックの中にさらに**_if文_**を記述入れ子(**ネスト**)にすることもできます。これにより、さらに細かい条件分岐ができるようになります。
```js
let obj = {
  num: 1,
  name: 'ocean',
}

if (obj.num <= 10) {
  if (obj.name === 'ocean') {
    console.log('値は10以下で、名前は"ocean"です。'); // ここが出力される
  }
}
```

<iframe width="100%" height="300" src="//jsfiddle.net/codegrit_hiro/7uerqf30/2/embedded/js,html,css,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>

## else文

**_if文_**は条件式が真となる場合にのみ処理を実行する制御文でした。`else if`および`else`を使うことで条件式を評価した結果が偽(`false`)となる場合に、さらなる条件分岐ができるようになります。

![Flowchart else](./images/flow-elseif.png)

`else if`を使った基本構文は次のようになります。

```js
//else if文の構文

if (条件式1) {
  //条件式1がtrue時に実行
  文；
  文;
}
else if (条件式2) {	//条件1でfalseの時に条件式2を評価
  //条件式2がtrue時に実行
  文；
  文;
}
```
**_if文_**の条件式が`false`であると判断されるとその直後の`else if`にある条件式を評価しに行きます。これが`true`であればその直後のブロック内の処理を実行します。
**_else if文_**の中で、`else if(条件式)`を使う回数に決まりはないので下記のように記述することは問題ありません。
```js
if (条件式1) {
  文;
} else if (条件式2) {
  文;
} else if (条件式3) {
  文;
} else if (条件式4) {
  文;
}
```


ただし**_else if文_**は必ず先頭に**_if文_**を伴います。**_else if文_**を単体で使用することはできません。**_if文_**および**_else if文_**による条件分岐の結果のどれにも`true`にならない場合の処理を記述したい場合は、制御文の最後に`else{処理文}`を追加することで可能になります。この時、`if`、`else if`、`else`のいずれかのブロックの処理が必ず実行されることになります。
```js
if (条件式1) {
  文;
} else if (条件式2) {
  文;
} else {
  文; // 全ての条件に当てはまらない場合に実行
}
```

- サンプルコード

```js
//街の規模を調べる条件分岐
let population = 1198000;

if (population < 100000) {
  console.log("Small City");
} else if (population < 500000) {
  console.log("Medium City");
} else if (population < 1200000) {
  console.log("Big City");
} else {
  console.log("Gigantic City");
}
```

出力結果:
```
"Big City"
```

<iframe width="100%" height="300" src="//jsfiddle.net/codegrit_hiro/qe7fau9h/2/embedded/js,html,css,result/dark/" allowfullscreen="allowfullscreen" allowpaymentrequest frameborder="0"></iframe>