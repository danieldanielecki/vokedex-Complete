<template>
  <div id="search-pokemon">
    <b-col>
      <h3>SEARCH POKEMON</h3>
      <input v-model="query" />
      <button @click="search">Search</button>
      <button @click="resetForm">Reset</button>
    </b-col>
  </div>
</template>

<script>
export default {
  name: "SearchPokemon",
  data() {
    return {
      query: "",
    };
  },
  methods: {
    search() {
      this.$emit("new-search-query", this.query);
    },
    resetForm() {
      this.query = "";
    },
  },
};
</script>

<style lang="scss"></style>
