<template>
    <div>
        <div v-for="product in products" :key="product.name" class="product-card">
          <div class="product-name">{{ product.name }}</div>
          <div class="product-cost">{{ product.cost }}</div>
          <img :src="product.image" alt="product image"/>
          <button @click="addToCart(product)">Add To Cart</button>
        </div>
    </div>
</template>

<script setup>
import { defineProps, defineEmits } from 'vue';

// Define props
const props = defineProps({
  products: {
    type: Array,
    required: true
  }
});

// Define emits
const emit = defineEmits(['addToCart']);

// Handle the addToCart event
const addToCart = (product) => {
  emit('addToCart', product);
};
</script>

<style lang="scss" scoped>
.product-card {
  /* Add your styles for the product card here */
}
.product-name {
  font-weight: bold;
}
.product-cost {
  color: green;
}
.product-card img {
  width: 100px;
  height: 100px;
}
</style>
