<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <div v-html="forecast"></div>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  data () {
    return {
      forecast: null
    }
  },
  mounted () {
    axios.get('/api/weatherforecast')
      .then(data => {
        this.forecast = data.body
      })
  }
}
</script>
