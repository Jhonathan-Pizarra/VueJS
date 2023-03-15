<!--Funcionalidades (JS)-->
<script>
import Grid from "./Grid.vue";
export default {
  components: {Grid},
  props:{
    url:{
      String,
    },
    nombre:{
      String
    }
  }
}

</script>

<!--Punto de inicio HTML-->
<template>
  <grid>
    <img
        :src="url"
        :alt="nombre"
    />

    <h2>{{nombre}}</h2>

    <a :href="url"
       target="_blank">Visitar
    </a>

  </grid>
</template>

<!--Estilos CSS-->
<style scoped>

img{
  width: 8rem;
  height: 8rem;
  padding: 0.5rem;
}

a{
  text-decoration: none;
  color: cadetblue;
  padding:  0.3rem;
  border-radius: 5px;
  border: 1px solid #F2F2F2;
}

</style>
