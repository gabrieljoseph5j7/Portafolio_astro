<script setup>
import { ref } from 'vue'
import DieselCalculator from './DieselCalculator.vue'

const mostrarCalculadora = ref(false)
</script>

<template>
  <div class="seccion">
    <h2>Mis Proyectos</h2>
    
    <div class="proyecto">
      <h3>Calculadora de Diesel para Camiones</h3>
      <p>Un día el chófer de mi papá vino con el tanque de diesel vacío, lo cual no era común porque recientemente
        gastamos en la gasolinera, le dije a mi papá que me pase los datos del kilometraje del GPS e hice una aplicación 
        con ayuda de GitHub para calcular el gasto de Diesel aproximado en un día, aquí una breve demostración.</p>
      
      <button @click="mostrarCalculadora = !mostrarCalculadora" class="boton">
        {{ mostrarCalculadora ? 'Ocultar' : 'Ver Demo' }}
      </button>

      <div v-if="mostrarCalculadora" class="demo">
        <DieselCalculator />
      </div>

      <div class="codigo">
        <h4>Código en Python:</h4>
        <pre><code>RENDIMIENTO = 4.286  # km por galón

def estimar_diesel(kilometros, horas, minutos, vel_max, rendimiento=RENDIMIENTO):
    # Convertir a horas totales
    horas_totales = horas + (minutos / 60)
    
    # Consumo por distancia
    consumo_distancia = kilometros / rendimiento
    
    # Penalización si va muy rápido
    extra = 0
    if vel_max > 90:
        extra = (vel_max - 90) * 0.01 * consumo_distancia
    
    # Consumo en ralentí
    tiempo_ralenti = horas_totales * 0.1
    consumo_ralenti = tiempo_ralenti * 0.5
    
    consumo_total = consumo_distancia + extra + consumo_ralenti
    return round(consumo_total, 2)

if __name__ == "__main__":
    km_dia = float(input("Ingrese km del día: "))
    horas = int(input("Ingrese horas conducidas: "))
    minutos = int(input("Ingrese minutos conducidos: "))
    vel_max_dia = float(input("Ingrese velocidad máxima del día: "))
    
    diesel_estimado = estimar_diesel(km_dia, horas, minutos, vel_max_dia)
    print(f"\nDiesel estimado para el día: {diesel_estimado} galones")
</code></pre>
      </div>
    </div>
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

.proyecto {
  background-color: #f9f9f9;
  padding: 20px;
  border-radius: 8px;
  margin-top: 15px;
}

h3 {
  color: #333;
  margin-bottom: 10px;
}

p {
  color: #555;
  line-height: 1.6;
  margin-bottom: 15px;
}

.boton {
  background-color: #4CAF50;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
  cursor: pointer;
  font-size: 14px;
  margin-bottom: 15px;
}

.boton:hover {
  background-color: #45a049;
}

.demo {
  margin: 20px 0;
  padding: 15px;
  background-color: white;
  border-radius: 8px;
  border: 2px solid #4CAF50;
}

.codigo {
  margin-top: 20px;
}

h4 {
  color: #333;
  margin-bottom: 10px;
}

pre {
  background-color: #2d2d2d;
  color: #f8f8f2;
  padding: 15px;
  border-radius: 5px;
  overflow-x: auto;
  font-size: 13px;
  line-height: 1.5;
}

code {
  font-family: 'Courier New', monospace;
}
</style>

<style scoped>
.section {
  margin-bottom: 3rem;
}

.card {
  background: white;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 15px rgba(0, 0, 0, 0.2);
}

.section-title {
  color: #667eea;
  font-size: 2rem;
  margin-bottom: 1.5rem;
  border-bottom: 3px solid #667eea;
  padding-bottom: 0.5rem;
}

.project-card {
  background: #f8f9fa;
  border-radius: 8px;
  padding: 1.5rem;
  margin-top: 1rem;
}

.project-title {
  color: #2c3e50;
  font-size: 1.6rem;
  margin-bottom: 1rem;
}

.project-description {
  color: #555;
  font-size: 1.1rem;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.technologies {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.tech-label {
  font-weight: 600;
  color: #2c3e50;
}

.tech-badge {
  background: #667eea;
  color: white;
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
  font-size: 0.9rem;
  font-weight: 500;
}

.features {
  margin-bottom: 1.5rem;
}

.features h4 {
  color: #2c3e50;
  margin-bottom: 0.5rem;
}

.features ul {
  list-style: none;
  padding-left: 0;
}

.features li {
  color: #555;
  padding: 0.3rem 0;
  padding-left: 1.5rem;
  position: relative;
}

.features li::before {
  content: '✓';
  position: absolute;
  left: 0;
  color: #667eea;
  font-weight: bold;
}

.demo-button {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  border: none;
  padding: 0.8rem 2rem;
  border-radius: 25px;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
  margin-bottom: 1rem;
}

.demo-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(102, 126, 234, 0.4);
}

.calculator-container {
  margin: 2rem 0;
  padding: 1.5rem;
  background: white;
  border-radius: 8px;
  border: 2px solid #667eea;
}

.code-section {
  margin-top: 2rem;
}

.code-section h4 {
  color: #2c3e50;
  margin-bottom: 1rem;
}

.code-instruction {
  color: #777;
  font-style: italic;
  margin-bottom: 1rem;
}

.code-block {
  background: #2c3e50;
  color: #a8e6cf;
  padding: 1.5rem;
  border-radius: 8px;
  overflow-x: auto;
  font-family: 'Courier New', monospace;
  font-size: 0.9rem;
  line-height: 1.5;
}

@media (max-width: 768px) {
  .card {
    padding: 1.5rem;
  }

  .section-title {
    font-size: 1.5rem;
  }

  .project-card {
    padding: 1rem;
  }

  .technologies {
    flex-direction: column;
    align-items: flex-start;
  }
}
</style>