<template>
  <div id="app">
    <h3>{{title}}</h3>
    <div class="row">
      <Character
        v-for="(id, index) in initial_ids"
        :id="id"
        :key="index"
      />
    </div>
  </div>
</template>

<script>
import Character from "./components/Character";
export default {
  name: 'app',
  data(){
    return {
      title: "Generate your Team",
      initial_ids: [1, 10, 11]
    }
  },
  components: {
    Character
  }
}
</script>
