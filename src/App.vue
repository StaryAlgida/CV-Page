<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
import { ref, watch } from 'vue'

const side = ref(0)
const defaultStyle = ref('menu-links menu-font-size')
const selectedStyle = ref('menu-links menu-font-size selected')

watch(side, () => {})
</script>

<template>
  <header>
    <div id="menu" class="menu-font-size">MENU</div>
    <div class="wrapper">
      <nav>
        <div class="menu-item">
          <RouterLink @click="side = 0" :class="side === 0 ? selectedStyle : defaultStyle" to="/"
            >HOME</RouterLink
          >
        </div>
        <div class="menu-item">
          <RouterLink
            @click="side = 1"
            :class="side === 1 ? selectedStyle : defaultStyle"
            to="/about"
            >ABOUT</RouterLink
          >
        </div>

        <div class="menu-item">
          <RouterLink
            @click="side = 2"
            :class="side === 2 ? selectedStyle : defaultStyle"
            to="/resume"
            >RESUME</RouterLink
          >
        </div>
        <div class="menu-item">
          <RouterLink
            @click="side = 3"
            :class="side === 3 ? selectedStyle : defaultStyle"
            to="/projects"
            >PROJECTS</RouterLink
          >
        </div>
      </nav>
    </div>
  </header>
  <div class="container">
    <aside>
      <a href="https://github.com/StaryAlgida"
        ><img src="../images/github.svg" alt="GitHub" srcset=""
      /></a>
      <a href="https://www.linkedin.com/in/piotr-wawrze%C5%84czyk-6aa15a262/"
        ><img src="../images/linkedin.svg" alt="GitHub" srcset=""
      /></a>
    </aside>
    <RouterView />
  </div>
</template>
