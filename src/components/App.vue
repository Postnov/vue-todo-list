<template>
    <div class="todo-app">
        <AppHeader />
        <div class="top-panel d-flex">
            <SearchPanel />
            <FilterButtons />
        </div>
        <TodoList :items="items" />
        <AddTodo />
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
    data() {
        return {
            maxId: 10,
            items: [
                {label: 'Make cofee', done: false, important: false, id: 1},
                {label: 'Learn Vue', done: false, important: false, id: 2},
                {label: 'Make awesome app', done: false, important: false, id: 3}
            ]
        }
    },
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

