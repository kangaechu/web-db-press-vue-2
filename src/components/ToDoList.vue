<template>
 <input v-model="inputValue">
 <button v-on:click="handleClick"> 
     ToDoを確認
 </button>
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
      inputValue: '',
      todoItems: [
        { id: 1, text: "Go out to sea" },
        { id: 2, text: "Invite the first member" },
      ],
    };
  },
  methods: {
      handleClick() {
          console.log(this)
          // 入力内容をalertで表示する
          alert(this.inputValue)
      }
  }
};
</script>