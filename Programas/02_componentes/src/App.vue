<template>

  <h1>Componentes</h1>
  <br/>

  <card
      url="https://cdn.svgporn.com/logos/vue.svg?response-content-disposition=attachment%3Bfilename%3Dvue.svg"
      nombre="Vue.Js"
  />

  <card
      url="https://cdn.svgporn.com/logos/react.svg?response-content-disposition=attachment%3Bfilename%3Dreact.svg"
      nombre="React.Js"
  />

  <card
      url="https://cdn.svgporn.com/logos/angular-icon.svg?response-content-disposition=attachment%3Bfilename%3Dangular-icon.svg"
      nombre="Angular.Js"
  />

  <card
      url="https://cdn.svgporn.com/logos/nextjs.svg?response-content-disposition=attachment%3Bfilename%3Dnextjs.svg"
      nombre="Next.Js"
  />

  <card
      url="https://cdn.svgporn.com/logos/svelte-icon.svg?response-content-disposition=attachment%3Bfilename%3Dsvelte-icon.svg"
      nombre="Svelte.Js"
  />

  <card/>


</template>

<script>
import Card from "./components/Card.vue"

export default {
  components:{Card},
}

</script>
<!--
Los componentes entran en acción cunado vamos contruyendo nuesrtras aplicaciones
los componentes pueden ahislarse o compartir estados, datos
de tal manera que podemos agregar oquitar funcionalidades a un sitio web
-->