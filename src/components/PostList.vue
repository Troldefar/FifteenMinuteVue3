<template>
  <div class="post-list">
    <div v-for="post in posts" :key="post">
      <Post :post="post" />
    </div>
  </div>
</template>

<script>
import Post from './Post';
export default {
  props: ['posts'],
  components: {
    Post
  },
  setup(props) {
    
  }
}
</script>

<style>

</style>