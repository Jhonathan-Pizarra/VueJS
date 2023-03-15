
<script>
export default {
  data: () =>({
    titulo: "Hola Vue3!",
    html: "<h3> Soy h3 </h3>",
    edad: 16,
    usuarios: ["John", "Paul","George","Ringo"],
    clicks: 0,
    url: "https://cdn.svgporn.com/logos/github-icon.svg?response-content-disposition=attachment%3Bfilename%3Dgithub-icon.svg"
  }),

  methods: {
    add(){
      this.edad++
    },
    dec(){
      this.edad--
    },
    click(){
      this.clicks++
    }
  }

}
</script>

<template>
  <div>
    <div>
      <h1>Directivas</h1>
      <br/>
    </div>

    <div v-html="html"></div>

    <span>
    {{edad}}
  </span>

    <h2 v-if="edad >= 18 && edad > 0 && edad < 100">Mayor de edad</h2>
    <h2 v-else-if="edad < 18 && edad > 0 && edad < 100">Menor de edad</h2>
    <h2 v-else>Esa no es una edad.</h2>

    <ul>
      <li v-for="usuario in usuarios" :key="usuario">{{ usuario }}</li>
    </ul>

    <button @click="add()">Aumentar</button>
    <button @click="dec()">Disminuir</button>

  </div>
  <img :src="url"/>
  <div @click="click" class="contador">Clicks: {{clicks}}</div>
</template>

<style scoped>

div{
  text-align: center;
  margin: 0px 2rem;
}

.contador{
  background: tomato;
  color: snow;
  font-weight: bold;
  height: 400px;
}
</style>