<template>
    <div class="ui card article content">
        <a class="image card-image" :href="url" target="_blank" rel="noopener noreferrer">
            <img :src="urlToImage" alt="news article thumbnail">
        </a>
        
        <p >
            <a :href="url" target="blank" class="header">{{title}}</a>
        </p>
        <div class="meta">
            <span class="date">{{publishedAt}}</span>
        </div>
        <div class="description">
            {{description}}
        </div>
    </div>
</template>

<!-- sourceName = article.source.name  -->

<script>
export default {
    name: 'NewsArticleCard',
    props: ['title', 'description', 'url', 'urlToImage', 'publishedAt', 'sourceName']
}
</script>

<style>
.card-image {
    margin-bottom: 1rem;
}

.article .description, .header{
    font-size: 1.25rem;
}
</style>