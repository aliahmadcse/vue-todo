<template>
    <div id="app">
        <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
        <todo-list></todo-list>
    </div>
</template>

<script>
import TodoList from './components/TodoList';

export default {
    name: 'App',
    components: {
        TodoList
    }
};
</script>

<style>
/* */
</style>
