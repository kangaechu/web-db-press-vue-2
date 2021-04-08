<template>
  <!-- ToDoListを使用する -->
  <ToDoList />
</template>
<script>
// ToDoList.vueをインポート
import ToDoList from './components/ToDoList.vue'
export default {
  name: 'App',
  components: {
    // ToDoListを<template>で使用できるようにする
    ToDoList
  }
}
</script>
