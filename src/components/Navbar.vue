<script setup lang="ts">
import { ref } from 'vue';

interface MenuItem {
  name: string;
  link: string;
}

const menuItems: MenuItem[] = [
  { name: 'Accueil', link: '/' },
  { name: 'À propos', link: '/about' },
  { name: 'Contact', link: '/contact' }
];

const isMenuOpen = ref<boolean>(false);

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value;
};
</script>

<template>
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Mon Menu</a>
        <button class="navbar-toggler" type="button" @click="toggleMenu">
          <span class="navbar-toggler-icon"></span>
        </button>
  
        <div class="collapse navbar-collapse" :class="{ show: isMenuOpen }">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li v-for="item in menuItems" :key="item.name" class="nav-item">
              <a class="nav-link" :href="item.link">{{ item.name }}</a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </template>
  
