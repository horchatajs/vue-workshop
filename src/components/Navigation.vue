<template>
  <div class="h-24 bg-indigo text-white shadow flex items-center">
    <div class="container mx-auto flex justify-between">
      <router-link :to="{name: 'home'}">
        <img src="@/assets/images/logo.svg" alt="Logo Pokemon" class="h-16">
      </router-link>
      <img src="@/assets/logo.png" alt="Logo Vue" class="h-16">
    </div>
  </div>
</template>

<script>
export default {
  name: "Navigation"
};
</script>
