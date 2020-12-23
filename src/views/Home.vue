<template>
  <b-container class="p-3 bg-secondary home-view rounded">
    <b-row>
      <div id="blue-ball" class="bg-primary rounded-circle m-4" v-if="blue" />
      <div
        class="tiny-balls bg-danger rounded-circle mr-1 mt-4"
        v-else-if="danger"
      />
      <div
        class="tiny-balls bg-warning rounded-circle mr-1 mt-4"
        v-else-if="warning"
      />
      <div class="tiny-balls bg-success rounded-circle mr-1 mt-4" v-else />
      <h1 v-show="blue">Bla bla bla...</h1>
      <h1 v-bind:id="boundId">{{ title }}</h1>
      <p>Hello {{ name }}</p>
      <a :href="boundUrl">Click</a>
    </b-row>
    <b-row>
      <ul>
        <li v-for="detail in details" :key="detail.index">
          {{ detail }}
        </li>
      </ul>
    </b-row>
    <b-row>
      <ul v-for="pokemon in pokemons" :key="pokemon.index">
        <h3>{{ pokemon.name }}</h3>
        <p>{{ pokemon.type }}</p>
      </ul>
    </b-row>
    <hr />

    <form>
      <button @click.prevent="FirstClickHandler('hellow2')" type="button">
        Prevent
      </button>
      <button @click="window.alert('test')">Button 1</button>
    </form>
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
      details: ["awesome", "fire", "dragon"],
      name: "Daniel",
      pokemons: [
        { name: "charmander", type: "fire" },
        { name: "squirtle", type: "water" },
        { name: "bulbasaur", type: "grass" },
      ],
      title: "Title",
      warning: false,
    };
  },
  methods: {
    FirstClickHandler(data) {
      alert("I have been clicked " + data);
    },
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
