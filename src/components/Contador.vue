<template>
    <div>
      <h2>REF</h2>
      <p>El contador es {{ contador }}</p>
      <button @click="incrementar">Incrementar</button>
      <button @click="decrementar">Decrementar</button>
      <button @click="reiniciar">Reiniciar</button>
    </div>
</template>

<script>
import { ref } from 'vue';

const contador = ref(0);

const incrementar = () => {
  contador.value++ 
}

const decrementar = () => {
  contador.value--
}

const reiniciar = () => {
  contador.value = 0
}
</script>

<style>

</style>