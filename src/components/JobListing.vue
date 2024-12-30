<script setup>
import { defineProps, ref, computed } from 'vue';

const props = defineProps({
  job: {
    type: Object,
    required: true,
    default: () => ({
      name: '',
      image: '',
      price: 0,
      url: '',
    })
  }
});

</script>

<template>
  <div class="bg-white rounded-xl shadow-md relative">
    <div class="p-4">
      <div class="mb-6">
        <h3 class="text-md font-bold truncate">{{ job.name }}</h3>
      </div>
      <a :href="job.url" target="_blank">
        <img :src="job.image" alt="Job Image" class="mb-2 w-[100%] h-[40%] rounded-lg" />
      </a>

      <h3 class="text-black mb-2"><span class="text-xl font-bold">Free</span> <span class="text-sm font-light">{{ job.sale_price }} of {{ job.price }} $</span></h3>
      <h3 class="text-blue-500 text-sm mb-2"> <span class="truncate">({{ job.rating.toFixed(0) }} ratings)</span>  {{ job.views }} students</h3>
      <a :href="job.url" target="_blank" class="text-black mb-2 inline-block w-full">
        <button class="bg-black text-white px-8 py-2 rounded-lg w-full">
          Go to Course
        </button>
      </a>
    </div>
  </div>
</template>
