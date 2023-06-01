<template>
    <ul class="lista-recursos">
      <learningResource  v-for="res in resources" :key="res.id" :resource="res"/>
    </ul>
</template>

<script>
import learningResource from './learningResource.vue';

export default {
  name: 'storedresources',
  inject:['resources'],
  components:{
    learningResource
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
.lista-recursos{
  display: grid;
  grid-template-columns: 100%;
  grid-template-rows: 50% 50%;
  gap: 5%;
}
</style>
