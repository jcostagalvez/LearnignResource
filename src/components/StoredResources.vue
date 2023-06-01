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
