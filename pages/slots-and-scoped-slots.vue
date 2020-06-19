<template>
  <b-container>
    <my-button name="Some other data">Button 1</my-button>
    <my-button name="Some other data">Button 2</my-button>
  </b-container>
</template>

<script lang="ts">
import Vue from 'vue'
import Button from '~/components/slots-and-scoped-slots/Button.vue'
export default Vue.extend({
  components: {
    'my-button': Button,
  },
})
</script>
