<template>
    <div class="todo-app">

    </div>
</template>

<script>
import AddTodo from './AddTodo.vue';
import AppHeader from './AppHeader.vue';
import FilterButtons from './FilterButtons.vue';
import SearchPanel from './SearchPanel.vue';
import TodoList from './TodoList.vue';

export default {
    name: 'App',
    components: {
        AddTodo,
        AppHeader,
        FilterButtons,
        SearchPanel,
        TodoList
    }
}
</script>

<style>
.todo-app {
    margin: 2rem auto 0;
    max-width: 400px
}

.top-panel {
    margin: 1rem 0
}
</style>

