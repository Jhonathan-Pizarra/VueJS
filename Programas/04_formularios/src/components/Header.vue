<script>
export default{
  data:() =>({
    url:"https://cdn.svgporn.com/logos/vue.svg?response-content-disposition=attachment%3Bfilename%3Dvue.svg",
  }),

}
</script>

<template>
  <div class="container text-center">
    <div class="row">
      <div class="col">
        <h1>Formularios</h1>
      </div>
      <div class="col">
        <img width="100" :src="url" :alt="url"/>
      </div>
    </div>
  </div>
  <hr/>
</template>