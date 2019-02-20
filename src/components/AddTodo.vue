<template>
    <form class="add-todo d-flex" @submit.prevent="addItem">
        <input type="text" class="form-control" placeholder="Enter you task in here" v-model="label">
        <button class="btn btn-outline-secondary">Add item</button>
    </form>
</template>

<script>
    export default {
        name: 'AddTodo',
        data() {
            return {
                label: ''
            }
        },
        methods: {
            addItem() {
                this.$emit('addItem', this.label);
                this.label = '';
            }
        }
    }
</script>

<style>
    .add-todo {
        margin-top: 20px
    }

    .add-todo input {
        margin-right: 3px;
        -webkit-flex: 1 0;
        flex: 1 0
    }
</style>

