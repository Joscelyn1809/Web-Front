<template>
  <v-table>
    <thead>
      <tr>
        <th class="text-left">Autor</th>
        <th class="text-left">Titulo</th>
        <th class="text-left">Post</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item, index) in datos" :key="item.id">
        <td>{{ autores[item.userId - 1].name }}</td>
        <td>{{ item.title }}</td>
        <td>{{ item.body }}</td>
      </tr>
    </tbody>
  </v-table>
</template>

<script setup>
import { ref, onMounted } from "vue";
const datos = ref([]);
onMounted(async () => {
  const r = await fetch("https://jsonplaceholder.typicode.com/users/1/posts");
  datos.value = await r.json();
  console.log(datos.value);
});

const autores = ref([]);
onMounted(async () => {
  const a = await fetch("https://jsonplaceholder.typicode.com/users");
  autores.value = await a.json();
  console.log(autores.value);
});
</script>
