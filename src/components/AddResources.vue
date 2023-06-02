<template>
  <div class="form-container">

    <basedialog v-if="inputIsInvalid" title="ERROR">
        <!-- Rellenar los diferentes slots -->
        <template #body> 
            <p> Uno de los valores esta vacio, por favor rellene todos los valores para ingresar un recurso</p>
        </template>
        <template #actions> 
            <basebutton @click.native="closeModal"  typeButton="borrar"> Cerrar </basebutton>
        </template>
    </basedialog>

    <form @submit.prevent="submitData">
        <div class="form_field">
            <label for="title"> Titulo</label>
            <input class="field-input" id="title" name="title" type="text" ref="titleinput"/>
        </div>
        <div class="form_field">
            <label for="description"> Descripcion</label>
            <textarea class="field-input" id="description" name="description" ref="descriptioninput"/>
        </div>
        <div class="form_field">
            <label for="link"> Link</label>
            <input class="field-input" id="link" name="link" type="url" ref="urlinput"/>
        </div>
        <div class="form_button">
            <basebutton type="submit" typeButton="crear"> Generar un recurso</basebutton>
        </div>
    </form>
  </div>
</template>

<script>
import basebutton from './UI/BaseButton.vue';
import basedialog from './UI/BaseDialog.vue';

export default {
    components:{ 
        basebutton,
        basedialog
    },
    inject:['addResource'],
    data(){
        return{
            inputIsInvalid : false
        }
    },
    methods:{
        submitData(){  
            const title = this.$refs.titleinput.value;
            const description = this.$refs.descriptioninput.value;
            const url = this.$refs.urlinput.value;

            if(title.trim() == '' || description.trim() == '' || url.trim() == ''){
                console.log('esta vacio');
                this.inputIsInvalid = true;
            }else{
                this.addResource(title, description, url);
            }
        },

        closeModal(){
            this.inputIsInvalid = false
        }
    }
}
</script>

<style>
form{
    margin: 5%;
    display: grid;
    gap: 5%;
    grid-template-columns: 100%;
}

.form_field{
    height: 40%;
    margin-bottom: 5%;
    display: flex;
    flex-direction: column;
}
.form_field label{
    margin-bottom: 2%;
}
.field-input {
    border: none;
    border-bottom: 2px solid rgb(28, 74, 28);
}
.field-input:focus{
    outline: none;
}
.form_button{
    margin-top: 1%;
}
</style>