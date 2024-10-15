

<script>
import { reactive } from 'vue';


const usuari = reactive({
  nom: "Pepe",
  cognom: "Viyuela",
  dni: "48196179R",
  edad: 18
})

const aumentarEdad = () => {
  usuari.edad++
}
</script>

<template>
  <div>
    
      <h2>REACTIVE</h2>
      <p>El usuario es {{ usuari.nom }} {{ usuari.cognom }}, y tiene {{ usuari.edad }} años</p>
      <button @click="aumentarEdad">Ha crecido</button>

  </div>
</template>

<style>

</style>