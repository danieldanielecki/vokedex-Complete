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
    <b-row :class="{ darkTheme: isDark }">
      <button @click="isDark = !isDark">enter darkness</button>
      <ul v-for="pokemon in pokemons" :key="pokemon.index">
        <h3 :style="{ color: pokemon.color }">
          {{ pokemon.name }}
        </h3>
        <p>{{ pokemon.type }}</p>
      </ul>
    </b-row>
    <hr />

    <form @submit="formSubmit">
      <button @click.prevent="FirstClickHandler('hellow2')" type="button">
        Prevent
      </button>
      <button>Button 1</button>
      <input :class="{ myBackground }" v-model="searchQuery" />
      <button type="submit">Search</button>
      <button type="submit" @click.prevent="resetForm">Reset</button>
      <h3>Your name is {{ searchQuery }}</h3>
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
      isDark: false,
      name: "Daniel",
      pokemons: [
        { color: "red", name: "charmander", type: "fire" },
        { color: "blue", name: "squirtle", type: "water" },
        { color: "#f0f0f0", name: "bulbasaur", type: "grass" },
      ],
      searchQuery: "Daniel",
      title2: "Title2",
      warning: false,
    };
  },
  computed: {
    title() {
      return this.title2 + " " + this.searchQuery;
    },
  },
  methods: {
    FirstClickHandler(data) {
      alert("I have been clicked " + data);
    },
    formSubmit() {
      alert(`hello, your query: ${this.searchQuery}`);
    },
    resetForm() {
      this.searchQuery = "";
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

.myBackground {
  background-color: brown !important;
}

.darkTheme {
  background-color: black;
}
</style>
