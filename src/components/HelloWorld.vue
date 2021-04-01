<template>
  <div class="hello">
    <div class="container d-flex justify-content-center">
      <img src="@/assets/starwars.png" alt="">
    </div>
    <div class="container">
    </div>
    <div class="container">
      <div class="row">
        <div v-for="result in results" :key="result" class="col">
          <div class="card mb-3 border-0 shadow" style="width: 18rem;">
            <div class="card-body">
              <h5 class="card-title">{{ result.name }}</h5>
              <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
              <ul class="list-group list-group-flush">
                <li class="list-group-item">birth year: {{ result.birth_year }}</li>
                <li class="list-group-item">gender: {{ result.gender }}</li>
                <li class="list-group-item">homeworld:
                  <a :href="result.homeworld" target="_blank">
                    <img class="img-fluid ml-2" src="@/assets/globe.svg" alt="homeworld">
                  </a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'

  export default {
    data() {
      return {
        results: []
      }
    },

    props: {
      msg: String,
    },
    methods: {
      getStarwars() {
        axios.get('https://swapi.dev/api/people/')
          .then(response => this.results = response.data.results)
        // .then(response => console.log(response));
      }
    },

    created() {
      this.getStarwars()
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>