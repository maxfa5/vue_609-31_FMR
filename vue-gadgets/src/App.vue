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
          <img
          src="/logo.svg"
          />

          <p class="text-sm">
            Лучшие цены <br> в интернет-магазинах
          </p>
        </div>
        <ul class="flex gap-10">
          <li>
            <a href="#" class="flex gap-3 items-center">
              <span class="p-3.5 rounded-xl bg-slate-100 hover:bg-slate-200 transition">
              <img
          src="/cart-icon.svg"
          />
              </span>
              Корзина
            </a>
          </li>
                    <li>
            <a href="#" class="flex gap-3 items-center">
              <span class="p-3.5 rounded-xl bg-slate-100 hover:bg-slate-200 transition">
                <img
          src="/like-outline.svg"
          />
              </span>
              Избранное
            </a>
          </li>
                    <li>
            <a href="#" class="flex gap-3 items-center">
              <span class="p-3.5 rounded-xl bg-slate-100 hover:bg-slate-200 transition">
                <img
          src="/orders-icon.svg"
          />
              </span>
              Заказы
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