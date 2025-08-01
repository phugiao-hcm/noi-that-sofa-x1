<template>
  <div>
    <h4 class="font-semibold text-sm uppercase mb-2">Color</h4>
    <div class="flex flex-wrap gap-2">
      <div
        v-for="(color, idx) in colors"
        :key="idx"
        :title="color.name"
        :style="{ backgroundColor: color.code }"
        class="w-7 h-7 rounded-full border-2 border-white ring-1 ring-gray-300 cursor-pointer"
      />
    </div>
  </div>
</template>

<script setup>
const colors = [
  { name: "Gray", code: "#888" },
  { name: "Brown", code: "#8B5E3C" },
  { name: "Beige", code: "#EDD9A3" },
  { name: "Yellow", code: "#FFE152" },
  { name: "Green", code: "#008000" },
  { name: "Black", code: "#000" },
  { name: "Blue", code: "#4F77C8" },
  { name: "Orange", code: "#FFA500" },
  { name: "White", code: "#F3F3F3" },
  { name: "Red", code: "#990000" },
];
</script>
