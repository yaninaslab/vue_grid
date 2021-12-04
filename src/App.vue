<template>
  <div id="app">
    <page-header></page-header>
    <tweet-item v-for="tweet in tweets" :key="tweet['username']"
    :desc="tweet['desc']"
    :username="tweet['username']"
    :date="tweet['date']">

    </tweet-item>
  
  </div>
</template>

<script>
import PageHeader from './components/PageHeader.vue'
import TweetItem from './components/TweetItem.vue'

export default {
  name: 'App',
  components: {
    PageHeader,
    TweetItem
  },

  data() {
  return {
    tweets: [
      {
        desc: "This is the content of tweet 1",
        username: "John",
        date: "03-12-2021"
        
      },
      {
        desc: "This is the content of tweet 2",
        username: "Nick",
        date: "04-12-2021"
      },
      {
        desc: "This is the content of tweet 3",
        username: "Andrew",
        date: "05-12-2021"
      },
      {
        desc: "This is the content of tweet 4",
        username: "Dave",
        date: "06-12-2021"
      }
    ]
  }
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
</style>
