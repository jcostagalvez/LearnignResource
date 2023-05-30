<template>
    <ul class="lista-recursos">
      <learningResource  v-for="res in storedResources" :key="res.id" :resource="res"/>
    </ul>
</template>

<script>
import learningResource from './learningResource.vue';

export default {
  name: 'storedresources',
  components:{
    learningResource
  },
  data(){
    return{
      storedResources: [
        {
          id: 1,
          title: 'Moodle UAM',
          description: 'Materiales de las difetentes clases del master',
          link: 'https://formacion.uam.es/login/index.php'
        },
        {
          id: 2,
          title: 'Hospital Niño Jesús',
          description: 'Materiales que aplican ellos en la consulta',
          link: 'https://www.comunidad.madrid/hospital/ninojesus/nosotros'
        }
      ]
    }
  }
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
