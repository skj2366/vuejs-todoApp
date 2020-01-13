<template>
    <form v-on:enter.prevent="appTodo">
        <input type="text" v-model="inputValue" />
        <button class="btn-reset" v-on:click.prevent="addTodo"></button>
    </form>
</template>

<script>
export default {
    props: ['value'],
    data() {
        return {
            inputValue: this.value
        }
    },
    methods: {
        addTodo() {
            this.$emit('@submit', this.inputValue);
            this.inputValue = '';
        }
    }
}
</script>