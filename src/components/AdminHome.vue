<script>

export default{
  data(){
    return{
      pokemons: []
    }
  },
  methods: {
    async fetchPokemons(url) {
      try {
        const response = await fetch(url);
        const data = await response.json();
        this.pokemons.push(...data.results);
      
      } catch (error) {
        console.error("Erro ao buscar Pokémons:", error);
      }
    },
  },
  created() {
    this.fetchPokemons("https://pokeapi.co/api/v2/pokemon?limit=20");
  },
}


</script>

<template>
 <ul>
      <li v-for="pokemon in pokemons" :key="pokemon.name">
        {{ pokemon.name }}
        <img :src="`https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${pokemons.indexOf(pokemon)+1}.png`" :alt="pokemon.name" />
      </li>
</ul>


</template>

<style scoped>

</style>