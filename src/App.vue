<template>
  <div id="app">
    <div>
      <div v-for='news in news' :key="news.id">
        <h1>{{news.title}}</h1>
        <div>
          {{news.body}}
        </div>
      </div>
    </div>
    <!--img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/-->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  data: function() {
    return {
      news: []
    }
  },
  mounted() {
    this.getNews()
  },
  components: {
    // HelloWorld
  },
  methods: {  
    getNews() {
      fetch('http://jsonplaceholder.typicode.com/posts')
      .then(response => response.json())
      .then(json => {
        this.news = json
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
