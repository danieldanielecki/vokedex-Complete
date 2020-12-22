<template>
  <b-container class="p-3 bg-secondary home-view rounded">
    <b-row>
      <div id="blue-ball" class="bg-primary rounded-circle m-4" v-if="blue" />
      <div class="tiny-balls bg-danger rounded-circle mr-1 mt-4" v-else-if="danger" />
      <div class="tiny-balls bg-warning rounded-circle mr-1 mt-4" v-else-if="warning" />
      <div class="tiny-balls bg-success rounded-circle mr-1 mt-4" v-else />
      <h1 v-show="blue">Bla bla bla...</h1>
      <h1 v-bind:id="boundId">{{ title }}</h1>
       <p>Hello {{name }}</p>
      <a :href="boundUrl">Click</a>
    </b-row>
    <b-row>
    </b-row>
    <b-row>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "Home",
  data() {
    return {
      blue: false,
      boundId: "bound-id",
      boundUrl: "https://google.com",
      danger: false,
      name: "Daniel",
      title: "Title",
      warning: false
    };
  },
};
</script>

<style lang="scss">
#blue-ball {
  height: 70px;
  width: 70px;
  border: 10px solid lightgrey;
}

.tiny-balls {
  height: 20px;
  width: 20px;
  border: 1px solid black;
}

.home-view {
  border: 3px solid black;
}
</style>