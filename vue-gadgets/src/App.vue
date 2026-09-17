<script setup>
import ProductList from './components/ProductList.vue';
import {ref} from 'vue'

const items = ref([
    {
        "id": 1,
        "title": "Apple Watch Series 7 синий",
        "price": 34990,
        "imageUrl": "/product1.png"
    },
    {
        "id": 2,
        "title": "Beats Studio3 Wireless черный",
        "price": 25000,
        "imageUrl": "/product2.png"
    },
    {
        "id": 3,
        "title": "Sony PlayStation 4 Slim черный",
        "price": 30000,
        "imageUrl": "/product3.png"
    },
    {
        "id": 4,
        "title": "Sony PlayStation 5 Slim черный",
        "price": 30000,
        "imageUrl": "/product3.png"
    },
    {
        "id": 5,
        "title": "Sony PlayStation 3 Slim черный",
        "price": 30000,
        "imageUrl": "/product3.png"
    },
    {
        "id": 6,
        "title": "Sony PlayStation 2 Slim черный",
        "price": 30000,
        "imageUrl": "/product3.png"
    },
    {
        "id": 7,
        "title": "Sony PlayStation 1 черный",
        "price": 30000,
        "imageUrl": "/product3.png"
    },
    {
        "id": 8,
        "title": "Sony PlayStation 4 pro черный",
        "price": 30000,
        "imageUrl": "/product3.png"
    },
    {
        "id": 9,
        "title": "Sony PlayStation 6 черный",
        "price": 30000,
        "imageUrl": "/product3.png"
    },
])

</script>


<template>
  <div class="mx-auto w-[1440px] mb-25">
    <nav class="py-3 border-b border-b-slate-200">
      <div class="flex items-center justify-between">
        <div class="flex items-center gap-3">
          <img src="/logo.svg" alt="Логотип">
          <p class="text-sm">
            Лучшие цены <br> в интернет-магазинах
          </p>
        </div>
        <ul class="flex gap-10">
          <li>
            <a href="#" class="flex gap-3 items-center">
              <span class="p-3.5 rounded-xl bg-slate-100 hover:bg-slate-200 transition">
                <img src="/cart-icon.svg" alt="Корзина">
              </span>
              Корзина
            </a>
          </li>
        </ul>
      </div>
    </nav>
    
    <main class="pt-10">
      <h1 class="text-[40px] font-bold mb-5">Каталог</h1>
      <div class="grid grid-cols-5 gap-5">
        <product-list :items="items"></product-list>
      </div>
    </main>
  </div>    
    
  <footer class="p-6 bg-slate-100">
    <div class="text-center text-slate-500">
      Copyright &copy; 2023
    </div>
  </footer>
</template>

<script setup>
import { onMounted, ref } from "vue";
import axios from "axios";

import logo from "@/assets/logo.svg";
import cartIcon from "@/assets/cart-icon.svg";
import ProductList from "./components/ProductList.vue";

const items = ref([]);
const fetchItems = async () => {
    try {
        const { data } = await axios.get(
            "https://99bd51eed5613d1e.mokky.dev/items"
        );
        items.value = data.map((obj) => ({
            ...obj,
            isFavorite: false,
            isAdded: false,
        }));
    } catch (e) {
        console.log(e);
    }
};
onMounted(async () => {
    await fetchItems();
});
</script>


<template>
  <div class="mx-auto w-[1440px] mb-25">
    <nav class="py-3 border-b border-b-slate-200">
      <div class="flex items-center justify-between">
        <div class="flex items-center gap-3">
          <img :src="logo" alt="Логотип">
          <p class="text-sm">
            Лучшие цены <br> в интернет-магазинах
          </p>
        </div>
        <ul class="flex gap-10">
          <li>
            <a href="#" class="flex gap-3 items-center">
              <span class="p-3.5 rounded-xl bg-slate-100 hover:bg-slate-200 transition">
                <img :src="cartIcon" alt="Корзина">
              </span>
              Корзина
            </a>
          </li>
        </ul>
      </div>
    </nav>
    
    <main class="pt-10">
      <h1 class="text-[40px] font-bold mb-5">Каталог</h1>
      <div class="grid grid-cols-5 gap-5">
        <product-list :items="items"></product-list>
      </div>
    </main>
  </div>    
    
  <footer class="p-6 bg-slate-100">
    <div class="text-center text-slate-500">
      Copyright &copy; 2023
    </div>
  </footer>
</template>