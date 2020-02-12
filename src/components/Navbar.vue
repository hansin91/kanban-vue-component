<template>
  <nav class="navbar navbar-expand-md navbar-dark fixed-top">
    <router-link class="btn btn-link btn-title" to="/" exact>Kanban</router-link>
    <div class="login-register">
      <router-link class="btn btn-link" to="login" exact>Login</router-link>
      <router-link class="btn btn-primary btn-register" to="register">Register</router-link>
    </div>
  </nav>
</template>

<script>
export default {
  name: "Navbar"
};
</script>