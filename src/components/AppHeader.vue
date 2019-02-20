<template>
    <div class="app-header d-flex">
        <h1>{{ nameApp }}</h1>
        <h2>{{ toDo }} more to do, {{done}} done</h2>
    </div>
</template>

<script>
export default {
    name: 'AppHeader',
    props: ['nameApp', 'toDo', 'done']
}
</script>


<style>
    .app-header {
        -webkit-align-items: flex-end;
        align-items: flex-end
    }

    .app-header h1 {
        -webkit-flex-grow: 1;
        flex-grow: 1
    }

    .app-header h2 {
        font-size: 1.2rem;
        color: grey
    }
</style>

