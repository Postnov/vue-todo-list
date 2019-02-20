<template>
    <ul class="list-group todo-list">
        <li class="list-group-item" v-for="item in items" :key="item.id">
            <TodoItem
            :item="item"
            @onDone="onDone"
            @onImportant="onImportant"/>
        </li>
    </ul>
</template>

<script>
import TodoItem from './TodoItem.vue'
export default {
    name: 'TodoList',
    props: ['items'],
    methods: {
        onDone(id) {
            this.$emit('onDone', id);
        },
        onImportant(id) {
            this.$emit('onImportant', id);
        }
    },
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
