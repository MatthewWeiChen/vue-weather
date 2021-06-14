<template>
  <div class="search-box">
    <input
      v-model="location"
      type="text"
      placeholder="Search..."
      class="search-bar"
      @keyup.enter="$emit('searchLocation', $event.target.value)"
    />
  </div>
</template>
<script>
export default {
  name: "Search Bar",
  data() {
    return {
      location: "",
    };
  },
};
</script>

<style>
.search-bar {
  width: 100%;
  padding: 10px;
  border: none;
  border-top-right-radius: 15px;
  border-bottom-left-radius: 15px;
  line-height: 2em;
  background-color: rgb(224, 224, 224);
}
::placeholder {
  font-size: 16px;
}
</style>