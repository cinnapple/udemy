<template>
  <div id="app">
    <h3>Got jokes?</h3>
    <button class="btn btn-primary" @click="initJokes">Add Ten Random Jokes</button>
    <button class="btn btn-primary" @click="addJoke">Add a Joke</button>
    <br>
    <span v-for="(type, index) in types" :key="index">
      <input type="checkbox" :value="type" v-model="checkedTypes" checked>
      <label :for="type">{{type}}</label>&nbsp;
    </span>
    <div class="col-md-12">
      <Joke v-for="(joke, index) in $store.state.jokes" :joke="joke" :index="index" :key="index"
        v-show="checkedTypes.includes(joke.type)"
       />
    </div>
  </div>
</template>

<script>
import { mapActions } from "vuex";
import Joke from "./Joke";

export default {
  data() {
    return {
      types: ["general", "knock-knock", "programming"],
      checkedTypes:["general", "knock-knock", "programming"]
    }
  },
  methods: mapActions(["initJokes", "addJoke"]),
  components: {
    Joke
  }
};
</script>
