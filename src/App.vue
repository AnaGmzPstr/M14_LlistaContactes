<script setup>
import { reactive, ref } from 'vue';
import Form from './components/form.vue'

const arrayUsers = reactive([]);

const gestioUsers = (datosRecibidos) => {
  arrayUsers.push(datosRecibidos);
}

</script>

<template>
  <h1>Llibreta de contactes</h1>
  <main>
    <Form @addContact="gestioUsers"></Form>
    <ul>
      <li v-for = 'user in arrayUsers' :key ='user.nom'>{{ user.nom }} - {{ user.telf }}</li>
    </ul>
  </main>
</template>

<style scoped>

</style>
