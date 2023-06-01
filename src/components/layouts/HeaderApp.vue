<template>
  <div class="title">
    <h1>{{title}}</h1>
  </div>
</template>

<script>
export default {
    name:"headerapp",
    props:["title"]

}
</script>

<style>
.title{
    margin: 0%;
    background: rgb(28, 74, 28);
    height: 5rem;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

h1{
    color: white;
    text-transform: uppercase;
    font-size: 50px;
    font-weight: bold;
}
</style>