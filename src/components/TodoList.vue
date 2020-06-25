<template>
    <div class="container">
        <div class="row">
            <div class="col-12">
                <p class="display-3">Vue crash course</p>
            </div>
        </div>
        <div class="row">
            <div class="col-12 col-lg-6">
                <new-todo @on-addtodo="addTodo($event)"></new-todo>
            </div>
        </div>
        <div class="row">
            <div class="col-12 col-lg-6">
                <ul class="list-group">
                    <Todo
                        v-for="(todo,index) in todos"
                        :key="index"
                        :todoString="todo.todoString"
                        :completed="todo.completed"
                        @on-delete="deleteTodo(todo)"
                        @on-toggle="toggleTodo(todo)"
                        @on-edit="editTodo(todo,$event)"
                    />
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
import Todo from './Todo';
import NewTodo from './NewTodo';

export default {
    components: {
        Todo,
        NewTodo
    },

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