<script setup>
import { reactive, ref, computed } from 'vue';
import Form from './components/form.vue'

const arrayUsers = reactive([]);

const gestioUsers = (datosRecibidos) => {
  arrayUsers.push(datosRecibidos);
}

// buscador
const buscador = ref('');
const arrayFiltrado = computed(() =>
  arrayUsers.filter(user => user.nom.toLowerCase().includes(buscador.value))
)

</script>

<template>
  <h1>Llibreta de contactes</h1>
  <main>
    <Form @addContact="gestioUsers"></Form>
    <hr>
    <input type="text" placeholder="Busca..." v-model="buscador"/>
    <ul>
      <li v-for = 'user in arrayFiltrado' :key ='user.nom'>{{ user.nom }} - {{ user.telf }}</li>
    </ul>
  </main>
</template>