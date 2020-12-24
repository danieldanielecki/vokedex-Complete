<template>
  <div id="app">
    <Pokemons />
    <SearchPokemon @new-search-query="handleQuery" />
    <SearchResults :query="query" />
    <PokemonDetails />
    <PokemonImage />
    <router-link to="about">About</router-link>
  </div>
</template>

<script>
import Pokemons from "./../components/Pokemons";
import SearchPokemon from "./../components/Search/SearchPokemon";
import SearchResults from "./../components/Search/SearchResults";
import PokemonDetails from "./../components/PokemonDetails";
import PokemonImage from "./../components/PokemonImage";

export default {
  name: "App",
  data() {
    return {
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
  created() {
    console.log("created");
    console.log(this.$el);
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
