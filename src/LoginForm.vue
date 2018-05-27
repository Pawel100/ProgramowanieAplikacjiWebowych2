<template>
   <div>
       <label>{{ msg }}</label>
       <input type="email" v-model="email">
       <button @click="enter()">{{buttonLabel}}</button>
   </div>

     
</template>

<script>
export default {
  props: ['buttonLabel'],
 data() {
     return {
         msg: 'Zaloguj się e-mailem hahaha',
         email: ''
     }
 },
 mounted() {
  if (!this.buttonLabel) {
    this.buttonLabel = 'Zaloguj się';
  }
}, 
 methods: {
     enter() {
         if(!this.emailError) {
          this.$emit('login', this.email);
     }
 }
}
 
}
</script>