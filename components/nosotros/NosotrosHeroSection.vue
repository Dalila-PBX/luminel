<script setup lang="ts">
import { nosotrosData } from '@/data/nosotros';
</script>


<template>
   <section>
    <div
      class="container-fluid section-nosotros position-relative d-flex justify-content-center align-items-center"
      :style="{ backgroundImage: `url(${nosotrosData.nosotros.bgDesktop})` }"
    >
      <!-- Capa 1: Fondo intermedio (Sandwich) -->
      <!-- w-100 h-100 para que ocupe todo el espacio disponible-->
      <div
        class="carrusel-sandwich position-absolute w-100 h-100"
        :style="{ backgroundImage: `url(${nosotrosData.nosotrosBackground})` }"
      ></div>

      <!-- Capa 2: Imagen más pequeña (Recuadro) -->
      <div
        class="content-layer position-absolute"
        :style="{ backgroundImage: `url(${nosotrosData.nosotros.imgRecuadro})` }"
      ></div>

      <!-- Capa 3: Contenido de Texto -->
      <div class="text-content text-center position-relative"
            v-motion-slide-visible-top
            :delay="200"
            :duration="1200">
        <h1 class="fw-bold text-uppercase mb-lg-2 mb-0 nosotros-title pb-lg-3 pb-0"

        >Nosotros</h1>
        <p class="mx-auto nosotros-text"  style="max-width: 800px">
          En Lúminel Agencia Creativa, creemos que el diseño va más allá de lo visual: es una
          herramienta estratégica que conecta, comunica y construye marcas sólidas.
        </p>
      </div>
    </div>
  </section>

</template>


<style scoped>

  .section-nosotros {
  min-height: 80vh; /* Asegura que ocupe al menos toda la altura de la pantalla */
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  overflow: hidden;
}

.carrusel-sandwich {
  background-size: contain;
  background-position: center center;
  background-repeat: no-repeat;
  z-index: 1;
  pointer-events: none;
}

.content-layer {
  z-index: 2;
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
  width: 80%;
  height: 100%;
  top: 40%;
  left: 50%;
  transform: translate(-50%, -50%);
  pointer-events: none;
}

.text-content {
  z-index: 3; /* Encima de todas las imágenes */
  color: white; /* Asumiendo que el fondo es oscuro */

}

.nosotros-title{
  font-family: 'Work Sans', sans-serif;
  font-size: clamp(2.4rem, 6vw, 4.5rem);
}

.nosotros-text{
  font-family: 'Work Sans', sans-serif;
  font-size: clamp(.9rem, 2.5vw, 1.1rem);
  width: 60%;

}

/* Ajuste para móviles si la imagen del recuadro se ve muy pequeña */
@media (max-width: 768px) {

  .section-nosotros{
    min-height: 70vh;
    margin-top: -70px;
  }
  .content-layer {
    width: 150%;
    height: 80%;
  }
  .nosotros-text{
    width: 70%;
  }
}

@media (max-width: 992px){
  .section-nosotros{
    margin-top: -70px;
  }
}

</style>

