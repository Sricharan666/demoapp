<template>
  <div class="container">
    <h2>Login</h2>
    <br />
    <form @submit.prevent="pushtoDash(na , pass)">
      <div>
        <label for="email">Email</label><br />
        <input type="email" id="email" v-model="formValues.email" />
      </div>
      <div>
        <label for="password">Password</label><br />
        <input type="password" id="password" v-model="formValues.password" />
      </div>
      <div>
        <button>submit</button>
      </div>
    </form>
    <div>
<br>
    <p>email : {{ na }}</p>
    <p>password : {{ pass }}</p>
    </div>

  </div>
</template>
<script>
export default {
  props: {
    na: String,
    pass: String,
  },
  data() {
    return {
      formValues: {
        email: "",
        password: "",
      },
    };
  },
  methods: {
    pushtoDash(x, y) {
      if (this.formValues.email == '' || this.formValues.password == '') {
        alert(" please enter values");
      } 
      else if(x !== this.formValues.email || y !== this.formValues.password) {
       alert("please enter valid name and password");
       
      }else{
        alert("success");
        console.log("email", this.formValues.email);
        console.log("password", this.formValues.password);
        this.$emit("redirectdash");
      }
    },
  },
};
</script>
<style scoped>
.container {
  width: 400px;
  background-image: linear-gradient(
    to right,
    rgb(225, 118, 250),
    rgb(65, 80, 250)
  );
  padding: 30px;
  border-radius: 20px;
  color: white;
    margin: 60px auto 0;
}
input {
  border-radius: 5px;
  width: 250px;
}
</style>