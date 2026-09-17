<script setup>
import { onMounted, ref } from "vue";
import axios from "axios";
import ProductList from "./components/ProductList.vue";
import logo from "/logo.svg";



const items = ref([]);
const fetchItems = async () => {
    try {
        const { data } = await axios.get(
            "https://1201a231a73088af.mokky.dev/products"
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
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M12 21.65C11.69 21.65 11.39 21.61 11.14 21.52C7.32 20.21 1.25 15.56 1.25 8.69C1.25 5.19 4.08 2.35 7.56 2.35C9.25 2.35 10.83 3.01 12 4.19C13.17 3.01 14.75 2.35 16.44 2.35C19.92 2.35 22.75 5.2 22.75 8.69C22.75 15.57 16.68 20.21 12.86 21.52C12.61 21.61 12.31 21.65 12 21.65ZM7.56 3.85C4.91 3.85 2.75 6.02 2.75 8.69C2.75 15.52 9.32 19.32 11.63 20.11C11.81 20.17 12.2 20.17 12.38 20.11C14.68 19.32 21.26 15.53 21.26 8.69C21.26 6.02 19.1 3.85 16.45 3.85C14.93 3.85 13.52 4.56 12.61 5.79C12.33 6.17 11.69 6.17 11.41 5.79C10.48 4.55 9.08 3.85 7.56 3.85Z" fill="#263141"/>
</svg>

          <p class="text-sm">
            Лучшие цены <br> в интернет-магазинах
          </p>
        </div>
        <ul class="flex gap-10">
          <li>
            <a href="#" class="flex gap-3 items-center">
              <span class="p-3.5 rounded-xl bg-slate-100 hover:bg-slate-200 transition">
<svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M15.5 19L8.5 12L15.5 5" stroke="#7E8794" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
</svg>
              </span>
              Корзина
            </a>
          </li>
        </ul>
      </div>
    </nav>
    
    <main class="pt-10">
      <h1 class="text-[40px] font-bold mb-5">Каталог</h1>
        <product-list :items="items"></product-list>
    </main>
  </div>    
    
  <footer class="p-6 bg-slate-100">
    <div class="text-center text-slate-500">
      Copyright &copy; 2023
    </div>
  </footer>
</template>