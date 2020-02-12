<template>
  <div class="login-form-container">
    <form class="form-login">
      <div class="text-center mb-4">
        <h1 class="h3 mb-3 font-weight-normal">Please login</h1>
      </div>
      <div class="form-label-group">
        <input
          type="email"
          id="inputEmail"
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
          class="form-control"
          placeholder="Password"
          required
        />
        <label for="inputPassword">Password</label>
      </div>
      <button class="btn btn-lg btn-success btn-block" type="submit">Login</button>
      <div class="form-separator">OR</div>
      <GoogleSigninButton></GoogleSigninButton>
      <hr />
      <div class="register-account">
        <p>Don't have an account ?</p>
        <router-link to="/register">Register a new account</router-link>
      </div>
      <div class="img-login">
        <img class="img-fluid" src="../assets/images/laptop-2298286_1280.jpg" />
      </div>
    </form>
  </div>
</template>

<script>
import GoogleSigninButton from "../components/GoogleSigninButton";
export default {
  name: "Login",
  components: {
    GoogleSigninButton
  },
  data() {
    return {
      email: ""
    };
  }
};
</script>