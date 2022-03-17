<template>
 <h1>{{title}}</h1>
<div>
  <Grid/>
</div>
 
</template>

<script>

import Grid from'./components/Grid.vue';

export default {
  name: 'App',
  components:{  
    Grid
  },
  data(){
    return {
      title:"Vue Demo App",
      header: "Sign up",
      message: "Please hurry before the deal closes"
     
    }
  },

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1{
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
