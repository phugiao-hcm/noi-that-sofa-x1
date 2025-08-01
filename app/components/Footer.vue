<template>
  <footer class="bg-neutral-900 text-white py-10">
    <div class="container mx-auto px-4 grid grid-cols-1 md:grid-cols-4 gap-8">
      <!-- Logo + About -->
      <div>
        <h2 class="text-xl font-semibold mb-3">ScandiHome</h2>
        <p class="text-sm text-neutral-300">
          Scandinavian inspired furniture and home décor. Modern, minimal, and
          made for you.
        </p>
      </div>

      <!-- Quick Links -->
      <div>
        <h3 class="text-lg font-medium mb-2">Quick Links</h3>
        <ul class="space-y-1 text-sm text-neutral-400">
          <li><a href="#" class="hover:underline">Home</a></li>
          <li><a href="#" class="hover:underline">Shop</a></li>
          <li><a href="#" class="hover:underline">Sofas</a></li>
          <li><a href="#" class="hover:underline">Contact</a></li>
        </ul>
      </div>

      <!-- Customer Service -->
      <div>
        <h3 class="text-lg font-medium mb-2">Customer Service</h3>
        <ul class="space-y-1 text-sm text-neutral-400">
          <li><a href="#" class="hover:underline">FAQ</a></li>
          <li><a href="#" class="hover:underline">Shipping & Returns</a></li>
          <li><a href="#" class="hover:underline">Privacy Policy</a></li>
          <li><a href="#" class="hover:underline">Terms of Service</a></li>
        </ul>
      </div>

      <!-- Newsletter -->
      <div>
        <h3 class="text-lg font-medium mb-2">Stay Updated</h3>
        <p class="text-sm text-neutral-300 mb-3">Subscribe to our newsletter</p>
        <form @submit.prevent class="flex flex-col space-y-2">
          <input
            type="email"
            placeholder="Your email"
            class="px-3 py-2 rounded text-black"
          />
          <button
            type="submit"
            class="bg-white text-black px-3 py-2 rounded hover:bg-neutral-200"
          >
            Subscribe
          </button>
        </form>
      </div>
    </div>

    <!-- Bottom line -->
    <div
      class="mt-10 border-t border-neutral-700 pt-5 text-center text-sm text-neutral-400"
    >
      &copy; 2025 ScandiHome. All rights reserved.
    </div>
  </footer>
</template>
