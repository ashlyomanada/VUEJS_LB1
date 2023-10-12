<template>
  <nav></nav>
  <div class="container">
    <div class="form-box">
      <form class="form">
        <span class="title">Sign up</span>
        <span class="subtitle">Create Your account here!</span>
        <div class="form-container">
          <input type="text" class="input" placeholder="Full Name" />
          <input type="email" class="input" placeholder="Email" />
          <input type="password" class="input" placeholder="Password" />
        </div>
        <button>Sign up</button>
      </form>
      <div class="form-section">
        <p>Have an account? <a href="">Log in</a></p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
};
</script>
<style scoped></style>
