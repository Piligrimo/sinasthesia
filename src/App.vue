<template>
  <div id="app">
    <div class="sticky-block">
      <input v-model="line">
      <button @click="save">Сохранить</button>
    </div>
    
    <div class="container">
      <letter v-for="(character, i) in line" :key="i" :character="character"/>
    </div>
  </div>
</template>

<script>
import Letter from './components/Letter.vue'
export default {
  name: 'App',
  components: {
    Letter
  },
  data () {
    return  {
      line: '3,1415926'
    }
  },
  created () {
    this.line = localStorage.getItem('line') || '3,1415926'
  },
  methods: {
    save () {
      localStorage.setItem('line', this.line)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.container {
  padding: 20px;

}
.sticky-block {
  position: sticky;
  top: 50px;
  left: 28px;
}
</style>
