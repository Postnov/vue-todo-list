<template>
    <div class="todo-app">
        <AppHeader
            :nameApp="nameApp"
            :done="doneLength"
            :toDo="todoLength"/>
        <div class="top-panel d-flex">
            <SearchPanel
                @search="searchItems"/>
            <FilterButtons
                :filter="filter"
                @filterItem="filterItem"/>
        </div>
        <TodoList
            :items="filterItems"
            @onDone="onDone"
            @onImportant="onImportant"
            @onDelete="onDelete"
        />
        <AddTodo
            @addItem="addItem"/>
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
            nameApp: 'Todo App',
            maxId: 10,
            items: [
                {label: 'Make cofee', done: false, important: false, id: 1},
                {label: 'Learn Vue', done: false, important: false, id: 2},
                {label: 'Make awesome app', done: false, important: false, id: 3}
            ],
            filterItems: [],
            filter: 'all',
        }
    },
    methods: {
        onDone(id) {
            this.items = this.items.map((el) => {
                if (el.id === id) el.done = !el.done;
                return el;
            });

            this.filterItem(this.filter);
        },
        onImportant(id) {
            this.items = this.items.map((el) => {
                if (el.id === id) el.important = !el.important;
                return el;
            });

            this.filterItem(this.filter);
        },
        onDelete(id) {
            this.items = this.items.filter((el) => {
                return el.id !== id;
            });

            this.filterItem(this.filter);
        },
        addItem(label) {
            this.items.push({
                label,
                done: false,
                important: false,
                id: this.maxId++
            });

            this.filterItem(this.filter);
        },

        searchItems(query) {
            this.filterItems = this.items.filter((el) => {
                return el.label.toLowerCase().indexOf(query.toLowerCase()) !== -1;
            })
        },

        filterItem(type) {
            this.filter = type;

            if (type === 'all') {
                this.filterItems = this.items;
            }else if (type === 'active') {
                this.filterItems = this.items.filter((el) => {
                    return el.done === false
                });
            }else if (type === 'done') {
                this.filterItems = this.items.filter((el) => {
                    return el.done === true
                });
            }
        }


    },
    computed: {
        doneLength() {
            return this.items.filter((el) => el.done).length;
        },
        todoLength() {
            let doneLenth = this.items.filter((el) => el.done).length;
            return this.items.length - this.doneLength;
        }
    },
    mounted() {
        this.filterItems = this.items;
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

