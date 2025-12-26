<script setup lang="ts">
import { ref } from 'vue';

// Datos de ejemplo para los proyectos. Puedes mover esto a tu archivo de datos.
const portfolioItems = ref([
  {
    id: 1,
    title: 'Web Design',
    category: 'Mobile / Design / Rebranding',
    imgSrc:
      '/img/branding/tarjeta1.png',
    link: '#',
  },
  {
    id: 2,
    title: 'UX Design',
    category: 'UX / UI / Research',
    imgSrc:
      '/img/branding/tarjeta2.png',
    link: '#',
  },
  {
    id: 3,
    title: 'Concepts',
    category: 'Design / Creative',
    imgSrc:
      '/img/branding/tarjeta3.png',
    link: '#',
  },
  {
    id: 4,
    title: 'Creative & Cool',
    category: 'Design / Food',
    imgSrc:
      '/img/branding/tarjeta4.png',
    link: '#',
  },
  {
    id: 5,
    title: 'AR-VR',
    category: 'VR / AR / Creative',
    imgSrc:
      '/img/branding/tarjeta5.png',
    link: '#',
  },
  {
    id: 6,
    title: 'Logo',
    category: 'Design / Logo / Clothing',
    imgSrc:
      '/img/branding/tarjeta6.png',
    link: '#',
  },
  {
    id: 6,
    title: 'Logo',
    category: 'Design / Logo / Clothing',
    imgSrc:
      '/img/branding/tarjeta7.png',
    link: '#',
  },
  {
    id: 6,
    title: 'Logo',
    category: 'Design / Logo / Clothing',
    imgSrc:
      '/img/branding/tarjeta8.png',
    link: '#',
  },
  {
    id: 6,
    title: 'Logo',
    category: 'Design / Logo / Clothing',
    imgSrc:
      '/img/branding/tarjeta9.png',
    link: '#',
  },
  {
    id: 6,
    title: 'Logo',
    category: 'Design / Logo / Clothing',
    imgSrc:
      '/img/branding/tarjeta10.png',
    link: '#',
  },
]);
</script>

<template>
  <section class="portfolio-section bg-white py-0">
    <div class="container-fluid m-0 p-0">


      <!-- Contenedor de las tarjetas del portafolio -->
      <div class="row g-0">
        <!-- Usamos v-for para crear dinámicamente cada tarjeta -->
        <div
          v-for="item in portfolioItems"
          :key="item.id"
          class="col-12 col-md-6  "
        >
          <a :href="item.link" class="portfolio-card position-relative overflow-hidden d-block">
            <!-- Contenido de texto que aparece en hover -->
            <div
              class="card-content position-absolute w-100 d-flex flex-column align-items-center p-4 bg-dark"
            >
              <span class="fs-6 text-white text-uppercase fw-bold mb-2 text-center">{{
                item.title
              }}</span>
              <span class="category-text small fw-bold text-center">{{ item.category }}</span>
            </div>
            <!-- Imagen de fondo de la tarjeta -->
            <div class="card-image h-100">
              <img :src="item.imgSrc" :alt="item.title" class="w-100 h-100" />
            </div>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.portfolio-card {
  height: 600px; /* Altura fija para las tarjetas */
}
.card-content {
  z-index: 2;
  bottom: -150px; /* Oculto por defecto, ajusta si es necesario */
  transition: bottom 0.5s ease-in-out;
  min-height: 100px;
}
.portfolio-card:hover .card-content {
  bottom: 0;
}
.card-image img {
  object-fit: cover; /* Evita que la imagen se deforme */
  transform: scale(1.2);
  transition: transform 0.5s ease-in-out;
}
.portfolio-card:hover .card-image img {
  transform: scale(1);
}
.category-text {
  color: #18cfab; /* Color personalizado para la categoría */
}



/* En pantallas pequeñas, el contenido es visible por defecto para mejorar la UX en móvil */
@media (max-width: 768px) {
  .portfolio-card {
  height: 400px; /* Altura fija para las tarjetas */
  }
  .card-content {
    bottom: 0;
    background-color: rgba(0, 0, 0, 0.6); /* Fondo semi-transparente */
  }
  .portfolio-card:hover .card-image img {
    transform: scale(1.2); /* Desactivamos el zoom-out en móvil */
  }
}
</style>
