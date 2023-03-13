<script>
  const numero = 10;
  export default {
    data: () => ({
      contador: 10,
    }),
    methods: {
      saludar (){
        console.log("Hola Mundo!");
      },
      incrementar(){
        this.contador++; //Usamos this para usar la propiedad de una variable que este dentro de data()
      },
      disminuir(){
        this.contador--;
      },
      reiniciar(){
        this.contador = 10;
      },
    },
  };
</script>

<!-- 1) Los tempalte es como el DOM donde se renderiza todo el HTML-->
<template>

  <!-- 3) Vamos a meter todos las etiquetas en 1 div-->
  <div class="container">
  <!--
  Todo en Vue funciona con SFC: Son componentes,
  Single Funcional component,
  Un solo archivo de Vue tiene el HTML, CSS y JS de la 

  Se utiliza algo llamado tempalte, como etiqueta HTML:
  -->
    <img src="./assets/logo.svg" alt="logo vue" width="150" height="150"/>
    <small> <h1>Hola Mundo!</h1></small>
    <hr/>
    <h2>Contador: {{contador}}</h2>
    <button @click="incrementar()">+1</button>
    <button @click="disminuir()">-1</button>
    <button @click="reiniciar()">Reset</button>
  </div>
</template>

<!--2) Estilziar-->
<style scoped>  /*Con el atributo scoped se le añade un data-hash a todos los elemetnos HTML*/
/* 4) Se puede importar los estilos */

.container{
  text-align: center;
  font-weight: bolder;
}

small{
  color: brown;
}

h1{
  color: lightgreen;
} /*Se aplica a todos los elementos h1 dentro de este archivo*/

h2{
  font-size: 1.5rem;
}

button{
  cursor: pointer;
  font-size: 1.5rem;
  margin: 0px, 12px;
}

</style>