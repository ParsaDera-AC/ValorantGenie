<template>
    <form @submit.prevent="login">
      <label for="username">Username:</label>
      <input type="text" v-model="username" id="username"><br>
      <label for="password">Password:</label>
      <input type="password" v-model="password" id="password"><br>
      <button type="submit">Log In</button>
    </form>
  </template>
  
  <script>

  export default {
    data() {
      return {
        username: '',
        password: ''
      };
    },
    methods: {
      login() {
        
        this.$emit('login', { username: this.username, password: this.password });

        
      }
    }
  };
  </script>
  