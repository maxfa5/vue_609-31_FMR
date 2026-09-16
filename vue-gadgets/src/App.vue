<template>
  <body>
    <div class="mx-auto w-[1440px] mb-25">
      <nav class="py-3 border-b border-b-slate-200">
        <div class="flex items-center justify-between">
          <div class="flex items-center gap-3">
            <img src="/vue-gadgets/public/logo (1).svg" alt="">
            <p class="text-sm">
              Лучшие цены <br> в интернет-магазинах
            </p>
          </div>
          <ul class="flex gap-10">
            <li>
              <a href="" class="flex gap-3 items-center"></a>
              <span class="p-3 5 rounded-xl bg-slate-100 hover:bg-slate-200 transition">
              <img src="/vue-gadgets/public/cart-icon (1).svg" alt="">

              </span>
              Корзина
            </li>
          </ul>
        </div>
      </nav>
      <main class="pt-10">
        <h1 class="text-[40px] font-bold mb-5">Каталог</h1>
        <div class="grid grid-cols-5 gap-5">
        <div class="p-5 bg-slate-100 rounded-xl flex flex-col justify-between gap-2">
          <div>
            <img src="/vue-gadgets/public/product-1 (1).png"
              class="mb-4"
              alt=""/>
            <h3 class="text-xl font-semibold">
              Apple Watch 3 pro 7 синий
            </h3>
          </div>
          <div class="flex items-center justify-between gap-2"></div>
          <div>
            <p class="text-late-500">Цена</p>
            <b class="text-xl">34 900 Р</b>
          </div>
          <div class="flex items-center gap-3">
            <button class="rounded-4xl bg-white shadow p-3 cursor-pointer hover:scale-110 transition">
              <svg>
              </svg>
            </button>
            <button class="rounded-4xl bg-white shadow p-3 cursor-pointer hover:scale-110 transition">
              <svg width="24" height="24" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M15.5 19L8.5 12L15.5 5" stroke="#7E8794" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/>
              </svg>

            </button>
          </div>
        </div>
        </div>
      </main>
    </div>    
    <footer class="p-6 bg-slate-100">
      <div class="text-center text-slate-500">
        Copyright @ 2023
      </div>
    </footer>
</body>
</template>