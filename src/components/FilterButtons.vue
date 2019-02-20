<template>
    <div class="btn-group">
        <button
            v-for="button in buttons"
            :key="button.label"
            @click="$emit('filterItem', button.type)"
            type="button"
            class="btn"
            :class="[button.type == filter ? 'btn-info' : 'btn-outline-secondary']">
            {{button.label}}</button>
    </div>
</template>

<script>
export default {
    name: 'FilterButtons',
    props: ['filter'],
    data() {
        return {
            buttons: [
                {label: 'All', active: true, type: 'all'},
                {label: 'Active', active: false, type: 'active'},
                {label: 'Done', active: false, type: 'done'},
            ]
        }
    },
}
</script>

