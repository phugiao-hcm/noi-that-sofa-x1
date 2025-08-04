<template>
    <div class="max-w-7xl mx-auto px-4">
        <!-- Tiêu đề -->
        <h2 class="text-2xl font-bold mt-8 mb-4">Sofa nổi bật</h2>
        <p class="text-gray-600 mb-6">
            Khám phá các mẫu sofa được ưa chuộng và phù hợp mọi không gian.
        </p>

        <div class="flex flex-col md:flex-row gap-6">
            <section class="w-full">
                <div
                    class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6"
                >
                    <div
                        v-for="product in products"
                        :key="product.id"
                        class="p-4 rounded shadow hover:shadow-lg transition"
                    >
                        <img
                            :src="product.image"
                            :alt="product.name"
                            class="w-full h-48 object-cover mb-3 rounded"
                        />
                        <h4 class="font-semibold text-lg">
                            {{ product.name }}
                        </h4>
                        <p class="text-red-600 font-bold">
                            {{ product.price }}đ
                        </p>
                    </div>
                </div>
            </section>
        </div>
    </div>
</template>

<script setup>
const products = [
    {
        id: 1,
        name: "Sofa Nordic Gray",
        price: "12.700.000",
        image: "images/1.png",
    },
    {
        id: 2,
        name: "Sofa Modern White",
        price: "12.700.000",
        image: "images/2.png",
    },
    {
        id: 3,
        name: "Sofa Velvet Green",
        price: "4.700.000",
        image: "images/3.png",
    },
    {
        id: 4,
        name: "Sofa Classic Blue",
        price: "2.700.000",
        image: "images/4.png",
    },
    {
        id: 5,
        name: "Sofa Leather Brown",
        price: "1.300.000",
        image: "images/5.png",
    },
    {
        id: 6,
        name: "Sofa Retro Beige",
        price: "2.200.000",
        image: "images/6.png",
    },
];
</script>

<style scoped>
@media (max-width: 768px) {
    aside {
        order: 2;
    }
    section {
        order: 1;
    }
}
</style>
