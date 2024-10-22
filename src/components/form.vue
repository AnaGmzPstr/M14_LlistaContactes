<script setup>
import { ref } from 'vue';

// codigo
const inputNom = ref();
const inputNumero = ref();

const emit = defineEmits(['addContact']);

// enviar datos a la función addContact
const addContact = () => {
    emit('addContact', {nom: inputNom.value, telf: inputNumero.value});
}

</script>

<template>
    <input type="text" placeholder="Nom del contacte" id="nameContact" v-model="inputNom" required>
    <input type="number" placeholder="Número del contacte" v-model="inputNumero" required>
    <button @click="addContact">Afegir contacte</button>

</template>