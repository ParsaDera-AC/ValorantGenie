<template>
  <v-form @submit.prevent="login">
    <v-text-field
      label="Username"
      v-model="username"
      id="username"
      class="my-custom-class"
    />
    <v-text-field
      label="Password"
      v-model="password"
      id="password"
      type="password"
      class="my-custom-class"
    />
    <v-btn type="submit" color="primary">Log In</v-btn>
  </v-form>
</template>


<script>
export default {
  data() {
    return {
      username: "",
      password: "",
    };
  },
  methods: {
    login() {
      this.$emit("login", { username: this.username, password: this.password });
    },
  },
};
</script>

<style>
  .my-custom-class {
    /* custom styles here */
    font-size: 20px;
    margin-top: 20px;
  }
</style>
