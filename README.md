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
