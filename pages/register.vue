<template>
  <div class="app">
    <Header></Header>
    <div class="register box-shadow">
      <h2 class="register-ttl">Registration</h2>
      <div class="register-form">
        <validation-observer ref="obs" v-slot="ObserverProps">
          <div class="register-input-wrap">
            <img src="@/assets/images/username.png" alt="username" class="register-img">
            <validation-provider v-slot="ProviderProps" rules="required">
              <input type="text" v-model="name" name="ユーザー名" class="register-input" placeholder="Username">
              <div class="error">{{ ProviderProps.errors[0] }}</div>
            </validation-provider>
          </div>
          <div class="register-input-wrap">
            <img src="@/assets/images/email.png" alt="email" class="register-img">
            <validation-provider v-slot="ProviderProps" rules="required|email">
              <input type="email" v-model="email" name="メールアドレス" class="register-input" placeholder="Email">
              <div class="error">{{ ProviderProps.errors[0] }}</div>
            </validation-provider>
          </div>
          <div class="register-input-wrap">
            <img src="@/assets/images/password.png" alt="password" class="register-img">
            <validation-provider v-slot="ProviderProps" rules="required|min:8">
              <input type="password" v-model="password" name="パスワード" class="register-input" placeholder="Password">
              <div class="error">{{ ProviderProps.errors[0] }}</div>
            </validation-provider>
          </div>
          <div class="register-btn-wrap">
            <button @click="register" :disabled="ObserverProps.invalid || !ObserverProps.validated" class="register-btn">登録</button>
          </div>
        </validation-observer>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: null,
      email: null,
      password: null
    };
  },
  methods: {
    register() {
      if (confirm('登録しますか？')) {
        this.insertUser();
      }
    },
    async insertUser() {
      const sendData = {
        name: this.name,
        email: this.email,
        password: this.password,
      }
      await this.$axios.post('/api/users/', sendData)
      this.$router.replace('/thanks')
    }
  },
};
</script>

<style scoped>
.register-btn-wrap {
  margin-top: 25px;
  text-align: right;
}
</style>