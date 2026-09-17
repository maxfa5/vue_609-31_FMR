<script setup>
defineProps({
  imgUrl: String,
  title: String,
  price: String,
});
</script>

<template>
  <div class="p-5 bg-slate-100 rounded-xl flex flex-col justify-between gap-2">
    <div>
      <img
        style="width: 100%; height: 192px;"

        class="mb-4 w-full h-48 object-cover rounded-lg"
        :src="imgUrl"
        alt=""
      />
      <h3 class="text-xl font-semibold">
        {{ title }}
      </h3>
    </div>
    <div class="flex items-center justify-between gap-2">
      <div>
        <p class="text-slate-500">Цена</p>
        <b class="text-xl">{{ price }} Р.</b>
      </div>
      <div class="flex items-center gap-3">
      </div>
    </div>
  </div>
</template>