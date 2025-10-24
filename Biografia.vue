<script setup>

const biografia = `Soy Gabriel Romero, tengo 16 años, estudio informática y me gusta leer 
de vez en cuando. Me apasiona todo lo que tenga que ver con las computadoras y el deporte,
especialmente el boxeo. Tengo una Mac pero soy bien pobre y mi comida favorita es la pizza con piña.`

</script>

<template>
  <div class="seccion">
    <h2>Sobre mí</h2>
    <p>{{ biografia }}</p>
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

p {
  color: #555;
  line-height: 1.6;
  text-align: justify;
}
</style>