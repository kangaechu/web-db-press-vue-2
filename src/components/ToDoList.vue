<template>
  <input v-model="inputValue" />
  <button v-on:click="handleClick">ToDoを確認</button>
  <ul>
    <li
      v-for="todo in todoItems"
      v-bind:key="todo.id"
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
    return {
      inputValue: "",
      todoItems: [
        { id: 1, text: "Go out to sea" },
        { id: 2, text: "Invite the first member" },
      ],
    };
  },
  methods: {
    handleClick() {
      // 入力をリストに追加
      this.todoItems.push({
        id: this.todoItems.length + 1,
        done: false,
        text: this.inputValue,
      });
      this.inputValue = "";
    },
  },
};
</script>