<template>
  <div id="app">
    <ContentHeader/>
    <ArticleGrid />
  </div>
</template>

<script>

import ArticleGrid from './components/ArticleGrid'
import ContentHeader from './components/ContentHeader'
export default {
  name: 'App',
  components: {
    ContentHeader,
    ArticleGrid
  }
}
</script>