<template>
<div>
    <div class="nav">
      <p>Savoir Inutile</p>
    </div>
  <div class="container">
    <div>
      <h1 class="title" >
       {{ phrase }}
      </h1>
      <a class="button--green" v-on:click="update">New Fact </a>
    </div>
  </div>
</div>  
</template>

<script>
import axios from 'axios'

export default {
  data(){
    return{
      phrase: []
    }
  },
  methods:{
    update(){
      axios.get('https://uselessfacts.jsph.pl/random.json?language=en')
    .then(response => this.phrase = response.data.text)
    }
  },
  mounted(){
    axios.get('https://uselessfacts.jsph.pl/random.json?language=en')
    .then(response => this.phrase = response.data.text)
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 90vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;

}
.nav{
  border-bottom:2px solid lightgray;
  width: 100%;
   display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
  height: 55px;
}
.nav p{
  font-size: 30px;
  color: #35495e;
}
.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 50px;
  color: #35495e;
  letter-spacing: 1px;
  padding: 2em;
}




</style>
