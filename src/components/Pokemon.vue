<template>
  <ul>
    <h3 :style="{ color: color }">
      {{ name }}
    </h3>
    <p>{{ type }}</p>
  </ul>
</template>

<script>
export default {
  name: "Pokemon",
  props: {
    color: String,
    name: String,
    type: String,
  },
};
</script>

<style lang="scss"></style>
