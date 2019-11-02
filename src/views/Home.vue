<template>
  <div class="home">
    <div>{{ text }}</div>
    <div>{{ num + (num * tax) }}</div>
    <div>{{ flag ? 'OK' : 'NG' }}</div>
    <div>{{howmuch}}</div>
    <div v-show="vShowFlag">ここがvShow</div>
    <div v-if="vIfFlag">ここがvIf</div>
    <div v-for="(val, idx) in listItem" :key="idx">{{ val }}</div>
    <input v-model="inputText" />
    <div>{{ inputText }}</div>
    <br>
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App" :propValue="20" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  },
  data: function() {
    return {
      text: 'price',
      num: 100,
      tax: 0.10,
      flag: true,
      vShowFlag: true,
      vIfFlag: false,
      listItem: ['apple','banana','orange'],
      inputText: '',
    }
  },
  computed: {
    howmuch() {
      const { text, num, tax } = this;
      return text + " is " + (num + (num * tax))
    }
  },
  created() {
    // console.log('created!');
  },
  mounted() {
    // console.log('mounted!');
  },
  beforeDestroy() {
    // console.log('beforeDestroy');
  },
}
</script>
