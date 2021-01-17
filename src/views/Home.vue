<template>
  <div>
    <div v-if="error">{{error}}</div>
    <PostList :posts="posts" />
  </div>
</template>

<script>
import PostList from '../components/PostList';
import getPosts from '../composables/getPosts';
export default {
  name: 'Home',
  components: {
    PostList
  },
  setup() {
    const { posts, error, load } = getPosts();
    load();
    return {
      posts,
      error
    }

  }
}
</script>
