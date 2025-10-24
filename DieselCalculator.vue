<script setup>
import { ref, computed } from 'vue'

const RENDIMIENTO = 4.286

const kilometros = ref(0)
const horas = ref(0)
const minutos = ref(0)
const velMax = ref(0)

const calcularDiesel = computed(() => {
  if (kilometros.value > 0) {
    const horasTotales = horas.value + (minutos.value / 60)
    const consumoDistancia = kilometros.value / RENDIMIENTO
    
    let extra = 0
    if (velMax.value > 90) {
      extra = (velMax.value - 90) * 0.01 * consumoDistancia
    }
    
    const tiempoRalenti = horasTotales * 0.1
    const consumoRalenti = tiempoRalenti * 0.5
    
    const total = consumoDistancia + extra + consumoRalenti
    return total.toFixed(2)
  }
  return 0
})

const limpiar = () => {
  kilometros.value = 0
  horas.value = 0
  minutos.value = 0
  velMax.value = 0
}
</script>

<template>
  <div class="calculadora">
    <h3>Calculadora de Diesel</h3>
    
    <div class="campo">
      <label>Kilómetros recorridos:</label>
      <input v-model.number="kilometros" type="number" min="0">
    </div>

    <div class="fila">
      <div class="campo">
        <label>Horas:</label>
        <input v-model.number="horas" type="number" min="0" max="24">
      </div>
      <div class="campo">
        <label>Minutos:</label>
        <input v-model.number="minutos" type="number" min="0" max="59">
      </div>
    </div>

    <div class="campo">
      <label>Velocidad máxima (km/h):</label>
      <input v-model.number="velMax" type="number" min="0">
    </div>

    <div v-if="calcularDiesel > 0" class="resultado">
      <strong>Diesel necesario:</strong>
      <div class="valor">{{ calcularDiesel }} galones</div>
    </div>

    <button @click="limpiar" class="boton-limpiar">Limpiar</button>
  </div>
</template>

<style scoped>
.calculadora {
  padding: 15px;
}

h3 {
  color: #333;
  margin-bottom: 15px;
  text-align: center;
}

.campo {
  margin-bottom: 15px;
}

.fila {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}

label {
  display: block;
  color: #555;
  margin-bottom: 5px;
  font-size: 14px;
}

input {
  width: 100%;
  padding: 8px;
  border: 1px solid #ddd;
  border-radius: 4px;
  font-size: 14px;
}

.resultado {
  background-color: #4CAF50;
  color: white;
  padding: 15px;
  border-radius: 5px;
  text-align: center;
  margin: 20px 0;
}

.valor {
  font-size: 24px;
  font-weight: bold;
  margin-top: 5px;
}

.boton-limpiar {
  width: 100%;
  padding: 10px;
  background-color: #f44336;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 14px;
}

.boton-limpiar:hover {
  background-color: #da190b;
}
</style>