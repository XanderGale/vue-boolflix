<template>
    <header>
        <h1>Boolflix</h1>
        <input class="search" type="text" v-model="userInput" v-on:keyup.enter="$emit('searchInput', userInput)">
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
    }
}
</script>

<style scoped lang="scss">
    header{
        height: 70px;
        padding: 10px;
        color: white;
        background: rgb(0,0,0);
        background: linear-gradient(180deg, rgba(0,0,0,1) 0%, rgba(61,61,61,1) 90%);

        display: flex;
        flex-flow: row nowrap;
        justify-content: flex-start;
        align-items: center;
        .search{
            margin-left: auto;
        }
        h1{
            color: red;
            text-transform: uppercase;
        }
    }
</style>