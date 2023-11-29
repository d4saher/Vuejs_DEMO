<script>
    import tweets from '@/assets/tweets.json';
    import TweetOptions from './TweetOptions.vue';
    import TweetComposition from './TweetComposition.vue';

    export default {
    components: { TweetOptions},
    data() {
        return {
            // Usar los tweets importados
            tweetsList: tweets,
            showChild: true
        };
    },
    methods: {
        removeTweet(key) {
            this.tweetsList = this.tweetsList.filter(tweet => tweet.id !== key);
        }
    },
    components: { TweetOptions, TweetComposition }
}
</script>

<template>
    <div class="APIS">
        <div class="twOptions">
            <h1>Options API</h1>
            <TweetOptions
                v-for="tweet in tweetsList"
                :key="'opt' + tweet.id"
                :tweetId="tweet.id"
                :username="tweet.username"
                :content="tweet.content"
                :publishedAt="tweet.publishedAt"
                @remove="removeTweet"
            />
        </div>

    </div>
</template>

<style scoped>
    .APIS {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    .twOptions, .twComposition {
        flex: 1; /* Cada contenedor tomará la mitad del espacio disponible */
        max-width: 500px; /* O un máximo de 500px, ajusta según sea necesario */
        margin-right: 20px;
    }

    .twComposition {
        border-left: 1px solid #41D688;
        padding-left: 20px;
     }

</style>