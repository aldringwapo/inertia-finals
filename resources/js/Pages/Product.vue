<template>
  <div class="container mx-auto py-8 px-4 flex flex-col items-center">
    <head>
      <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/bootstrap-icons/1.8.1/font/bootstrap-icons.min.css">
    </head>
    
    <div class="flex justify-between w-full">
      <h1 class="text-4xl my-6 text-white font-bold">List of Products</h1>
      <Link :href="'/products/create'" class="btn inline-block  font-semibold leading-5 text-white bg-red-600 hover:bg-red-700 rounded-lg mb-6 shadow-lg transition-transform transform hover:scale-105">Create New</Link>
    </div>

    <div class=" flex flex-wrap md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-6 gap-8 justify-items-center">
      <div v-for="product in props.products" :key="product.id" class="card-container">
        <div class="card bg-white shadow-2xl rounded-2xl overflow-hidden transform transition-transform hover:scale-105 hover:shadow-2xl" style="width: 220px; height: 300px;">
          <div class="p-6 relative h-full flex flex-col justify-center items-center">
            <div class="absolute inset-0 bg-gradient-to-r from-red-500 via-red-600 to-red-700 opacity-10 rounded-2xl"></div>
            <div class="relative z-10 flex flex-col justify-center items-center">
              <h2 class="text-2xl font-semibold text-black mt-4">{{ product.name }}</h2>
              <p class="text-gray-700">{{ product.description }}</p>
              <p class="text-gray-700 font-bold mt-2">₱ {{ product.price }}</p>
              <p> {{ getCategoryName(product.category_id) }}</p>
              <Link :href="'/products/' + product.id" class="view-product-btn mt-2">
                <i class="bi bi-box-seam"></i>
              </Link>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { Link } from '@inertiajs/vue3';
import { defineProps } from 'vue';
import Yourlayout from '@/Layouts/Yourlayout.vue';

const props = defineProps({
  products: Array,
  categories: Array,
});

defineOptions({
  layout: Yourlayout
});

// const products = ref(props.products);

// onMounted(async () => {
//   try {
//     // Fetch products data or use the passed props
//   } catch (error) {
//     console.error('Error fetching products:', error);
//   }
// });

const getCategoryName = (id) => {
    const category = props.categories.find(category => category.id === id);
    return category ? category.name : 'Unknown';
};
</script>

<style scoped>
.card {
  background: linear-gradient(45deg, #efdbd4, #e27461);

}
.container {
  background: linear-gradient(45deg, #f16836, #e27461);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1), 0 6px 20px rgba(0, 0, 0, 0.1);
  padding: 20px;
  max-width: 100%;
}

.btn {
  padding: 20px 12px;
  border-radius: 4px;
  color: white;
  text-decoration: none;
  transition: background-color 0.3s ease, transform 0.3s ease;
}

.btn-red {
  background-color: #ff4500;
}

.btn-red:hover {
  background-color: #e60000;
}

.card {
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  border-radius: 20px;
}

.card:hover {
  transform: translateY(-5px);
  box-shadow: 0 15px 25px rgba(0, 0, 0, 0.1);
}

.shadow-2xl {
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1), 0 3px 6px rgba(0, 0, 0, 0.05);
}

.rounded-2xl {
  border-radius: 1.5rem;
}

.overflow-hidden {
  overflow: hidden;
}

.text-gray-700 {
  color: #4a4a4a;
}

.view-product-btn {
  padding: 8px 12px;
  border-radius: 4px;
  background-color: #ff4500;
  color: white;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease;
  text-decoration: none;
  display: inline-block;
}

.view-product-btn:hover {
  background-color: #e60000;
}

.card-container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
