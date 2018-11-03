```html
    <template v-else>
      <div class="flex flex-col justify-center items-center w-full">
        <p class="text-xl font-bold mb-4">No hemos encontrado tu Pokemon :(</p>
        <img src="https://media.giphy.com/media/SsjyaYH2gkNCE/giphy.gif" alt="Pikachu crying" class="w-64">
      </div>
    </template>
```

```javascript
    :src="require(`@/assets/images/pokemons/${pokemon.image}`)"
```

```html
    <router-link :to="{name: 'pokemon-detail', params: {name: pokemon.name}}" class="absolute h-full w-full"></router-link>
```

```javascript
    async getPokemons() {
      try {
        const response = await fetch("/pokemons.json");
        const json = await response.json();
        this.pokemons = json;
      } catch (error) {
        console.log(error);
      }
    }
```

```javascript
    filteredPokemons() {
      return this.pokemons
        .filter(pokemon => pokemon.name.includes(this.searchText))
        .filter(pokemon => {
          if (this.selectedPokemonTypes.length === 0) return true;
          return pokemon.types.find(type =>
            this.selectedPokemonTypes.includes(type)
          );
        });
    }
```

```javascript
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
];
```

```html
<div v-for="type in pokemon.types"
    :key="type"
    class="mx-2 text-white px-3 rounded-full py-1 font-bold"
    :class="`bg-${type}`">
    {{ type }}
</div>
```
