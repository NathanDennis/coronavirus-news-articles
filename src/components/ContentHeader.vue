<template>
    <div class="ui container">
        <img id="virus-icon" src="virusicon.png" alt="virus icon">
        <div class="content">
          <h1>COVID-19 Updates</h1>
        </div>
        <div class="sub header subtext">
          <p>The most popular COVID-19 related articles of today</p>
          <p>Checking for new articles every hour</p>
        </div>

      <br>

      <div class="ui container info-links-container">
        <a
          class="info-link"
          target="blank"
          href="https://coronavirus.jhu.edu/map.html">
          John Hopkins University Cronavirus Dashboard
        </a>
        <br>
        <br>
        <a
          class="info-link"
          target="blank"
          href="https://www.who.int/emergencies/diseases/novel-coronavirus-2019/advice-for-public">
          World Health Organisation advice for the public
        </a>
      </div>
      
    </div>
</template>

<script>
export default {
    name: 'ContentHeader'
}
</script>

<style>
  .container {
    margin-bottom: 1.5rem;
  }
</style>
