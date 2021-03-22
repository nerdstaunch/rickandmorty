<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
  {{testvar}}
</template>

<script>
import axios from 'axios';
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      testvar:'loading'
    }
  },
  created() {
    console.log("hello");
    this.test();
  },
  methods: {

    test() {
      axios.get('https://rickandmortyapi.com/api')
      .then((response) => {
        this.testvar = response.data
        console.log(response.data);
        console.log(response.status);
        console.log(response.statusText);
        console.log(response.headers);
        console.log(response.config);
      });
    }

  }
}
</script>
