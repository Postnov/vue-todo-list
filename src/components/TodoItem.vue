<template>
    <span
        class="todo-item"
        :class="{'done': item.done, 'important': item.important}">
        <span
            @click="$emit('onDone', item.id)"
            class="todo-item-label">{{ item.label }}</span>
        <button
            @click="$emit('onImportant', item.id)"
            type="button" class="btn btn-outline-success btn-sm float-right">
            <i class="fa fa-exclamation"></i>
        </button>
        <button
            @click="$emit('onDelete', item.id)"
            type="button" class="btn btn-outline-danger btn-sm float-right">
            <i class="fa fa-trash-o"></i>
        </button>
    </span>
</template>


<script>
export default {
    name: 'TodoItem',
    props: ['item']
}
</script>


<style>
.todo-item {
    font-size: 1.25rem
}

.todo-item button {
    width: 35px;
    margin: 3px
}

.todo-item-label {
    margin-left: 1.25rem;
    line-height: 35px;
    cursor: pointer;
    -webkit-user-select: none;
    -moz-user-select: none;
    -ms-user-select: none;
    user-select: none
}

.todo-item.done .todo-item-label {
    text-decoration: line-through
}

.todo-item.important .todo-item-label {
    font-weight: 700;
    color: #4682b4
}
</style>
