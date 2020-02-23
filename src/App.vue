<template>
    <div id="app">
        <div class="get" v-for="get in gets" :key="get.id">
            <div>{{gets.result}}</div>

        </div>
    </div>
</template>

<script>


    export default {
        name: "app",
        data() {
            return {
                gets: []
            };
        },

        async mounted() {
            const res = await fetch
            ("https://api.unsplash.com/search/photos?query=london&client_id=7KOSBgto5zitVK6UfxHhkCTSLZ8zdBMrHUZZ-Ofedws");


            const gets = await res.json();
            this.gets = gets;

        }
    };
</script>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin: 50px auto;
        width: 80vw;

    }
</style>
