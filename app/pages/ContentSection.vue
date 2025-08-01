<template>
  <div class="container mx-auto px-4">
    <div class="flex flex-col md:flex-row gap-4">
      <!-- Bộ lọc bên trái -->
      <aside class="w-full lg:w-1/4">
        <SidebarFilters />
      </aside>

      <!-- Danh sách sản phẩm bên phải -->
      <section
        class="w-full md:w-3/4 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4"
      >
        <div
          v-for="product in products"
          :key="product.id"
          class="border p-4 rounded shadow hover:shadow-md transition"
        >
          <img
            :src="product.image"
            :alt="product.name"
            class="w-full h-48 object-cover mb-2 rounded"
          />
          <h4 class="font-semibold text-lg">{{ product.name }}</h4>
          <p class="text-gray-600">${{ product.price }}</p>
        </div>
      </section>
    </div>
  </div>
</template>

<script setup>
import SidebarFilters from "./FilterSidebar.vue";

const products = [
  {
    id: 1,
    name: "Sofa Nordic Gray",
    price: 1299,
    image: "https://via.placeholder.com/400x300?text=Sofa+1",
  },
  {
    id: 2,
    name: "Sofa Modern White",
    price: 1899,
    image: "https://via.placeholder.com/400x300?text=Sofa+2",
  },
  {
    id: 3,
    name: "Sofa Velvet Green",
    price: 1599,
    image: "https://via.placeholder.com/400x300?text=Sofa+3",
  },
  {
    id: 4,
    name: "Sofa Classic Blue",
    price: 1799,
    image: "https://via.placeholder.com/400x300?text=Sofa+4",
  },
  {
    id: 5,
    name: "Sofa Leather Brown",
    price: 2099,
    image: "https://via.placeholder.com/400x300?text=Sofa+5",
  },
  {
    id: 6,
    name: "Sofa Retro Beige",
    price: 1399,
    image: "https://via.placeholder.com/400x300?text=Sofa+6",
  },
];
</script>

<style scoped>
/* Đảm bảo padding khi mobile */
@media (max-width: 768px) {
  aside {
    order: 2;
  }

  section {
    order: 1;
  }
}
</style>
