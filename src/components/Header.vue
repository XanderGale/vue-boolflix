<template>
    <header>
        <h1>Boolflix</h1>
        <div class="searchbox">
            <input class="search" type="text" v-model="userInput" v-on:keyup.enter="$emit('searchInput', userInput)">
            <button @click="$emit('searchInput', userInput)">
                <i class="fas fa-search"></i>
            </button>
        </div>
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
        .searchbox{
            margin-left: auto;
            position: relative;
            .search{
                margin-left: auto;
                border-radius: 7px;
                border-style: none;
                padding: 5px;
                height: 20px;
                &:focus-visible{
                    outline: none;
                }
            }
            button {
                position: absolute;
                right: 3px;
                top: 3px;
                display: inline-block;
                border: none;
                margin: 0;
                text-decoration: none;
                background: transparent;
                color: black;
                cursor: pointer;
                text-align: center;
                -webkit-appearance: none;
                -moz-appearance: none;
            }
            button:active {
                transform: scale(0.99);
            }
        }
        h1{
            color: red;
            text-transform: uppercase;
        }
    }
</style>