<script>
export default {
  props: {
    progreso: Number
  }
}
</script>

<template>

  <div>
    <h2>Progreso {{progreso}}%</h2>
  </div>

  <div class="progress" role="progressbar" aria-label="Animated striped example" :aria-valuenow="progreso" aria-valuemin="0" aria-valuemax="100">
    <div class="progress-bar progress-bar-striped progress-bar-animated bg-success" :style="`width: ${progreso} %`">
      {{progreso}}
    </div>
  </div>

</template>