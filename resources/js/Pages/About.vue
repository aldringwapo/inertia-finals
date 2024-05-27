<template>
  <div class="about-page">
    <h1>About JB Music Store</h1>
    <section class="intro">
      <p>Welcome to JB Music Store, your ultimate destination for a diverse range of musical instruments and accessories. At JB Music Store, we are committed to bringing you a seamless shopping experience, featuring high-quality items across various categories. Whether you're looking for guitars, keyboards, drums, or accessories, JB Music Store has it all.</p>
    </section>
    
    <section class="categories">
      <h2>Our Categories</h2>
      <ul>
        <li>Guitars</li>
        <li>Keyboards</li>
        <li>Drums</li>
        <li>Accessories</li>
      </ul>
    </section>
    
    <section class="mission">
      <h2>Our Mission</h2>
      <p>At JB Music Store, our mission is to provide our customers with a wide variety of musical instruments and accessories at competitive prices, all while ensuring an enjoyable and hassle-free shopping experience. We carefully curate our product selection to meet the diverse needs and preferences of musicians and enthusiasts.</p>
    </section>

    <section class="commitment">
      <h2>Our Commitment to Quality</h2>
      <p>We prioritize quality in every product we offer. Our dedicated team works tirelessly to source the best items, ensuring that each product meets our high standards of excellence. With JB Music Store, you can shop with confidence, knowing that quality is guaranteed.</p>
    </section>
    
    <section class="customer-service">
      <h2>Exceptional Customer Service</h2>
      <p>Customer satisfaction is our top priority. Our support team is always ready to assist you with any questions or concerns. We strive to make your shopping experience as smooth and enjoyable as possible, from browsing to delivery.</p>
    </section>
  </div>
</template>

<script setup>
import Yourlayout from '@/Layouts/Yourlayout.vue';

defineOptions({
  layout: Yourlayout
});
</script>

<style scoped>
.about-page {
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  font-family: Arial, sans-serif;
  color: white;
  background-color: black; /* Changed background color to black */
}

h1 {
  text-align: center;
  margin-bottom: 20px;
  font-size: 2.5em;
}

section {
  margin-bottom: 30px;
}

h2 {
  font-size: 1.8em;
  margin-bottom: 10px;
}

p {
  font-size: 1.1em;
  line-height: 1.6;
}

ul {
  list-style-type: none;
  padding: 0;
}

ul li {
  background: #ebbebe;
  margin: 5px 0;
  padding: 10px;
  border-radius: 5px;
  color: black;
}
</style>
