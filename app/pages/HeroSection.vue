<template>
    <section class="relative h-[500px] md:h-[600px] overflow-hidden">
        <!-- Ảnh nền -->
        <img
            src="/images/hero.png"
            alt="Sofa Collection"
            class="absolute inset-0 w-full h-full object-cover"
        />

        <!-- Lớp phủ -->
        <div class="absolute inset-0 bg-black/50"></div>

        <!-- Nội dung -->
        <div
            class="relative z-10 h-full flex flex-col items-center justify-center text-white text-center px-4"
        >
            <h1 class="text-3xl md:text-5xl font-bold mb-4">
                Sofa Collection 2025
            </h1>
            <p class="text-base md:text-xl mb-6">
                Sự thoải mái lấy cảm hứng từ Sofa Phú Giáo cho cuộc sống hiện
                đại của bạn
            </p>
            <NuxtLink
                to="/"
                class="bg-amber-500 hover:bg-amber-600 px-6 py-3 rounded-full text-white font-medium transition"
            >
                Xem bộ sưu tập
            </NuxtLink>
        </div>
    </section>
</template>
