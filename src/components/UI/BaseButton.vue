<template>
    <button :type="type" :class="typeButton"> 
        <slot> </slot>
    </button>
</template>

<script>
export default {
    name:'basebutton',
    props:{
        typeButton:{
            type: String
        },
        type:{
            type: String
        }
    }
}
</script>

<style>
    .borrar{
        background-color: white;
        cursor: pointer;
        width: 20%;
        height: 50px;
        border-radius: 5%;
        color: rgb(140, 35, 35);;
        border: none;
    }
    .borrar:hover{
        background-color: rgb(140, 35, 35);
        color: white;
    }
    .crear{
        cursor: pointer;
        width: 20%;
        height: 50px;
        border-radius: 5%;
        color: rgb(28, 74, 28);
        border: none;
    }
    .crear:hover{
        color: white;
        background: rgb(28, 74, 28);
    }
    .tab{
        cursor: pointer;
        width: 20%;
        height: 50px;
        background-color: white;
        color:rgb(28, 74, 28);
        border: none;
    }
    .tab:hover{
        color: white;
        background: rgb(190, 187, 187);
    }
    .tab:focus{
        color: white;
        background: rgb(190, 187, 187);
    }
</style>