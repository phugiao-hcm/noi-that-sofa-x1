<template>
  <header class="bg-white shadow-sm sticky top-0 z-50">
    <div class="max-w-7xl mx-auto px-4 py-3 flex items-center justify-between">
      <!-- Logo -->
      <router-link to="/" class="text-xl font-bold text-gray-800">
        <img src="/images/1.png" alt="Logo" class="h-8" />
      </router-link>

      <!-- Navigation -->
      <nav class="hidden md:flex items-center gap-6">
        <router-link
          v-for="(item, index) in navItems"
          :key="index"
          :to="item.href"
          class="text-gray-700 hover:text-black transition"
        >
          {{ item.label }}
        </router-link>
      </nav>

      <!-- Mobile Menu Button -->
      <button class="md:hidden" @click="toggleMobileMenu">
        <svg
          class="h-6 w-6 text-gray-800"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16M4 18h16"
          />
        </svg>
      </button>
    </div>

    <!-- Mobile Menu -->
    <transition name="fade">
      <div v-if="showMobileMenu" class="md:hidden bg-white px-4 pb-4">
        <router-link
          v-for="(item, index) in navItems"
          :key="index"
          :to="item.href"
          class="block py-2 text-gray-700 hover:text-black transition"
          @click="toggleMobileMenu"
        >
          {{ item.label }}
        </router-link>
      </div>
    </transition>
  </header>
</template>

<script setup>
import { ref } from "vue";

const showMobileMenu = ref(false);
const toggleMobileMenu = () => {
  showMobileMenu.value = !showMobileMenu.value;
};

const navItems = [
  { label: "Trang chủ", href: "/" },
  { label: "Sản phẩm", href: "/products" },
  { label: "Về chúng tôi", href: "/about" },
  { label: "Liên hệ", href: "/contact" },
];
</script>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
