
<!-- 
<script>
  import { ref } from 'vue';

  export default {

    setup() {
      let showMenu = ref(false);
      const toggleNav = () => (showMenu.value = !showMenu.value);
      return { showMenu, toggleNav };
    },
    data() {
      return {
        boton: false,
      };
    },
    methods: {
      mostrar: function () {
        //this.boton = !this.showMenu;
        console.log(this.boton);
      },
    },
  };
</script> -->

<script setup>
  import { ref } from 'vue';
  import Btn from './elements/button.vue'; // Cambiado a Btn para seguir las convenciones de nomenclatura de Vue

  let showMenu = ref(false);
  const toggleNav = () => (showMenu.value = !showMenu.value);

  
</script>

<script>

  export default {
    methods: {
      scrollToSection(sectionId) {
        const section = document.querySelector(sectionId);
        if (section) {
          window.scrollTo({
            top: section.offsetTop,
            behavior: 'smooth' // Efecto de desplazamiento suave
          });
        }
      }
    }
  }

</script>


<template>
  <div class="fixed top-0 w-full z-10">
    <div class="bg-transparent">
      <nav
        class="
          container
          px-6
          py-2
          mx-auto
          md:flex md:justify-between md:items-center
          font-sans font-bold
        "
      >
        <div class="flex items-center justify-between">
          <button @click="scrollToSection('#inicio')"> 
            <img src="../assets/images/logo2.png" alt=""  width="120" height="120"/>
          </button>
          <!-- Mobile menu button -->
          <div @click="toggleNav" class="flex md:hidden">
            <button
              type="button"
              class="
                text-gray-100
                hover:text-gray-400
                focus:outline-none focus:text-gray-400
              "
            >
              <svg viewBox="0 0 24 24" class="w-6 h-6 fill-current">
                <path
                  fill-rule="evenodd"
                  d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z"
                ></path>
              </svg>
            </button>
          </div>
        </div>
  
        <!-- Mobile Menu open: "block", Menu closed: "hidden" -->
        <ul
          :class="showMenu ? 'flex' : 'hidden'"
          class="
            flex-col
            mt-8
            space-y-4
            md:flex md:space-y-0 md:flex-row md:items-center md:space-x-10 md:mt-0
            justify-center 
            text-center
            "
        >
          <button><li class="text-gray-100 hover:text-indigo-400" @click="scrollToSection('#inicio')">Inicio</li></button>
          <button> <li class="text-gray-100 hover:text-indigo-400" @click="scrollToSection('#cursos')">Cursos</li></button>
          <button><li class="text-gray-100 hover:text-indigo-400" @click="scrollToSection('#contacto')">Contacto</li></button>
          <li> <btn/> </li>
        </ul>
      </nav>
    </div>
  </div>
  </template>
  