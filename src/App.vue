<template>
  <div id="app">
    <headerapp :title="title"/>
    <resources/>
  </div>
</template>

<script>
import resources from './components/TheResources.vue'
import headerapp from './components/layouts/HeaderApp'
export default {
  name: 'App',
  components: {
    resources,
    headerapp
  },
  data (){
    return{
      title: 'Recuerdame Esto'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 0%;
  padding: 0%;
  box-sizing: border-box;
  height: 100%;
  width: 100%;
}
</style>
