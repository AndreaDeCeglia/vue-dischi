<template>
  <div id="app" class="bg-dark text-white py-5">

    <h1>Best Boolean CDs</h1>

    <div class="container">
      <div class="d-flex row justify-content-between align-items-center flex-wrap p-3">
        <CardComp
          v-for="(element, index) in CDdata"
          :key="index"
          :CD="element"
        />
      </div>
    </div>
  
  </div>
</template>

<script>
import CardComp from './components/CardComp.vue'
import axios from 'axios';

export default {
  name: 'App',
  components: {
    CardComp,
  },
  data(){
    return{
      CDdata: '',
    }
  },
  mounted(){
    this.getCD();
  },
  methods: {
    getCD(){
      axios.get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((response) =>{
          this.CDdata = response.data.response
        })
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  height: 100vh;
}

</style>
