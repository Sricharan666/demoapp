<template>
  <div class="container">
    <h2>Sign Up</h2>
    <form @submit.prevent="submitForm">
      <br />
      <div>
        <label for="firstName">First Name</label><br />
        <input type="text" id="firstName" v-model="formValues.firstName" />
      </div>
      <div>
        <label for="lastName">Last Name</label><br />
        <input type="text" id="lastName" v-model="formValues.lastName" />
      </div>
      <div>
        <label for="email">Email</label><br />
        <input type="email" id="email" v-model="formValues.email" />
      </div>
      <div>
        <label for="password">Password</label><br />
        <input type="password" id="password" v-model="formValues.password" />
      </div>
      <div>
        <label for="cpassword">Confirm Password</label><br />
        <input type="password" id="cpassword" v-model="formValues.cpassword" />
      </div>
      <div>
        <label for="country">country</label><br />
        <select id="country" v-model="formValues.country">
          <!-- <option value="">select your option</option> -->
          <option value="India">India</option>
          <option value="Viethnam">Viethnam</option>
          <option value="Singapore">Singapore</option>
        </select>
      </div>
      <div>
        <button>submit</button>
      </div>
    </form>
  </div>
</template>
<script>
export default {
  data() {
    return {
      formValues: {
        firstName: "",
        lastName: "",
        email: "",
        password: "",
        cpassword: "",
        country: "",
      },
    };
  },
  methods: {
    submitForm() {
      if (
        this.formValues.firstName == "" ||
        this.formValues.lastName == "" ||
        this.formValues.email == "" ||
        this.formValues.password == ""
      ) {
        alert("please enter values");
      } else if (this.formValues.password != this.formValues.cpassword) {
        alert("password and confirm password must be same");
      } else {
        this.$emit(
          "renderPage",
          this.formValues.email,
          this.formValues.password
        );
        //   console.log('Form values', this.formValues)
      }
    },
  },
};
</script>
<style scoped>
.container {
  width: 400px;
  background-image: linear-gradient(to right, rgb(225, 118, 250), rgb(65, 80, 250));
  padding: 30px;
  border-radius: 20px;
  color: white;
  margin: 60px auto 0;
}
input,
select {
  border-radius: 5px;
  width: 250px;
}
</style>