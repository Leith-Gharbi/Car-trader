<template>
  <div
    class="font-serif w-[1000px] text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto"
  >
    <input
      v-model="city"
      :class="cityError ? 'border-red-500 border' : ''"
      type="text"
      class="py-3 px-5 w-full rounded-full focus:outline-none"
      placeholder="Search by city ..."
    />
    <button class="bg-sky-500 px-10 text-white" @click="handelSearch">
      Search
    </button>
  </div>
</template>

<script setup>
const city = ref("");
const cityError = ref(false);
const handelSearch = () => {
  if (!city.value) {
   return cityError.value = true;
  }
  navigateTo(`/city/${city.value}/car/test`);
};
</script>