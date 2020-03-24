<template>
    <div class="ui container">
        <button class="ui inverted primary button" v-on:click="articlesToRender='UK', currentlyRendered='Articles from Great Britain'">UK Articles</button>
        <button class="ui inverted button" v-on:click="articlesToRender='USA', currentlyRendered='Articles from The United States'">USA Articles</button>
        <h2 class="currently-rendered">{{ currentlyRendered }}</h2>
        <hr />
    </div>
</template>

<script>
export default {
    name: 'ArticleGridHeader',
    data() {
        return {
            articlesToRender: 'USA',
            currentlyRendered: 'Articles from The United States'
        }
    }
}
</script>

<style>
    h2 {
        text-decoration: none !important;
    }
</style>