<script>
  import Formulario from '../src/components/Formulario.vue';
  import Data from '../src/components/Data.vue';
  import Grid from '../src/components/Grid.vue';

  export default
  {
    components: {Formulario, Data, Grid}
  };
</script>

<template>
  <div class="container">
    <h1>Cotizador de Criptomonedas</h1>
    <Grid>
      <Formulario/>
      <Data/>
    </Grid>
    <h6><strong>Vue 3 + SASS</strong></h6>
  </div>
</template>

