<template>
  <div>
    <router-link :to="{ name: 'Details', params: { id: post.id }}">
      <h3>
        {{ post.title }}
      </h3>
    </router-link>
    <h5>
      Snippet
    </h5>
    <p>
      {{ snip }}
    </p>
    <div v-for="tag in post.tags" :key="tag">
      <button>
        {{ tag }}
      </button>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue';
export default {
  props: ['post'],
  setup(props) {
    const snip = computed(() => {
      return props.post.body.substr(0, 1) + '...';
    });
    return {
      snip
    }
  }
}
</script>

<style>

</style>