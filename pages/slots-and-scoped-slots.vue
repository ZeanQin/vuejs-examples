<template>
  <b-container>
    <!-- slots -->
    <b-row class="my-4">
      <b-col>
        <h2>Slot</h2>
        <my-button title="Title 1 passed via property">
          Content 1 passed via slot
        </my-button>
        <my-button title="Title 2 passed via property">
          Content 2 passed via slot
        </my-button>
      </b-col>
    </b-row>

    <!-- scoped slots -->
    <b-row class="my-4">
      <b-col>
        <h2>Scoped slot</h2>
        <my-list :items="people">
          <slot slot-scope="{ one, two }">
            Name: {{ one.name }}, Age: {{ one.age }}, Factor: {{ two }}
          </slot>
        </my-list>
        <my-list :items="cubes">
          <slot slot-scope="{ one, two }">
            Width: {{ one.width }} Height: {{ one.height }} Depth:
            {{ one.depth }}
            , Factor: {{ two }}
          </slot>
        </my-list>
      </b-col>
    </b-row>
  </b-container>
</template>

<script lang="ts">
import Vue from 'vue'
import Button from '~/components/slots-and-scoped-slots/Button.vue'
import List from '~/components/slots-and-scoped-slots/List.vue'

export default Vue.extend({
  components: {
    'my-button': Button,
    'my-list': List,
  },
  data() {
    return {
      people: [
        { name: 'Alex', age: 30 },
        { name: 'Tim', age: 30 },
        { name: 'Ash', age: 30 },
      ],
      cubes: [
        { width: 10, height: 30, depth: 10 },
        { width: 10, height: 30, depth: 10 },
        { width: 10, height: 30, depth: 10 },
      ],
    }
  },
})
</script>
