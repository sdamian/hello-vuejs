<script lang="tsx">
import Vue, { VNode } from 'vue';
import _ from 'lodash-es';

export default Vue.extend({
  data() {
    return {
      yourName: '',
    };
  },
  computed: {
    betterName(): string {
      return _.upperFirst(this.$data.yourName.toLowerCase().split('').reverse().join(''));
    },
  },
  render(): VNode {
    const hello = <h1>Hello {this.betterName} :o</h1>;
    return (
      <div>
        <label>Name:</label>
        <input type="text" v-model={this.yourName} />
        {this.yourName ? hello : null}
      </div>
    );
  },
});
</script>

<style lang="css">
input {
    text-transform: uppercase;
}
</style>
