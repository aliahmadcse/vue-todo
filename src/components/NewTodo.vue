<template>
    <form @submit.prevent="addTodo()" class="my-3">
        <input v-model="newTodo" placeholder="Enter todo..." type="text" class="form-control" />
    </form>
</template>

<script>
export default {
    data() {
        return {
            newTodo: ''
        };
    },
    methods: {
        addTodo() {
            if (this.newTodo.length > 1) {
                this.$emit('on-addtodo', this.newTodo);
            }
            this.newTodo = '';
        }
    }
};
</script>

<style scoped>
</style>