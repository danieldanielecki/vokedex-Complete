<template>
  <div id="app">
    <Pokemons />
    <SearchPokemon />
    <SearchResults />
    <PokemonDetails />
    <PokemonImage />
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
  components: {
    Pokemons,
    SearchPokemon,
    SearchResults,
    PokemonDetails,
    PokemonImage,
  },
};
</script>

<style lang="scss"></style>
