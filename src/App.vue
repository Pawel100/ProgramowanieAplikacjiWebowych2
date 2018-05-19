<template>
  <div id="app">
    <h1>Twój e-mail to {{ email.length}}</h1>
    <input type="email" v-model="email">
    <h1>Twój e-mail to {{ email.toLowerCase() }}</h1>
    
    <div v-if="email.length < 10">Ale masz krótki adres!</div>
    <div v-else-if="email.length < 15">Twój adres e-mail jest w sam raz.</div>
    <div v-else>Twój adres e-mail jest stanowczo za długi.</div>

    <button @click="alertMyEmail()">Wyświetl mój e-mail w alercie</button>


  </div>

  
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      email: "test@test.com"
    };
  },
  methods: {
  alertMyEmail() {
    alert(this.email);
  }
}
};
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
