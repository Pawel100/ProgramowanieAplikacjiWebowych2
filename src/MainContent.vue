<template>
  <div>
    <div class="clearfix">
      <div class="float-left"><h2>Witaj {{ user }}</h2></div>
      <div class="float-right"><button class="button button-outline" @click="logout()">Wychodzę</button></div>
    </div>
    <hr>
  </div>
</template>

<script>
  export default {
    props: ['user'],
    data () {
      return {
      }
    },
    methods: {
      logout() {
        this.$emit('logout');
      }
    },
  }
</script>

