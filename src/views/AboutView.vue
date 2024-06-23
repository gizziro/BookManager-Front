<template>
  <div class="about">
    <h1>This is 젖탱이</h1>
    <input v-model="initText"></input>
    <button @click="clickEvent">click</button>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data() {
    return {
      initText : "hello",
    }
  },
  methods : {
    clickEvent() {
      axios.get('/api/test')
     .then(res => {
      console.log(res.text);
      this.initText = res.text;
    }
    )
    }
  }
}
</script>

<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
