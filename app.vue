<template>
  <div class="p-4">
    <h1 class="text-2xl font-bold text-center mb-6">Electric Categories</h1>
    <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
      <div
        v-for="category in categories"
        :key="category._id"
        class="bg-white shadow rounded overflow-hidden"
      >
        <img
          :src="category.img"
          :alt="category.name"
          class="w-full h-40 object-cover"
        />
        <div class="p-4">
          <h2 class="text-lg font-semibold">{{ category.name }}</h2>
          <p class="text-gray-600 text-sm">{{ category.description }}</p>
          <p class="text-green-600 font-bold mt-2">Price: ${{ category.price }}</p>
          <p class="text-gray-600 text-sm">Supplier: {{ category.supplier }}</p>
          <p class="text-gray-600 text-sm">Quantity: {{ category.quantity }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
const { data: categoriesData } = await useFetch(
  'https://laptop-warehouse-management-server-side.onrender.com/product'
);
const categories = categoriesData.value || [];
</script>
