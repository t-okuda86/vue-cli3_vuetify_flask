<template>
  <div class="home">
    <HeaderComponent title="ホーム" />
    <Part1 />
    <div>
      <p>Home page</p>
      <p>Random number from backend: {{ randomNumber }}</p>
      <button @click="getRandom">New random number</button>
  </div>
  </div>
</template>



<script>
import HeaderComponent from '@/components/HeaderComponent.vue'
import Part1 from '@/components/Part1.vue'
import axios from 'axios'


export default {
  name: 'home',
  components: {
    HeaderComponent,
    Part1
  },
  data () {
    return {
      randomNumber: 0
    }
  },
  methods: {
      getRandomInt (min, max) {
        min = Math.ceil(min)
        max = Math.floor(max)
        return Math.floor(Math.random() * (max - min + 1)) + min
      },
      getRandom () {
        // this.randomNumber = this.getRandomInt(1, 100)
        this.randomNumber = this.getRandomFromBackend()
      },
      getRandomFromBackend () {
        const path = `http://localhost:5000/api/random`
        axios.get(path)
        .then(response => {
          this.randomNumber = response.data.randomNumber
        })
        .catch(error => {
          console.log(error)
        })
    }
  },
  created () {
    this.getRandom()
  }
}
</script>