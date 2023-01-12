<template>
  <div>
    <h1>API Response</h1>
    <pre>{{ apiResponse }}</pre>
    <NameForm @login="handleLogin"></NameForm>
    
  </div>
</template>




<script>
import axios from "axios";
import NameForm from "./NameForm.vue";


export default {
  name: "FirstApi",
  props: {
    msg: String,
  },
  components: {
    NameForm,
  },
  data() {
    return {
      apiResponse: "",
      valorantUser: "",
      valorantTag: "",
    };
  },
  methods: {
    handleLogin(data) {
      console.log(data);
      console.log(data.username);
      console.log(data.password);

      this.valorantUser = data.username;
      this.valorantTag = data.password;
      this.fetchResponse();
    },
    fetchResponse() {
      console.log("https://api.henrikdev.xyz/valorant/v1/account/${this.valorantUser}/${this.valorantTag}");
      axios
        .get(
          `https://api.henrikdev.xyz/valorant/v1/account/${this.valorantUser}/${this.valorantTag}`
        )
        .then((response) => {
          
          this.apiResponse = response.data;
          console.log(response.data);
        })
        .catch((error) => {
          console.log(error);
        });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
