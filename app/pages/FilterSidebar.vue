<template>
  <div class="space-y-6 w-full">
    <div
      v-for="(section, index) in filterSections"
      :key="index"
      class="border-b pb-2"
    >
      <div
        class="flex items-center justify-between cursor-pointer mb-2"
        @click="toggleSection(index)"
      >
        <h3 class="font-bold text-lg uppercase">{{ section.title }}</h3>
        <span>▾</span>
      </div>

      <div v-show="section.open">
        <template v-if="section.type === 'checkbox'">
          <div
            v-for="option in section.options"
            :key="option.label"
            class="flex justify-between items-center mb-2"
          >
            <label class="flex items-center gap-2 text-gray-800">
              <input
                type="checkbox"
                class="accent-pink-500"
                v-model="section.model[option.label]"
              />
              {{ option.label }}
            </label>
            <span class="text-gray-500 text-sm">({{ option.count }})</span>
          </div>
        </template>

        <template v-else-if="section.type === 'color'">
          <div class="grid grid-cols-5 gap-2">
            <div
              v-for="(color, idx) in section.options"
              :key="idx"
              :style="{ backgroundColor: color }"
              class="w-8 h-8 rounded-full border-2 border-white shadow cursor-pointer hover:scale-110 transition"
              :class="{
                'ring-2 ring-gray-400': selectedColors.includes(color),
              }"
              @click="toggleColor(color)"
            ></div>
          </div>
        </template>
      </div>
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from "vue";

const selectedColors = ref([]);

function toggleColor(color) {
  const idx = selectedColors.value.indexOf(color);
  if (idx > -1) selectedColors.value.splice(idx, 1);
  else selectedColors.value.push(color);
}

// Data models for checkbox bindings
const brands = reactive({ Stressless: false });
const rooms = reactive({ "Living Room": false });
const types = reactive({
  Sofas: false,
  "Convertible Sofas": false,
  "Sleeper Sofas": false,
  "Power Reclining": false,
  Loveseats: false,
  Daybeds: false,
  "Living Room Chairs": false,
});
const prices = reactive({
  "$250 - $1250": false,
  "$1250 - $2000": false,
  "$2000 - $3000": false,
});

// Full filter config
const filterSections = reactive([
  {
    title: "Brand",
    type: "checkbox",
    open: true,
    model: brands,
    options: [{ label: "Stressless", count: 1 }],
  },
  {
    title: "Room",
    type: "checkbox",
    open: true,
    model: rooms,
    options: [{ label: "Living Room", count: 66 }],
  },
  {
    title: "Type",
    type: "checkbox",
    open: true,
    model: types,
    options: [
      { label: "Sofas", count: 58 },
      { label: "Convertible Sofas", count: 14 },
      { label: "Sleeper Sofas", count: 14 },
      { label: "Power Reclining", count: 12 },
      { label: "Loveseats", count: 8 },
      { label: "Daybeds", count: 4 },
      { label: "Living Room Chairs", count: 1 },
    ],
  },
  {
    title: "Color",
    type: "color",
    open: true,
    options: [
      "#999", // Gray
      "#a17442", // Brown
      "#e6d7a3", // Beige
      "#f7e77a", // Yellow
      "#008000", // Green
      "#000000", // Black
      "#4569aa", // Blue
      "#ff7a00", // Orange
      "#f4f4f4", // White
      "#990000", // Red
    ],
  },
  {
    title: "Price",
    type: "checkbox",
    open: true,
    model: prices,
    options: [
      { label: "$250 - $1250", count: 12 },
      { label: "$1250 - $2000", count: 28 },
      { label: "$2000 - $3000", count: 28 },
    ],
  },
]);

function toggleSection(index) {
  filterSections[index].open = !filterSections[index].open;
}
</script>
