<template>
  <div>
    <div v-if="page === 'register'">
      <RegisterPage @renderPage="submitLogin" />
    </div>
    <div v-else-if="page == 'login'">
      <LoginPage @redirectdash="submitDash" :na="email" :pass="password" />
    </div>
    <div v-else>
      <DashBoard />
    </div>
  </div>
</template>

<script>
import RegisterPage from "./components/RegisterPage.vue";
import LoginPage from "./components/LoginPage.vue";
import DashBoard from "./components/DashBoard.vue";
export default {
  name: "App",
  data() {
    return {
      page: "register",
      email: "",
      password: "",
    };
  },
  components: {
    RegisterPage,
    LoginPage,
    DashBoard,
  },
  methods: {
    submitLogin(email, password) {
      this.page = "login";
      this.email = email;
      this.password = password;
    },
    submitDash() {
      this.page = "dash";
    },
  },
};
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top : 60px; */

}
</style>

