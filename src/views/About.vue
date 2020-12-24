<template>
  <div id="about">
    <h1>About</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas aliquam
      molestiae quod. Beatae velit, magnam quis aspernatur odio nemo repellendus
      at dolores quos rerum minima. Similique saepe eum provident consequuntur?
    </p>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Quas aliquam
      molestiae quod. Beatae velit, magnam quis aspernatur odio nemo repellendus
      at dolores quos rerum minima. Similique saepe eum provident consequuntur?
    </p>
  </div>
</template>

<script>
export default {
  name: "About",
  mounted() {
    console.log("data: ", this.$route.params.name);
  },
};
</script>

<style lang="scss" scoped>
p {
  text-align: justify;
}
</style>
