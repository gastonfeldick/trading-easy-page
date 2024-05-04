<script setup>
  import Btn from './elements/button.vue'; // Cambiado a Btn para seguir las convenciones de nomenclatura de Vue
</script>
<template>
    <section id="inicio">
        <div class="flex justify-center items-center h-screen flex-col font-serif">
            <h1 class="text-white text-6xl italic">"Es hora de convertir</h1>
            <h1 class="text-white text-6xl italic">al trading en algo</h1>
            <h1 class="text-white text-6xl italic">sencillo"</h1>
            <div class="mt-20"><Btn/></div>
        </div>

        
    </section>
</template>
  
  <script>
  export default {
    // Componente de la sección de inicio
  }
  </script>
  
  <style>
  /* Estilos de la sección de inicio */
  </style>
  