<template>
    <div>
<textarea name="" ref="user_post_input" cols="30" rows="10"></textarea><br>
<button @click="push_button">Yell Post</button><br>
<button @click="add_tweet">Add Tweet</button>
    </div>
</template>

<script>
    export default {
        name: "user-input",

        methods: {
        push_button() {
            var input_value = this.$refs['user_post_input'].value;
            this.$emit('post_entered', input_value);
        },
        add_tweet() {
            var input_value = this.$refs['user_post_input'].value;
            this.$$emit('tweet_added', input_value);
        }

    
    }
    }
   

</script>

<style scoped>
textarea {
    margin: 20px;
}
button {
    margin: 10px;
}
</style>