<template>
  <div>
    <div v-for="(item, itemIndex) in items" :key="itemIndex" class="list-item">
      <slot :one="item" :two="two">
        <!-- fallback content here -->
      </slot>
    </div>
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

<style lang="scss" scoped>
$primary-color: #66615b;
.list-item {
  height: 50px;
  padding-left: 20px;
  display: flex;
  align-items: center;
  box-shadow: 0 6px 10px -4px rgba(0, 0, 0, 0.15);
  color: $primary-color;
}
</style>
