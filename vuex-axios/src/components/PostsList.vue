<template>
  <div class="postsList">
      <div v-for="post in posts" :key="post.id">
          <h1>{{ post.title }}</h1>

      </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
    computed: {
        ...mapState('posts', ['posts'])
    },
    created(){
        this.$store.dispatch('posts/loadPosts')
    }
}
</script>

<style>

</style>