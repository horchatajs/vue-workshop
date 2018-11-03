<template>
  <div class="container mx-auto">
    <div class="px-4">
      <h1 class="capitalize mb-2">Bulbasaur</h1>
      <div class="flex mb-12">
        <!-- types -->
      </div>
      <div class="w-full flex flex-col md:flex-row" v-if="Object.keys(pokemon).length">
        <div class="w-1/2 text-lg">
          <p class="mb-8">
            <span class="font-bold">Experiencia:</span> 50
          </p>
          <p class="mb-8">
            <span class="font-bold">Peso:</span> 100
          </p>
          <p class="mb-8">
            <span class="font-bold">Altura:</span> 150
          </p>
          <p class="mb-8">
            <span class="font-bold">Habilidades:</span> First, second
          </p>
        </div>
      </div>
      <div class="text-center">
        <router-link :to="{name: 'home'}" class="no-underline font-bold text-lg">Regresar</router-link>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "PokemonDetail",
  data() {
    return {
      pokemon: {}
    };
  },
  computed: {
    abilities() {
      return this.pokemon.abilities.join(", ");
    }
  },
  mounted() {
    this.getPokemon();
  },
  methods: {
    async getPokemon() {
      try {
        const response = await fetch("/pokemons.json");
        const json = await response.json();
        this.pokemon = json.find(p => p.name === this.$route.params.name);
      } catch (error) {
        console.log(error);
      }
    }
  }
};
</script>
