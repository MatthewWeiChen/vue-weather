<template>
  <div id="app">
    <main>
      <SearchBar @searchLocation="inputLocation" />
      <LocationTime :location="location" />
      <Temperature />
    </main>
  </div>
</template>

<script>
import SearchBar from "./components/searchBar.vue";
import LocationTime from "./components/locationTime.vue";
import Temperature from "./components/temperature.vue";
export default {
  name: "App",
  data() {
    return {
      api_key: "c3560b9f610169e4e40ddf1a6062f5f3",
      location: "",
    };
  },
  components: {
    SearchBar,
    LocationTime,
    Temperature,
  },
  methods: {
    inputLocation($event) {
      this.location = $event;
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

main {
  font-family: "montserrat", sans-serif;
  color: white;
}

#app {
  background-image: url("./assets/cold-bg.jpg");
  background-size: cover;
  background-position: bottom;
  transition: 0.4s;
}

main {
  min-height: 100vh;
  padding: 25px;
  background-image: linear-gradient(
    to bottom,
    rgba(0, 0, 0, 0.25),
    rgba(0, 0, 0, 0.75)
  );
}
</style>
