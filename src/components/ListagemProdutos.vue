<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';

const produtos = ref([]);

onMounted(async () => {
  const response = await axios.get('https://fakestoreapi.com/products');
  produtos.value = response.data;
});
</script>

<template>
  <div>
    <h1>Produtos</h1>
    <div v-for="produto in produtos" :key="produto.id">
      <h2>{% raw %}{{ produto.title }}{% endraw %}</h2>
      <p>{% raw %}{{ produto.description }}{% endraw %}</p>
      <p>{% raw %}{{ produto.price }}{% endraw %}</p>
      <img :src="produto.image" :alt="produto.title" />
    </div>
  </div>
</template>