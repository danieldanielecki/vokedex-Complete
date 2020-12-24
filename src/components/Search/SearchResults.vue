<template>
  <div id="search-results">
    <h3>SEARCH RESULTS FOR {{ query }}</h3>
  </div>
</template>

<script>
export default {
  name: "SearchResults",
  props: {
    query: String,
  },
};
</script>

<style lang="scss"></style>
