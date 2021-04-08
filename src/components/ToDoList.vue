<template>
  <input v-model="inputValue" />
  <button v-on:click="handleClick">ToDoを確認</button>
  <ul>
    <li v-for="todo in todoItems" v-bind:key="todo.id">
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
        text: this.inputValue,
      });
      this.inputValue = ''
    },
  },
};
</script>