<template>
  <div class="col-md-4" @click="switchCharacter">
    <div class="character-card">
      <div class="card-block">
        <h4 class="card-title">{{character.name}}</h4>
        <p clas="card-text">Heigh:{{character.height}} </p>
        <p clas="card-text">Mass: {{character.mass}}</p>
        <p clas="card-text">Eye color: {{character.eye_color}}</p>
        <p clas="card-text">Hair color: {{character.hair_color}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['id'],
  data() {
    return {
      character: {}
    }
  },
  methods: {
    fetchCharacter(id) {
      fetch(`https://swapi.co/api/people/${id}`, {
        method: "GET"
      }).then(response => response.json())
        .then(json => this.character = json)
    },
    switchCharacter() {
      let random_id = Math.floor(Math.random() * 83) + 1;
      this.fetchCharacter(random_id);
    }
  },
  created() {
    this.fetchCharacter(this.id)
  }
}
</script>
