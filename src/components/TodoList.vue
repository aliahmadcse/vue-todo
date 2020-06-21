<template>
    <div>
        <h1>Hello from todo list template</h1>
    </div>
</template>

<script>
export default {
    data() {
        return {
            todos: [
                {
                    todoString: 'Write code',
                    completed: true
                },
                {
                    todoString: 'Make wordpress app',
                    completed: false
                },
                {
                    todoString: 'Drink water',
                    completed: true
                },
                {
                    todoString: 'Work on blog',
                    completed: false
                }
            ]
        };
    },
    methods: {
        addTodo(newTodo) {
            this.todos.push({
                todoString: newTodo,
                completed: false
            });
        },
        toggleTodo(todo) {
            todo.completed = !todo.completed;
        },
        editTodo(todo, newTodoString) {
            todo.todoString = newTodoString;
        },
        deleteTodo(deleteTodo) {
            this.todos = this.todos.filter(todo => todo !== deleteTodo);
        }
    }
};
</script>

<style scoped>
</style>