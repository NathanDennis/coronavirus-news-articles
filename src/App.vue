<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
    <div class="ui grid article-wrapper">
        <NewsArticleCard v-for="article in articles" :key="article.id"
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
      articles: []
    }
  },
  mounted() {
    axios.get('https://nd-coronavirus-article-data.herokuapp.com/')
      .then((response) => {
        this.articles = response.data
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

li {
  list-style: none;
}
</style>
