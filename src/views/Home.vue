<template>
  <div id="app">
    <Pokemons />
    <SearchPokemon @new-search-query="handleQuery" />
    <SearchResults :query="query" />
    <PokemonDetails />
    <PokemonImage />
    <router-link to="about">About</router-link>
    <h2>List of pokemons</h2>
    <li v-for="pokemon in pokemons" :key="pokemon.name">
      {{ pokemon.name }}
    </li>
  </div>
</template>

<script>
import Pokemons from "./../components/Pokemons";
import SearchPokemon from "./../components/Search/SearchPokemon";
import SearchResults from "./../components/Search/SearchResults";
import PokemonDetails from "./../components/PokemonDetails";
import PokemonImage from "./../components/PokemonImage";
import { getAllPokemon } from "../services/pokeApi";

export default {
  name: "App",
  data() {
    return {
      pokemons: [],
      query: "",
    };
  },
  components: {
    Pokemons,
    SearchPokemon,
    SearchResults,
    PokemonDetails,
    PokemonImage,
  },
  async created() {
    console.log("created");
    console.log(this.$el);
    const pokemons = await getAllPokemon();
    this.pokemons = pokemons.results;
  },
  mounted() {
    console.log("Mounted");
    console.log(this.$el);
  },
  destroyed() {
    console.log("destroyed");
    console.log(this.$el);
  },
  methods: {
    handleQuery(data) {
      this.query = data;
    },
  },
};
</script>

<style lang="scss"></style>
