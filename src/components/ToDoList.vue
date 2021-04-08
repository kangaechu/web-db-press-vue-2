<template>
  <input v-model="inputValue" />
  <button v-on:click="handleClick">ToDoを確認</button>
  <input v-model="filterValue" placeholder="フィルタテキスト" />
  <ul>
    <li
      v-for="todo in filteredTodoItems"
      v-bind:key="todo.id"
      class="todo-item"
      v-bind:class="{ done: todo.done }"
      v-on:click="todo.done = !todo.done"
    >
      <span v-if="todo.done">✔️</span>
      {{ todo.text }}
    </li>
  </ul>
</template>
<script>
export default {
  data() {
    const todoItems =  [
        { id: 1, done: false, text: "Go out to sea" },
        { id: 2, done: false, text: "Invite the first member" },
      ],

    return {
      inputValue: "",
      todoItems,
      // filteredTodoItemsの初期値は、
      // todoItemsと同じ配列を使用する
      filteredTodoItems: todoItems,
      filterValue: "",
    };
  },
  watch: {
      // filterValueの値の変更を監視し
      // filteredTodoItemsを再計算する
      filterValue() {
        this.updateFilteredTodoItems()
      },
      // todoItemsの値の変更を監視し、
      // filteredTodoItemsを再計算する
      todoItems: {
        handler() {
          this.updateFilteredTodoItems()
        },
        // 深く監視することで配列要素の変更も監視する
        deep: true
      },
  },
  methods: {
    handleClick() {
      // 入力をリストに追加
      this.todoItems.push({
        id: this.todoItems.length + 1,
        done: false,
        text: this.inputValue,
      });
      this.inputValue = ""
    },
    // filteredTodoItemsに
    // 再計算した配列を与える
    updateFilteredTodoItems() {
      this.filteredTodoItems =
        this.filterValue
          ? this.todoItems.filter((todo) => 
            todo.text.includes(this.this.filterValue)
          )
          : this.todoItems
    }
  },
};
</script>
<style>
.todo-item.done {
  /* 背景を緑色にする */
  background-color: #3fb983;
  color: #ffffff;
}
</style>