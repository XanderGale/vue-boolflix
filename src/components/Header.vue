<template>
    <header>
        <input type="text" v-model="userInput" v-on:keyup.enter="$emit('searchInput', userInput)">
        <button @click="$emit('searchInput', userInput)">Search</button>
    </header>
</template>

<script>
export default {
    name: 'Header',
    data: function(){
        return {
            userInput: '',
        };
    },
    methods: {
        
    },
}
</script>

<style scoped lang="scss">

</style>