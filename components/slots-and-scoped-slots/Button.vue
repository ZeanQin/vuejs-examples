<template>
  <div class="btn">
    <h4 v-if="title">{{ title }}</h4>
    <slot />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    title: {
      type: String,
      default: '',
    },
  },
})
</script>

<style lang="scss" scoped>
$primary-color: #00ae76;

.btn {
  border: 2px solid $primary-color;
  padding: 10px;
  font-size: 16px;
  border-radius: 20px;
  color: $primary-color;

  &:hover {
    background-color: $primary-color;
    color: white;
  }
}
</style>
