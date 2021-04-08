<template>
    <ul>
        <li v-bind:title="todo">
            {{ todo.slice(0, 10) + '...' }}
        </li>
    </ul>
</template>
<script>
export default {
    data(){
        return { todo: 'go out to sea'}
    }
}
</script>