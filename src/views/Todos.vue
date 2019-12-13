<template>
<div>
    <h2>This is our todos</h2>
    <input type="text" v-model="todo">
    <button type="button" v-on:click="createTodo">Create Todo</button>
    <ul>
        <li v-for="todo in todos">
            {{ todo }}
        </li>
    </ul>
</div>
</template>

<script>
export default {
    name: 'todos',
    data: function () {
        return {
            todo: '',
            todos: []
        };
    },
    methods: {
        createTodo: function() {
            this.todos.push(this.todo);
            this.todo = '';
        }
    }
}
</script>

<style lang="css">
    
</style>