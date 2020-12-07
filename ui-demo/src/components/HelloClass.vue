<template>
  <div>
    <label>Name:</label>
    <input type="text" v-model="yourName" />
    <h1 v-if="yourName">Hello {{ betterName }} :)</h1>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import _ from 'lodash-es';

@Component
export default class Home extends Vue {
  yourName = '';

  get betterName() {
    return _.upperFirst(this.yourName.toLowerCase().split('').reverse().join(''));
  }
}
</script>

<style lang="css">
input {
    text-transform: uppercase;
}
</style>
