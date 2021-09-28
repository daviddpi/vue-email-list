<template>
  <div id="app">

    <h1>Le mie email:</h1>
    <div v-if="arrayEmail.length == 10">
      <Email v-for="(mail, index) in arrayEmail" :key="index" :emailText="mail" :emailIndex="index"/>
    </div>
    
  </div>
</template>

<script>
import axios from 'axios'
import Email from './components/Email.vue'

export default {
  name: 'App',
  components: {
    Email,
  },

  data(){
    return{
      arrayEmail: [],
    }
  },

  mounted(){
    for(let i = 0; i < 10; i++){
        axios.get('https://flynn.boolean.careers/exercises/api/random/mail').then( (response) => {
        const result = response;
        this.arrayEmail.push(result.data.response);
        console.log(result.data.response);
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
  margin-top: 60px;
}
</style>
