# Web + DB Press Vol. 120 最新Vue.js 3 入門 第2章 Vue.jsの基本的な使い方

## 作成するToDoリストアプリケーション

### 開発前の準備

- src/components/ToDoList.vue を作成（中身は空）
- src/App.vue を修正
- src/components/HelloWorld.vue, assets/を削除

`npm run dev` しても表示されない。src/components/ToDoList.vueが空なので表示する対象がない。

## ToDoリストの表示を実装

### 1つのToDoを表示するまでを実装

- src/components/ToDoList.vue を修正

- Q: dataって何？
- A: Webアプリの「状態」
[Vue.js - 状態管理](https://v3.ja.vuejs.org/guide/state-management.html#%E5%85%AC%E5%BC%8F%E3%81%AE-flux-%E3%83%A9%E3%82%A4%E3%82%AF%E3%81%AA%E5%AE%9F%E8%A3%85)

```
ElmのTEAインスパイアの(FaceBook考案の)Fluxライク
```

`data` に定義したプロパティを<template>内で参照できる。
Mustache構文（二重の波括弧）を記述するとJavaScript式を記述できる。


#### v-bindディレクティブ

`v-bind:title="todo"` によって、li要素のtitle属性にtodoをバインドしている。


### 複数のToDoを表示するまでを実装

v-forディレクティブにより、複数の要素を反復して表示できる。

v-forディレクティブ
https://v3.ja.vuejs.org/guide/list.html

> 配列に基づいて、アイテムのリストを描画するために、v-for ディレクティブを使用することができます。
> v-for ディレクティブには、 item in items の形式の特別な構文が必要で、 items はソースデータの配列、 item は繰り返される配列要素のエイリアスです。

key属性
https://v3.ja.vuejs.org/guide/migration/key-attribute.html

> 特別な属性である key はノードの ID を追跡するために Vue の仮想 DOM のアルゴリズムのヒントとして使用されます。

keyは仮想DOMのノードを一意で見つけるやつと認識（多分 DOMツリー内でグローバル）

## 入力フォームと追加ボタンを実装

### 入力フォームを実装

`v-model="プロパティ名"` と入力することにより、inputタグの入力内容をプロパティに反映できる。

https://v3.ja.vuejs.org/guide/migration/v-model.html

> Vue 3 では、双方向データバインディングの API が標準化され、混乱を減らし、開発者が v-model ディレクティブをより柔軟に使えるようになりました。

data（状態）が変わるとリアクティブシステムが反応（再描画）みたいな認識

Vue 2ではどうだったんだろう？？？

### ボタンを実装

`v-on:click="handleClick"` のように記述するとclickイベントが発火した時、methodsオプション内のhandleClickメソッドを呼び出す。

この場合のthisは何を指すの？という話になった。