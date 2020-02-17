<template>
  <div class="container">
    <div>
      <logo />
      <h1 class="title">
        nuxt-fundamental
      </h1>
      <h2 class="subtitle">
        My extraordinary Nuxt.js project
      </h2>
      <div class="links">
        <nuxt-link v-for="post in posts" v-bind:key="post.id" :to="{name: 'posts-id', params: {id: post.id}}" class="button--grey">
          {{post.title}}
        </nuxt-link>

      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'

export default {
      head(){
      return {
        title: 'Pagina de Posts 🐶'
      }
    },
  components: {
    Logo
  },
  computed: {
    posts () {
      //console.log(this.$store.state.prueba.all);
      return this.$store.state.prueba.all;
      
    }
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  /*color: #35495e;-*/
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
  padding-top: 15px;
}
</style>
