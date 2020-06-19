<template>
  <div>
    <slot v-for="item in items" :one="item" :two="two">
      <!-- fallback content here -->
    </slot>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    items: {
      type: Array,
      default: () => [],
    },
  },
  data() {
    return {
      two: 2,
    }
  },
})
</script>
