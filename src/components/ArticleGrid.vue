<template>
<div>
    <!-- <ArticleGridHeader /> -->
    <div class="ui container">
      <button class="ui inverted primary button" v-on:click="articlesToRender='UK', currentlyRendered='Articles from Great Britain'">UK Articles</button>
      <button class="ui inverted button" v-on:click="articlesToRender='USA', currentlyRendered='Articles from The United States'">USA Articles</button>
      <h2 class="currently-rendered" v-if="UnitedStatesArticles.length === 0">Loading articles...</h2>
      <h2 class="currently-rendered" v-else>{{ currentlyRendered }}</h2>
      <hr />
    </div>    

    <div class="ui grid article-wrapper" v-if="articlesToRender==='USA'">
      <NewsArticleCard
        v-for="article in UnitedStatesArticles"
        :key="article.id"
        :title="article.title"
        :description="article.description"
        :urlToImage="article.urlToImage"
        :url="article.url"
      />
    </div>

    <div class="ui grid article-wrapper" v-else>
      <NewsArticleCard
        v-for="article in UKArticles"
        :key="article.id"
        :title="article.title"
        :description="article.description"
        :urlToImage="article.urlToImage"
        :url="article.url"
      />
    </div>
  </div>
</template>

<script>
import axios from "axios";
import NewsArticleCard from "./NewsArticleCard";

// import ArticleGridHeader from "./ArticleGridHeader";
export default {
  name: "ArticleGrid",
  components: {
    NewsArticleCard,
    // ArticleGridHeader
  },
  data() {
    return {
      UnitedStatesArticles: [],
      UKArticles: [],
      currentlyRendered: 'Articles from The United States',
      articlesToRender: 'USA'
    };
  },
  mounted() {
    axios
      .get('https://coronavirusupdates.netlify.app/api/')
      .then(response => {
        this.UnitedStatesArticles = response.data.UnitedStatesArticleData
        this.UKArticles = response.data.UKArticleData
      })
      .catch(error => {
        console.log(error)
      });
  }
}
</script>
