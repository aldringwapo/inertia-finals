<template>
    <div class="shop-container">
      <h1>Categories</h1>
      <div class="categories">
        <div class="category" @click="filterProducts('Mobile')">DRUMS</div>
        <div class="category" @click="filterProducts('Tshirt')">GUITAR</div>
        <div class="category" @click="filterProducts('Tablet')">KEYBOARD</div>
      </div>
      <div class="product-grid">
        <div class="product-card" v-for="product in filteredProducts" :key="product.id">
          <div class="product-content">
            <img :src="product.image" :alt="product.name" class="product-image"/>
            <div class="product-details">
              <p class="product-name">{{ product.name }}</p>
            </div>
          </div>
          <button class="buy-now-button">Buy Now</button>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import Yourlayout from '@/Layouts/Yourlayout.vue';
  
  defineOptions({
    layout: Yourlayout
  });
  
  const products = [
    { id: 1, name: "DW DRUMS", price: "₱70K", image: "https://www.ubuy.com.ph/productimg/?image=aHR0cHM6Ly9tLm1lZGlhLWFtYXpvbi5jb20vaW1hZ2VzL0kvNjFQa2ZDOE9VM0wuX0FDX1NMMTAwMF8uanBn.jpg", category: "Mobile" },
    { id: 2, name: "GRETCH", price: "₱40K", image: "https://media.sweetwater.com/m/products/image/07dd4d8748ObPuww3w9oRhbRzOufv20jllgfCyVF.jpg?quality=82&width=750&ha=07dd4d8748681420", category: "Mobile" },
    { id: 3, name: "FENDER", price: "₱50K", image: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTGD8jR_l50ejJZyRSv1gRNHXIvfzoISbu7xPKryUERxnkSKFdHlnxsB7j6x1TjFXkdTHE&usqp=CAU", category: "Tshirt" },
    { id: 4, name: "J CRAFT", price: "₱70K", image: "https://down-ph.img.susercontent.com/file/sg-11134201-7rbk7-lplrs7ai16fv8e_tn.webp", category: "Tshirt" },
    { id: 5, name: "XPS 30 ", price: "₱50K", image: "https://down-ph.img.susercontent.com/file/sg-11134201-22120-op2tzd41hflv21", category: "Tablet" },
    { id: 6, name: "YAMAHA", price: "₱60K", image: "https://img.lazcdn.com/g/p/33adcfd3e6d1022380950a2ed5ac8cc1.jpg_720x720q80.jpg", category: "Tablet" },
  ];
  
  const selectedCategory = ref(null);
  
  const filteredProducts = ref([]);
  
  const filterProducts = (category) => {
    selectedCategory.value = selectedCategory.value === category ? null : category;
    filteredProducts.value = selectedCategory.value ? products.filter(product => product.category === selectedCategory.value) : products;
  };
  </script>
  
  
  <style scoped>

h1 {
    font-size: 40px;
    color: #333; 
    margin-bottom: 50px;
  }
  
  .shop-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 20px;
    font-size: 32px; 
    color: #000000; 
    margin-bottom: 20px; 
  }
  
  .categories {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
  }
  
  .category {
    padding: 10px 20px;
    margin: 0 10px;
    border-radius: 5px;
    background-color: #f0f0f0;
    font-weight: bold;
  }
  
  .product-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr); /* Change this line */
  gap: 20px;
  max-width: 1200px;
  align-items: center;
}


  
  .product-card {
    position: relative; /* Set position relative to contain absolute child */
    background: #fff;
    border-radius: 15px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
    transition: transform 0.3s, box-shadow 0.3s;
    overflow: hidden;
    text-align: center;
    padding: 20px;
    margin: auto; /* Center the product card */
    width: 200px; /* Set a fixed width for the product card */
    height: 300px; /* Set a fixed height for the product card */
  }
  
  .product-card:hover {
    transform: translateY(-10px);
    box-shadow: 0 8px 16px rgba(0, 0, 0, 0.3);
  }
  
  .product-content {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    height: 100%; /* Fill the height of the product card */
  }
  
  .product-image {
    width: 100%;
    height: auto;
    border-bottom: 1px solid #ddd;
    margin-bottom: 20px;
  }
  
  .product-details {
    margin-bottom: 20px;
  }
  
  .product-name {
    font-size: 24px;
    font-weight: bold;
    color: #333;
    margin: 0 0 50px;
  }
  
  .product-price {
    font-size: 20px;
    color: #ff8a00;
    margin: 0;
  }
  
  .buy-now-button {
    position: absolute; /* Position the button absolutely */
    bottom: 20px; /* Adjust the distance from the bottom */
    left: 50%; /* Align the button to the center horizontally */
    transform: translateX(-50%); /* Adjust for center alignment */
    background: linear-gradient(90deg, #ff8a00, #e52e71);
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 25px;
    font-size: 16px;
    cursor: pointer;
    transition: background 0.3s;
    width: 80%; /* Set a width for the button */
  }
  
  .buy-now-button:hover {
    background: linear-gradient(90deg, #e52e71, #ff8a00);
  }
  </style>
  