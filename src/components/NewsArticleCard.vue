<template>
  <div class="ui card article content">
    <a
      class="image card-image"
      :href="url"
      target="_blank"
      rel="noopener noreferrer"
    >
      <img :src="urlToImage" alt="news article thumbnail" />
    </a>

    <div class="content-text">
      <p>
        <a :href="url" target="blank" class="header">{{ title }}</a>
      </p>
      <div class="description">
        {{ description }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NewsArticleCard',
  props: [
    'title',
    'description',
    'url',
    'urlToImage',
    'publishedAt',
    'sourceName',
  ],
};
</script>

<style>
.card-image {
  margin-bottom: 1rem;
}

.card-image img {
  object-fit: cover;
  height: 12rem !important;
}

.article .description,
.header {
  font-size: 1.25rem;
}

.content-text {
  margin: 0 0.5rem 1rem 0.5rem;
}
</style>
