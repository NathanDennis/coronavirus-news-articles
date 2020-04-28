# Coronavirus News

### ~~Broken - NewsAPI.org no longer sends image URLs back in their JSON responses for free tier users. I'm trying to find a way to get article thumbnails back through other means. For now, the alt text will simply be displayed at the top of each article tile.~~

### Update - After reversing a decision to stop free tier users receiving ImageURLs from the API, all articles that should have a thumbnail image, now have those thumbnail images back. Hoping this doesn't happen again

## The most popular articles mentioning coronavirus of the day
Data updates on the hour

![Screenshot of app showing USA articles](https://i.imgur.com/jNRmQ8Tl.png)
![Screenshot of app showing UK articles](https://i.imgur.com/pbx3gMNl.png)
### First time using VueJS, I'm sure there's a lot that could be optimized/changed

[Currently hosted on Netlify](https://coronavirusupdates.netlify.com/)

API data provided by [newsapi.org](https://newsapi.org/)

Custom ExpressJS server with node-cron scheduler fetches API data hourly to minimise calls, data is then stored in a global variable for the site to make a GET request to, to populate the cards on the landing page
