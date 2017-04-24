<template>
  <div id="app">
    <h2>SimpleMDE in Vue.js</h2>
    
    <textarea id="content"></textarea>

    <br>
    <button @click="getContent()">提交</button>
  </div>
</template>

<script>
import SimpleMDE from 'simplemde'

export default {
  name: 'app',

  data () {
    return {
      mde: undefined,
      content: 'Welcome to Your Vue.js App'
    }
  },

  mounted () {
    this.mde = new SimpleMDE({
      element: document.getElementById('content'),
      toolbar: [
        'bold', 'italic', 'heading', 'quote', 'unordered-list', 'ordered-list', 
        'link', 'image', 'table', 'code', 'fullscreen', 'preview', 'guide'
      ]
    })
  },

  methods: {
    getContent () {
      console.log(this.mde.value())
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
