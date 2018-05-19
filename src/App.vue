<template>
  <div id="app">
    <h1>Witaj w systemie zapisów na zajęcia</h1>
      <div v-if="!isAuthenticated">
        Zaloguj się e-mailem:<input type="email" v-model="email"><button @click="logIn()">Zaloguj</button>
      </div>
      <div v-else>
        Witaj {{email}}<button @click="logOut()">Wyloguj</button>
    </div>
  </div>
</template>


<script>
import "milligram";
export default {
  name: 'app',
  data () {
    return {
      email: '',
      isAuthenticated: false
    }
  },
  methods: {
    logIn() {
      this.isAuthenticated = true
    },
    logOut() {
      this.isAuthenticated = false
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1,
h2 {
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
