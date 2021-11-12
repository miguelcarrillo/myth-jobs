<template>
  <div class="app">
    <p>{{name}} - {{age}}</p>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive, toRefs } from "vue";

export default defineComponent({
  name: "App",
  components: {},
  setup() {
    const state = reactive({
      name: "Link",
      age: 25 as string | number,
    });
    return {
      ...toRefs(state),
    };
  },
});
</script>

<style>
</style>
