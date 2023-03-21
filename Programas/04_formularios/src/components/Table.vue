<script>
export default {
  props: ['numeroUsuarios', 'usuarios', 'cambiarEstado', 'cleanData'],
}
</script>

<template>


  <div class="row my-2">
    <div class="col-6">
      <h3>Cantidad Usuarios: {{numeroUsuarios}}</h3>
    </div>

    <div class="col-6 text-end">
      <button @click="cleanData" class="btn btn-warning">Barrer Usuarios</button>
    </div>
  </div>

  <hr/>

    <div class="table-responsive">
      <table class="table table-hover">
        <thead>
        <tr>
          <th scope="col">#</th>
          <th scope="col">Nombre</th>
          <th scope="col">Correo</th>
          <th scope="col">Rol</th>
          <th scope="col">Acepta Términos</th>
          <th scope="col">Activo</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="(informacion, index) in usuarios" :key="index">
          <!--<tr v-for="informacion in usuarios" :key="informacion.index">-->
          <th scope="row">{{index+1}}</th>
          <td>{{ informacion.nombre }}</td>
          <td>{{informacion.correo}}</td>
          <td>{{ informacion.rol }}</td>
          <td @click="cambiarEstado(informacion, 'terminos')" :class="informacion.terminos ? 'bg-success' : 'bg-danger'">{{ informacion.terminos ? "Si" : "No" }}</td>
          <!--<td @click="cambiarEstado(informacion)">Cambiar</td>-->
          <td
              :class="informacion.activo ? 'bg-success' : 'bg-danger'"
              @click="cambiarEstado(informacion, 'activo')"
          >
            {{ informacion.activo ? "Activo" : "Inactivo" }}
          </td>
        </tr>
        </tbody>
      </table>
    </div>

</template>