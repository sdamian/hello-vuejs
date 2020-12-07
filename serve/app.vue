<template>
<div class="p-3">
    <label>Name:</label>&nbsp;
    <input type="text" v-model="yourName" />
    <h2 v-if="yourName">Hello {{ betterName }}!</h2>
</div>
</template>

<script lang="js">
import "bootstrap/dist/css/bootstrap.css";
export default {
  data() {
    return {
      yourName: "",
    };
  },
  computed: {
    betterName() {
      return this.yourName.split("").reverse().join("").toUpperCase();
    },
  },
};
</script>

<style lang="css">
input {
    text-transform: uppercase;
}
</style>
