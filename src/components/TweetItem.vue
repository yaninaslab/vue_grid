<template>
    <div class="tweets">
        <div class="tweet_card">
        <p>{{ desc }}</p>
        <h3>{{ username }}</h3>
        <h5>{{ date }}</h5>

</div>
    </div>
</template>

<script>
    export default {
        name: "tweet-item",
        mounted() {
            document.body.style.background = "lightblue";
        },

    props: {
        desc: String,
        username: String,
        date: String
    }
    }
</script>

<style scoped>
.tweets {
    display: grid;
    grid-auto-flow: column;
    margin-top: 20px;
}
.tweet_card {
    max-width: 250px;
    border-radius: 15px;
    box-shadow: 3px 3px 6px gray;
    padding: 10px;
}
p {
    font-weight: bold;
    font-size: 1.2rem;
}
h3 {
    color: blue;
}
</style>