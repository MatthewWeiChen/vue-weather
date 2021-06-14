<template>
  <div class="container">
    <div class="location">
      {{ location ? location : "Choose Location" }}
    </div>
    <div class="date">Sunday, 13 June 2021</div>
  </div>
</template>
<script>
export default {
  name: "LocationTime",
  props: {
    location: String,
  },
};
</script>
<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 30px;
  flex-wrap: wrap;
  flex-direction: column;
}
.location {
  font-size: 2em;
  text-shadow: 1px 1px black;
}
.date {
  font-style: italic;
  opacity: 0.5;
  margin-top: 3px;
  font-size: 1.2em;
}
</style>