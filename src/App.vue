<template>
  <div id="app">
    <main>
      <SearchBar @searchLocation="inputLocation" />
      <LocationTime :location="location" />
      <Temperature :temperature="temperature" />
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
      api_key: "c50f4b1779069f947bfd0fd196f49f8d",
      url_base: "https://api.openweathermap.org/data/2.5/",
      query: "",
      weather: {},
      location: "",
    };
  },
  components: {
    SearchBar,
    LocationTime,
    Temperature,
  },
  methods: {
    async inputLocation($event) {
      this.location = $event;
      console.log(this.location);
      const response = await fetch(
        `${this.url_base}weather?q=${this.location}&appid=${this.api_key}&units=imperial`
      );
      const data = await response.json();
      this.setResults(data);
    },
    setResults(results) {
      this.weather = results;
      console.log(results);
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
