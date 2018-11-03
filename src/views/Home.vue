<template>
  <div class="w-full flex flex-wrap flex-start">
    <section class="h-50 container mx-auto mb-8">
      <div class="py-8">
        <input class="w-full h-16 px-3 rounded mb-8 focus:outline-none focus:shadow-outline text-xl px-8 shadow-lg"
                type="search"
                placeholder="Buscar...">
      </div>
      <p class="text-lg font-bold mb-2 mx-4">Tipos de Pokemon</p>
      <div class="mx-4 flex justify-betwwen w-full flex-wrap">
          <div class="md-checkbox w-1/2 sm:w-1/4 xl:w-1/6" v-for="type in types" :key="type">
              <input :id="'checkbox-'+ type"
                      type="checkbox"
                      :value="type"
                      v-model="selectedPokemonTypes">
              <label :for="'checkbox-'+ type">
                  <i class="h-4 w-4 rounded-full mx-2" :class="`bg-${type}`"></i>
                  <span class="tracking-wide mx-2 font-medium">{{ type }}</span>
              </label>
          </div>
      </div>
    </section>
    <div class="flex flex-col w-full sm:w-1/2 md:w-1/3 xl:w-1/4 text-center mx-auto px-4 mb-6 relative group">
      <div class="mb-2 relative w-36 h-48 flex items-center justify-center group-hover:shadow-lg">
        <div class="absolute flex w-full h-full">
          <div class="w-full bg-poison"></div>
          <div class="w-full bg-grass"></div>
        </div>
        <img src="@/assets/images/pokemons/bulbasaur-min.gif"
             alt="bulbasaur"
             width="100"
             height="100"
             class="z-50 relative py-4">
      </div>
      <div class="capitalize font-bold text-lg">bulbasaur</div>
    </div>

  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      selectedPokemonTypes: [],
      types: [
        "grass",
        "poison",
        "fire",
        "flying",
        "water",
        "bug",
        "normal",
        "electric",
        "psychic"
      ]
    };
  }
};
</script>
