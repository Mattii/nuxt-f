<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        nuxt-fundmentals
      </h1>
      <div class="links">
        <nuxt-link class="button--green" 
        v-for="post in posts" 
        :key="post.id"
        :to="{ name: 'posts-id', params: { id: post.id}}"
        >
          {{post.title}}
        </nuxt-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  head() {
    return {
      title: 'Home Page',
        meta: [
          {name: 'twitter:title', content: 'nuxt-fundmentals'},
          {name: 'twitter:description', content: "Nuxt + Vue = love"},
          {hid: 'description', name: 'description', content: 'cosssssssss'},
          {name: 'twitter:image', content: ''},
          {name: 'twitter:card', content: 'summary_large_image'},
        ]
    }
  },
  computed: {
    posts() {
      return this.$store.state.posts.all;
    }
  }
}
</script>

<style scoped>
.container {
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  display: flex;
  justify-content: space-between;
  padding-top: 15px;
}
.links a{
  width: 23%;
}
</style>
