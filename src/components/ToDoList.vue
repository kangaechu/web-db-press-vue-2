<template>
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
      todoItems: [
        { id: 1, text: "Go out to sea" },
        { id: 2, text: "Invite the first member" },
      ],
    };
  },
};
</script>