<template>
  <div id="app">
    <page-header></page-header>
    <button @click="switch_view">Toggle Me</button>

    <div class="tweets_grid" v-if="isGrid">
      <tweet-item
        v-for="tweet in tweets"
        :key="tweet['username']"
        :desc="tweet['desc']"
        :username="tweet['username']"
        :date="tweet['date']"
      >
      </tweet-item>
    </div>
    <div class="tweets_list" v-else>
      <tweet-item
        v-for="tweet in tweets"
        :key="tweet['username']"
        :desc="tweet['desc']"
        :username="tweet['username']"
        :date="tweet['date']"
      >
      </tweet-item>
    </div>
    <user-input
      @post_entered="react_to_post_entered"
      @tweet_added="react_to_tweet_added"
    ></user-input>
    <h1>{{ yelled_post }}</h1>
    <h1>{{ tweeted_post }}</h1>
  </div>
</template>

<script>
import PageHeader from "./components/PageHeader.vue";
import TweetItem from "./components/TweetItem.vue";
import UserInput from "./components/UserInput.vue";

export default {
  name: "App",
  methods: {
    react_to_post_entered(post_content) {
      this.yelled_post = post_content;
    },
    react_to_tweet_added(post_tweet) {
      this.tweets.push({
        desc: post_tweet,
      });
    },
    switch_view() {
      if (this.isGrid === true) {
        this.isGrid = false;
      } else {
        this.isGrid = true;
      }
    },
  },
  components: {
    PageHeader,
    TweetItem,
    UserInput,
  },

  data() {
    return {
      isGrid: true,
      tweeted_post: undefined,
      yelled_post: undefined,
      tweets: [
        {
          desc: "This is the content of tweet 1",
          username: "John",
          date: "03-12-2021",
        },
        {
          desc: "This is the content of tweet 2",
          username: "Nick",
          date: "04-12-2021",
        },
        {
          desc: "This is the content of tweet 3",
          username: "Andrew",
          date: "05-12-2021",
        },
        {
          desc: "This is the content of tweet 4",
          username: "Dave",
          date: "06-12-2021",
        },
      ],
    };
  },
};
</script>

<style>
.tweets_grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  margin-top: 20px;
  column-gap: 70px;
  row-gap: 70px;
  padding: 10px;
}
.tweets_list {
  display: grid;
  margin-top: 20px;
  column-gap: 70px;
  row-gap: 70px;
  padding: 10px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
