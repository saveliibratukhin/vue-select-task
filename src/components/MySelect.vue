<template>
    <select
        @change="changeOption"
    >
        <option></option>
        <option 
            v-for="option in options"
            v-bind:key="option"
        >
            {{option}}
        </option>
    </select>
</template>

<script>
export default {
    props: {
        options: {
            type: Set,
            default: () => {}
        }
    },
    methods: {
        changeOption(event) {
            this.$emit('selected', event.target.value)
        }
    }
}
</script>

<style>
select {
    padding: 5px;
    min-width: 100px;
    margin: 5px
}

@media screen and (max-width: 768px) {
    select {
        min-width: 80%;
    }
}
</style>