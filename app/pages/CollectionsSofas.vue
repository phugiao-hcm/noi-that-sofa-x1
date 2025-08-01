<template>
  <section class="py-10 px-4">
    <h1 class="text-4xl font-bold mb-6 text-center">Danh sách Sofa</h1>

    <div
      class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6"
    >
      <div
        v-for="product in products"
        :key="product.id"
        class="bg-white rounded shadow hover:shadow-lg transition"
      >
        <img
          :src="product.image"
          :alt="product.name"
          class="w-full h-64 object-cover rounded-t"
        />
        <div class="p-4">
          <h2 class="text-lg font-semibold mb-2">{{ product.name }}</h2>
          <p class="text-gray-600 mb-2">{{ product.description }}</p>
          <p class="text-blue-600 font-bold text-xl">{{ product.price }}</p>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const products = [
  {
    id: 1,
    name: "Sofa Góc Hiện Đại",
    image: "/images/sofa1.jpg",
    description: "Chất liệu vải cao cấp, thoải mái.",
    price: "12.500.000đ",
  },
  {
    id: 2,
    name: "Sofa Da Thật Cao Cấp",
    image: "/images/sofa2.jpg",
    description: "Thiết kế sang trọng, dễ lau chùi.",
    price: "18.900.000đ",
  },
  {
    id: 3,
    name: "Sofa Đơn Tối Giản",
    image: "/images/sofa3.jpg",
    description: "Phù hợp phòng nhỏ, phong cách Bắc Âu.",
    price: "6.700.000đ",
  },
  {
    id: 4,
    name: "Sofa Giường Đa Năng",
    image: "/images/sofa4.jpg",
    description: "Có thể gập thành giường khi cần.",
    price: "9.800.000đ",
  },
  {
    id: 5,
    name: "Sofa L Chữ Sang Trọng",
    image: "/images/sofa5.jpg",
    description: "Dành cho phòng khách lớn, thoải mái.",
    price: "22.000.000đ",
  },
  {
    id: 6,
    name: "Sofa Gỗ & Nệm Vải",
    image: "/images/sofa6.jpg",
    description: "Sự kết hợp giữa cổ điển và hiện đại.",
    price: "14.500.000đ",
  },
  // ... thêm sản phẩm nếu muốn
];
</script>

<style scoped>
body {
  background-color: #f7f7f7;
}
</style>
