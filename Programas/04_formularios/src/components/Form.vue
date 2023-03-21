<script>

import ProgressBar from "./ProgressBar.vue";
import Table from "./Table.vue";
export default{
  components: {Table, ProgressBar},
  data:() =>({
    nombre:"John",
    correo:"",
    password:"",
    rol:"",
    terminos: false,
    usuarios: [],
    activo: false,
    //Valores iniciales
  }),

  methods:{
    addUser(){
      const informacion = {
        nombre: this.nombre,
        correo: this.correo,
        password: this.password,
        rol: this.rol,
        terminos: this.terminos,
        activo: this.activo,
      }
      console.log(informacion)

      //Introducir en el arreglo
      this.usuarios.push(informacion)
      this.saveData()

      //Limpiar formulario
      this.nombre="";
      this.correo="";
      this.password="";
      this.rol="";
      this.terminos=false;
      this.activo=false;
    },

    cambiarEstado(informacion, campo){
      //this.usuarios[id].terminos = !this.usuarios[id].terminos
      //console.log(informacion['campo'])
      informacion[campo] = !informacion[campo]
      this.saveData()

    },

    saveData(){
      localStorage.setItem("usuarios", JSON.stringify(this.usuarios))
    },

    cleanData(){
      this.usuarios = [];
      localStorage.clear()
    }
  },

  computed:{
    numeroUsuarios(){
      return this.usuarios.length;
    },

    progreso(){
      let registrados = 0
      this.usuarios.map( (u) => {
        if(u.activo){
          registrados++;
        }
      })

      return (registrados * 100) / this.numeroUsuarios;
      //this.numeroUsuarios
    }
  },

  mounted() {
    this.usuarios = JSON.parse(localStorage.getItem("usuarios"))  || []
  }
}
</script>

<template>

  <div class="row">

    <div class="row">
      <div  class="col-12 mb-14">
        <progress-bar :progreso="progreso"/>
      </div>
    </div>

    <div class="col-12 col-md-4">
      <form @submit.prevent="addUser">
        <div class="mb-3">
          <label for="InputNombre" class="form-label">Nombre</label>
          <input v-model.trim="nombre" type="text" class="form-control" placeholder="Nombre" id="InputNombre" required/>
        </div>

        <div class="mb-3">
          <label for="InputEmail1" class="form-label">Correo electrónico</label>
          <input v-model.trim="correo" type="email" class="form-control" placeholder="email@mail.com" aria-describedby="emailHelp" id="InputEmail1" required/>
          <div id="emailHelp" class="form-text">Nunca compartiremos esta información.</div>
        </div>

        <div class="mb-3">
          <label for="InputPassword" class="form-label">Contraseña</label>
          <input v-model="password" type="password" class="form-control" placeholder="Contraseña" id="InputPassword" required/>
        </div>

        <div class="mb-3">
          <label for="Selector" class="form-label">Rol</label>
          <select v-model="rol" class="form-select" id="Selector">
            <option disabled selected value="">Seleccionar</option>
            <option value="1">Administrador</option>
            <option value="2">Usuario</option>
            <option value="3">Invitado</option>
          </select>
        </div>

        <div class="form-check">
          <label class="form-check-label" for="flexCheckDefault">Términos y condiciones</label>
          <input v-model="terminos" class="form-check-input" type="checkbox" value="" id="flexCheckDefault">
        </div>

        <button type="submit" class="btn btn-primary">Registrar</button>
      </form>
    </div>

    <div class="col-12 col-md-8">
      <Table
          :numero-usuarios="numeroUsuarios"
          :usuarios="usuarios"
          :cambiar-estado="cambiarEstado"
          :clean-data="cleanData"
      />
    </div>

  </div>


  <!--
  <pre>
    {{correo}}
    {{rol}}
    {{terminos}}
  </pre>
  -->
</template>
