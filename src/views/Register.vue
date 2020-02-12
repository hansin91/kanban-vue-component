<template>
  <div class="register-form-container">
    <form class="form-register" @submit.prevent="registerUser">
      <div class="text-center mb-4">
        <h1 class="h3 mb-3 font-weight-normal">Register here</h1>
      </div>
      <div class="form-label-group">
        <input
          type="text"
          id="input-username"
          v-model="username"
          class="form-control"
          placeholder="Username"
          required
          autofocus
        />
        <label for="input-username">Username</label>
      </div>
      <div class="form-label-group">
        <input
          type="email"
          id="inputEmail"
          v-model="email"
          class="form-control"
          placeholder="Email address"
          required
          autofocus
        />
        <label for="inputEmail">Email address</label>
      </div>
      <div class="form-label-group">
        <input
          type="password"
          id="inputPassword"
          v-model="password"
          class="form-control"
          placeholder="Password"
          required
        />
        <label for="inputPassword">Password</label>
      </div>
      <button class="btn btn-lg btn-success btn-block" type="submit">Register</button>
      <div class="form-separator">OR</div>
      <GoogleSigninButton></GoogleSigninButton>
      <hr />
      <div class="register-account">
        <p>Already have an account ?</p>
        <router-link to="/login">Please login here</router-link>
      </div>
      <div class="img-login">
        <img class="img-fluid" src="../assets/images/laptop-2298286_1280.jpg" />
      </div>
    </form>
  </div>
</template>

<script>
const BASE_URL = "http://localhost:3000";
import GoogleSigninButton from "../components/GoogleSigninButton";
import axios from "axios";
export default {
  name: "Register",
  components: {
    GoogleSigninButton
  },
  data() {
    return {
      username: "",
      email: "",
      password: ""
    };
  },
  methods: {
    registerUser() {
      axios
        .post(BASE_URL + "/users/register", {
          email: this.email,
          username: this.username,
          password: this.password
        })
        .then(user => {
          console.log(user.data);
        })
        .catch(err => {
          console.log(err);
        });
    }
  },
  mounted() {
    this.email = this.$route.query.email;
  }
};
</script>