<script setup>
import { ref, reactive } from 'vue';

// ejemplo div REF
const contador = ref(0);

const incrementar = () => {
  contador.value++; 
};

const decrementar = () => {
  contador.value--;
};

const reiniciar = () => {
  contador.value = 0;
};

// ejemplo div REACTIVE
const usuari = reactive({
  nom: "Pep",
  cognom: "Guardiola",
  dni: "48196179R",
  edad: 18
});

const aumentarEdad = () => {
  usuari.edad++;
};

// Ejemplo v-bind
const titol = "El max es un buen compañero"
const imageURL = "https://imgs.search.brave.com/CEJKjQJ4bSF-pUgbrx8pBMv1JHoH5gnISfqXFIfqPno/rs:fit:860:0:0:0/g:ce/aHR0cHM6Ly90c2Uy/Lm1tLmJpbmcubmV0/L3RoP2lkPU9JUC45/RVJKMFhiYk80YkdV/ejRiclVLekVnSGFE/diZwaWQ9MTUuMQ";

// Ejemplo v-model
const nomUsuario = ref("");

// Ejemplo v-for
const productos = [
  {
    id:1,
    nombre:"Botella de agua",
    precio: 0.27
  },
  {
    id:2,
    nombre:"Paquete bizcochitos de Cacaolat",
    precio: 3.54
  },
  {
    id:3,
    nombre:"Piruleta",
    precio: 0.99
  },
]

// Ejemplo v-else
const logat = ref(false)
const logearse = () =>{
  logat.value = !logat.value
}

// Ejemplo v-show
const mostrar = ref(true)
</script>

<template>
  <div>
    <h1>Conceptos básicos de VUE Hugo Alonso</h1>
    <div>
      <h1 v-bind:title="titol">Pasa el ratolín por aquín</h1>
      <h2>Ejemplo de v-model</h2>

      <img class="imagen" :src="imageURL">
    </div>
    <div>
      <h2>REF</h2>
      <p>El contador es {{ contador }}</p>
      <button @click="incrementar">Incrementar</button>
      <button @click="decrementar">Decrementar</button>
      <button @click="reiniciar">Reiniciar</button>
    </div>

    <div>
      <h2>REACTIVE</h2>
      <p>El usuario es {{ usuari.nom }} {{ usuari.cognom }}, y tiene {{ usuari.edad }} años</p>
      <button @click="aumentarEdad">Ha crecido</button>
    </div>

    <div>
      <h2>Exemple v-model</h2>
      <h3>Nombre de usuario: {{ nomUsuario }}</h3>
      <input type="text" placeholder="Escribe tu nombre de usuario" v-model="nomUsuario">
    </div>

    <div>
      <h2>Ejemplo v-for</h2>
      <ul>
        <li v-for="producto in productos" :key="producto.id">
          {{ producto.nombre }} - {{ producto.precio }} €
        </li>
      </ul>
    </div>

    <div>
      <h2>Ejemplo de v-else</h2>
      <p v-if="logat">Estás logeado!!</p>
      <p v-else>No estás logeado.</p>
      <button @click="logearse">Logearse</button>
    </div>

    <div>
      <h2>Ejemplo de v-show</h2>
      <button @click="mostrar = !mostrar">Alternar visibilidad</button>
      <p v-show="mostrar">Ahora me ves</p>
    </div>
  </div>
</template>

<style scoped>
div{
  border-radius: 15px;
  margin: 15px;
  padding:15px;
  border: 1px solid black 
}

@media(max-width : 748px){
  .imagen{
    width: 175px;
    height: auto;
  }
}
</style>
