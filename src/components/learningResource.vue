<template>
  <li>
    <basecard>
        <header>
            <h3>{{ resource.title }}</h3>
            <basebutton @click.native="deleteResource"  typeButton="borrar"> Borrar </basebutton>
        </header>

        <p>{{resource.description}}</p>
        <nav>
            <a :href="resource.link"> Ver Link </a>
        </nav>
    </basecard>

  </li>
</template>

<script>
import basecard from './UI/BaseCard.vue';
import basebutton from './UI/BaseButton.vue';
export default {
    name: 'learningResource',
    inject:['resources'],
    components: {
        basecard, 
        basebutton
    },
    props:{
        resource:{
            type:Object,
            default: null
        }
    },
    methods:{
        deleteResource(){
            
            const resourceToDelete = this.resources.find(r => r.id == this.resource.id);
            const index = this.resource.indexOf(resourceToDelete);
            console.log(index);
            //this.resources.splice(resourceToDelete,1);
        }
    }
}
</script>

<style>
    li{
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
        border-radius: 2%;
        box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;        
        padding: 2%;
        max-width: 100%;
        max-height: 100%;
    }

    header{
        width: 100%;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }

    basecard{
        width: 100%;
    }

</style>