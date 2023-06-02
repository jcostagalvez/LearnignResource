<template>
    <div>
        <div class="button-container">
            <basebutton typeButton="tab" @click.native="setSelectedTab('storedresources')" > Recursos guardados</basebutton>
            <basebutton typeButton="tab" @click.native="setSelectedTab('addresources')" > añadir un rescurso</basebutton>
        </div> 
        <component :is="selectedTab"> </component>
    </div>
</template>

<script>
import basecard from './UI/BaseButton.vue';
import basebutton from './UI/BaseButton.vue';
import storedresources from './StoredResources.vue';
import addresources from './AddResources.vue';

export default {
    name: 'theResources',
    components: {
        basecard, 
        basebutton,
        storedresources,
        addresources
    },
    provide(){
            return{
                resources: this.storedResources,
                addResource: this.addResource
            }
        },
    data(){
        return {
            selectedTab : 'storedresources',
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
        };
    },
    methods:{
        setSelectedTab(tab) {
            console.log('selectedTab' + this.selectedTab);
            this.selectedTab = tab;
        },

        addResource(title, description, url){
            console.log(title);
            console.log(description);
            console.log(url);

            const newResource = {
                id: this.storedResources.length + 1,
                title: title,
                description: description,
                url: url
            }
            
            this.storedResources.unshift(newResource);
            this.selectedTab = 'storedresources';

        }
    }
}
</script>

<style>
.button-container{
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: first baseline;
}
</style>