<template>
  <div class="hello">
    <div class="container">
      <p class="bg-primary text-white">Star Wars API</p>
    </div>
    <div class="container">
      <div class="d-flex">
        <div class="card" style="width: 18rem;">
          <img src="#" class="card-img-top" alt="#">
          <div class="card-body">
            <h5 class="card-title">{{ CharacterData.name }}</h5>
            <p class="card-text">
              <span>height:</span><span>{{ CharacterData.height }}</span>
              <span>mass:</span><span>{{ CharacterData.mass }}</span>
              <span>hair color:</span><span>{{ CharacterData.hair_color }}</span>
            </p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    props: {
      msg: String,
      id: String,
      data: function () {
        return {
          CharacterData: {}
        }
      }
    },
    methods: {
      getUnits: function () {
        fetch(`https://swapi.dev/api/people/${this.id}/`)
          .then(response => response.json())
          .then(data => this.CharacterData = data)
      }
    },
    created: function () {
      this.getUnits()
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>