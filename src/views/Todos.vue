<template>
<div>
    <h2>This is our todos</h2>
    <input type="text" v-model="todo.text">
    <button type="button" v-on:click="createTodo">Create Todo</button>
    <ul>
        <li v-for="todo in todos" v-on:click="completeTodo(todo)">
            <span v-bind:class="{completed: todo.isCompleted}">{{ todo.text }}</span>
            <button v-on:click="deleteTodo">delete</button>
        </li>
    </ul>
</div>
</template>

<script>
export default {
    name: 'todos',
    data: function () {
        return {
            todo: this.newTodo(),
            todos: []
        };
    },
    methods: {
        createTodo: function() {
            this.todos.push(this.todo);
            this.todo = this.newTodo();
        },
        deleteTodo: function() {

        },
        completeTodo: function(todo) {
            todo.isCompleted = !todo.isCompleted;
        },
        newTodo: function() {
            return {
                text: '',
                isCompleted: false
            };
        }
    }
}
</script>

<style lang="css">
ul {
    list-style: none;
}

.completed {
    text-decoration: line-through;
}
</style>