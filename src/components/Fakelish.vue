<template>
  <div>
    <ul>
      <li v-for="fakeWord in fakeWords">
        {{ fakeWord }}
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import * as fakelish from 'fakelish';

// Capitalize string
function capitalize(str: string) {
  return str.charAt(0).toUpperCase() + str.substring(1);
}

@Component
export default class Fakelish extends Vue {
  private fakeWords: string[] = [];

  // Min and max Lengths of fake words
  private minLen = 7;
  private maxLen = 11;

  private async mounted() {
    // Generate 20 fake words
    for ( let i = 0; i < 20; i++) {
      // Generate a fake word
      const fakeWord = await fakelish.generateFakeWord(this.minLen, this.maxLen);
      // Push the capitalized fake word
      this.fakeWords.push(capitalize(fakeWord));
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
a {
  color: #42b983;
}
</style>
