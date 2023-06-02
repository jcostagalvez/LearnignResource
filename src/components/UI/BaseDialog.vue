<template>
  <dialog open>
    <header class="header-container">
        <slot>
            <h2>{{ title }}</h2>
        </slot>
    </header>
    <section>
        <slot name="body"></slot>
    </section>
    <menu>
        <slot name="actions"></slot>
    </menu>
  </dialog>
</template>

<script>
export default {
    name:'basedialog',
    props:['title']
}
</script>

<style>

dialog {
  position: fixed;
  top: 20vh;
  left: 10%;
  width: 80%;
  z-index: 100;
  border-radius: 12px;
  border: none;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 0;
  margin: 0;
  overflow: hidden;
}

.header-container {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: rgb(28, 74, 28);
  color: white;
  width: 100%;
  padding: 1rem;
}


menu {
  padding: 1rem;
  display: flex;
  justify-content: flex-end;
  margin: 0;
}
</style>