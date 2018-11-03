<template>
  <div id="app">
    <navigation></navigation>
    <div class="my-12 container mx-auto">
      <router-view/>
    </div>
  </div>
</template>

<script>
import Navigation from "@/components/Navigation";
export default {
  name: "App",
  components: {
    Navigation
  }
};
</script>
