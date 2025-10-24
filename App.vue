<script setup>
import Encabezado from './components/Encabezado.vue'
import Biografia from './components/Biografia.vue'
import Metas from './components/Metas.vue'
import Proyectos from './components/Proyectos.vue'
import Redes from './components/Redes.vue'
</script>


<template>
  <div id="app">
    <Encabezado />
    <main class="main-content">
      <Biografia />
      <Metas />
      <Proyectos/>
    </main>
    <Redes/>
  </div>
</template>

<style scoped>
#app {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}

.main-content {
  flex: 1;
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
  width: 100%;
  box-sizing: border-box;
}

@media (max-width: 768px) {
  .main-content {
    padding: 1rem;
  }
}
</style>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  margin: 0;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  background-attachment: fixed;
}
</style>