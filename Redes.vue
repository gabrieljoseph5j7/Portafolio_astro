<script setup>
// EDITA TUS REDES SOCIALES AQUÍ
const redes = [
  { nombre: 'GitHub', url: 'https://github.com/gabrieljoseph5j7' },
  { nombre: 'Facebook', url: 'https://www.facebook.com/profile.php?id=100092214561851' },
  { nombre: 'Email', url: 'https://mail.google.com/mail/u/0/#search/gabrielgraka%40gmail.com' }
]
</script>

<template>
  <div class="seccion">
    <h2>Contacto</h2>
    <div class="redes">
      <a v-for="red in redes" :key="red.nombre" :href="red.url" target="_blank" class="enlace">
        {{ red.nombre }}
      </a>
    </div>
    <p class="footer-text">© 2024 - Mi Portafolio</p>
  </div>
</template>

<style scoped>
.seccion {
  background-color: white;
  padding: 25px;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  text-align: center;
}

h2 {
  color: #4CAF50;
  margin-bottom: 15px;
  border-bottom: 2px solid #4CAF50;
  padding-bottom: 8px;
}

.redes {
  display: flex;
  justify-content: center;
  gap: 15px;
  flex-wrap: wrap;
  margin-bottom: 15px;
}

.enlace {
  background-color: #4CAF50;
  color: white;
  padding: 10px 20px;
  border-radius: 5px;
  text-decoration: none;
  font-size: 14px;
}

.enlace:hover {
  background-color: #45a049;
}

.footer-text {
  color: #888;
  font-size: 12px;
  margin-top: 15px;
}
</style>
