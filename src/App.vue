<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <div class="buttons">
      <button class="ui inverted primary button" v-on:click="articlesToRender='UK', currentlyRendered='Articles from Great Britain'">UK Articles</button>
      <button class="ui inverted button" v-on:click="articlesToRender='USA', currentlyRendered='Articles from The United States'">USA Articles</button>
      <h1 class="currently-rendered">{{ currentlyRendered }}</h1>
    </div>

    <div class="ui grid article-wrapper loading-header" v-if="UnitedStatesArticles.length === 0">
      <h2>Loading articles...</h2>
    </div>

    <!-- USA ARTICLES -->
    <div class="ui grid article-wrapper" v-if="articlesToRender==='USA'">
          <NewsArticleCard v-for="article in UnitedStatesArticles" :key="article.id"
          :title="article.title" 
          :description="article.description"
          :urlToImage="article.urlToImage"
          :url="article.url"
        />
    </div>

    <!-- UK ARTICLES -->
    <div class="ui grid article-wrapper" v-else>
          <NewsArticleCard v-for="article in UKArticles" :key="article.id"
          :title="article.title" 
          :description="article.description"
          :urlToImage="article.urlToImage"
          :url="article.url"
        />
    </div>
  </div>
</template>

<script>
import axios from 'axios'

// Component imports
import NewsArticleCard from './components/NewsArticleCard' 
export default {
  name: 'App',
  components: {
    NewsArticleCard
  },
  data() {
    return {
      UnitedStatesArticles: [],
      UKArticles: [],
      articlesToRender: 'USA',
      currentlyRendered: 'Articles from The United States'
    }
  },
  mounted() {
    axios.get('https://nd-coronavirus-article-data.herokuapp.com/')
    // axios.get('http://localhost:3000')
      .then((response) => {
        this.UnitedStatesArticles = response.data.UnitedStatesArticleData
        this.UKArticles = response.data.UKArticleData
        console.log('build success')
    })
  }
}

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.currently-rendered {
  color: white;
  text-decoration: underline;
}

.buttons {
  margin-bottom: 2rem;
}

li {
  list-style: none;
}
</style>
