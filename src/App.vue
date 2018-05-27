<template>
  <div id="app">
    <h1 class="app-title">{{ msg }}</h1>
      <div v-if="!authenticatedEmail">
        <login-form @login="logMeIn($event)"
          :button-label = "'Wchodzę'" >
        </login-form>
        
      </div>
      <main-content
      v-else
      @logout="logMeOut()"
      :user="authenticatedEmail">
    </main-content>
  </div>

</template>

<script>
import "milligram";
import LoginForm from "./LoginForm";
import MainContent from "./MainContent";
export default {
  name: 'app',
  components: {LoginForm,
                MainContent},
  data () {
    return {
      msg: 'Witaj w systemie zapisów na zajęcia',
      authenticatedEmail: ""
    }
  },
  methods: {
    logMeOut() {
      this.authenticatedEmail = '';
      this.isAuthenticated = false;
    },
    logMeIn(email) {
  this.authenticatedEmail = email;
   this.isAuthenticated = true;
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
