<template>
  <div class="temperature-container">
    <div class="temperature">90° F</div>
  </div>
</template>
<script>
export default {
  name: "Temperature",
};
</script>
<style>
.temperature-container {
  text-align: center;
}

.temperature-container .temperature {
  margin-top: 30px;
  background-color: rgba(241, 241, 241, 0.3);
  font-size: 5em;
  font-weight: 900;
  display: inline-block;
  padding: 10px 25px;
  text-shadow: 2px 4px rgba(0, 0, 0, 0.25);
}
</style>