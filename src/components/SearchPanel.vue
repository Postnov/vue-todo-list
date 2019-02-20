<template>
    <input
        type="text"
        class="form-control search-panel"
        placeholder="Search"
        v-model="query"
        @keyup="$emit('search', query)">
</template>

<script>
export default {
    name: 'SearchPanel',
    data() {
        return {
            query: ''
        }
    }
}
</script>

<style>
.search-panel {
    width: auto;
    -webkit-flex-grow: 1;
    flex-grow: 1;
    margin-right: 3px
}
</style>


