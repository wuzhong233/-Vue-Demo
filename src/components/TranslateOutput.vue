<template>
  <div id="translateOutput">
    <h2>{{translatedText}}</h2>
  </div>
</template>

<script>
export default {
  name: "translateOutput",
  props: ["translatedText"]
};
</script>

<style scoped>
div {
  text-align: center;
  font-size: 26px;
  color: #fff;
}
</style>