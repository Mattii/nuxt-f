<template>
    <div class="wrapper">
        <article>
            <h1 class="title">
                {{ post.title}}
            </h1>
            <p>{{ post.content }}</p>
        </article>
        <aside>
            <h3>Post You my enjoy</h3>
            <ul>
                <li v-for="related in relatedPosts" :key="related.id" class="appear">
                    <nuxt-link :to="{name: 'posts-id', params: {id: related.id}}">
                       {{ related.title }}
                    </nuxt-link>
                </li>
            </ul>
        </aside>
    </div>
</template>

<script>
export default {
    head() {
        return {
            title: this.post.title,
            description: 'Weather forecast information',
            meta: [
                {name: 'twitter:title', content: this.post.title},
                {name: 'twitter:description', content: this.post.content},
                {name: 'twitter:image', content: ''},
                {name: 'twitter:card', content: 'summary_large_image'},
            ]
        }
     },
    data(){
        return {
            id: this.$route.params.id
        }
    },
    computed: {
        post() {
            return this.$store.state.posts.all.find(post => post.id === this.id);
        },
        relatedPosts() {
            return this.$store.state.posts.all.filter(post => post.id !== this.id);
        }
    }
}
</script>

<style scoped>
    .wrapper{
        display: flex;
        justify-content: space-between;
        line-height: 2;
        max-width: 800px;
        margin: auto;
    }
    article * {
        margin-bottom: 1rem;
    }
    aside{
        min-width: 280px;
        max-width: 280px;
        padding-left: 2rem;
    }
    .title {
        font-size: 2rem;
    }
    .appear{
        animation: 1s appear;
    }
    @keyframes appear {
        0% {
            opacity: 0;
        }
    }
</style>