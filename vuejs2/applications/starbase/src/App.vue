<template>
  <div id="app">
    <h3>{{title}}</h3>
    <div class="col-md-12">
      <Character v-for="(id, index) in initial_ids" :key="index" :id="id" />
    </div>
  </div>
</template>

<script>
import Character from "./components/Character";

export default {
  name: "app",
  data() {
    return {
      title: "Generate Your Team",
      initial_ids: [1, 13, 14]
    };
  },
  components: {
    Character
  }
};
</script>
