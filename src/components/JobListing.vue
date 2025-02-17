<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  item: {
    type: Object,
    required: true,
    default: () => ({
      name: '',
      image: '',
      price: 0,
      sale_price: 0,
      url: '',
      rating: 0,
      views: 0
    })
  }
});
</script>

<template>
  <div class="bg-white rounded-xl shadow-md relative">
    <div class="p-4">
      <div class="mb-6">
        <h3 class="text-black hover:text-primary text-xs font-bold truncate">{{ item.name }}</h3>
      </div>
      <a :href="item.url" target="_blank">
        <img :src="item.image" alt="item Image" class="mb-2 w-full h-[40%] rounded-lg" />
      </a>
      <h3 class="text-black mb-2">
        <span class="text-xl font-bold">Free</span>
        <span class="text-sm font-light">{{ item.sale_price }} of {{ item.price }} $</span>
      </h3>
      <h3 class="text-blue-500 text-sm mb-2">
        <span class="truncate">({{ item.rating?.toFixed(0) || 0 }} ratings)</span>
        {{ item.views }} students
      </h3>
      <a :href="item.url" target="_blank" class="text-black mb-2 inline-block w-full">
        <button class="bg-black hover:bg-primary text-white hover:text-black px-8 py-2 rounded-lg w-full">
          Go to Course
        </button>
      </a>
    </div>
  </div>
</template>
