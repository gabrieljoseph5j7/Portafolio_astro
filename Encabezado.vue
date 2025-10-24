<<script setup>
const nombre = 'Gabriel Joseph Romero Villalba' 
const carrera = 'Alumno de Segundo Informática' 
const foto = 'https://media.gq.com/photos/6515bae3ce56f476f6886228/16:9/w_2560%2Cc_limit/81156287' 
//https://media.gq.com/photos/6515bae3ce56f476f6886228/16:9/w_2560%2Cc_limit/81156287
//https://images3.memedroid.com/images/UPLOADED141/64cfe0511ed48.jpeg
//https://i.pinimg.com/236x/66/ac/d4/66acd48c800a5dfae78efdf2e076a8e7.jpg
//https://stickerly.pstatic.net/sticker_pack/o3jmpfyHedUf1pyoiyboA/89DR9P/15/474c27ec-9412-4b01-b4fd-7344b1b972cc.png
</script>

<template>
  <div class="encabezado">
    <img :src="foto" :alt="nombre" class="foto-perfil">
    <h1>{{ nombre }}</h1>
    <p>{{ carrera }}</p>
  </div>
</template>

<style scoped>
.encabezado {
  background-color: white;
  padding: 30px;
  text-align: center;
  border-radius: 10px;
  margin-bottom: 20px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

.foto-perfil {
  width: 150px;
  height: 150px;
  border-radius: 50%;
  object-fit: cover;
  margin-bottom: 15px;
  border: 3px solid #4CAF50;
}

h1 {
  color: #333;
  margin-bottom: 5px;
}

p {
  color: #666;
  font-size: 16px;
}
</style>