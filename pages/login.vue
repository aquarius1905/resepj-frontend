<template>
  <div class="app">
    <Header></Header>
    <div class="user-login">
      <div class="user-login-innner box-shadow">
        <h2 class="login-ttl">Login</h2>
        <div class="login-form">
          <div class="login-input-wrap">
            <img src="@/assets/images/email.png" alt="email" class="login-img">
            <input v-model="email" type="text" placeholder="メールアドレス" class="login-input" required />
          </div>
          <div class="login-input-wrap">
            <img src="@/assets/images/password.png" alt="password" class="login-img">
            <input v-model="password" type="password" placeholder="パスワード" class="login-input" required />
          </div>
          <div class="login-btn-wrap">
            <button class="login-btn">ログイン</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    };
  },
  created() {
  },
};
</script>

<style scoped>
.login-btn-wrap {
  display: flex;
  justify-content: right;
}
@media screen and (max-width: 768px) {
  .login-btn-wrap {
      display: flex;
      justify-content: right;
    }
}
</style>