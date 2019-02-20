<template>
    <ul class="list-group todo-list">
        <li class="list-group-item">
            <TodoItem />
        </li>
    </ul>
</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
    name: 'TodoList',
    components: {
        TodoItem
    }
}
</script>


<style>
.todo-list .list-group-item {
    padding: .45rem .75rem
}
</style>
