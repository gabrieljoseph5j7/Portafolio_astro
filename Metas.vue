<script setup>
// EDITA TUS METAS AQUÍ
const metas = [
  'Aprender más sobre desarrollo web',
  'Entrar a la universidad con Cadmen y Torres',
  'Trabajar en una empresa tecnológica',
  'Graduarme y tener trabajo estable sin hijos ni deudas'
]
</script>

<template>
  <div class="seccion">
    <h2>Mis Metas</h2>
    <ul>
      <li v-for="(meta, index) in metas" :key="index">
        {{ meta }}
      </li>
    </ul>
  </div>
</template>

<style scoped>
.seccion {
  background-color: white;
  padding: 25px;
  border-radius: 10px;
  margin-bottom: 20px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

h2 {
  color: #4CAF50;
  margin-bottom: 15px;
  border-bottom: 2px solid #4CAF50;
  padding-bottom: 8px;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  padding: 10px;
  margin: 8px 0;
  background-color: #f9f9f9;
  border-left: 4px solid #4CAF50;
  color: #555;
}
</style>