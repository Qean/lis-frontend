<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <h1>Login</h1>
    <v-text-field v-model="email" :rules="emailRules" label="E-mail" required />

    <v-text-field v-model="password" label="Password" required />

    <v-btn :disabled="!valid" color="success" class="mr-4" @click="login"
      >Login</v-btn
    >
  </v-form>
</template>
<script>
export default {
  name: 'SignUp',
  props: {
    signUpFlag: {
      type: Boolean,
      default: true
    }
  },
  data: () => ({
    valid: false,
    email: '',
    emailRules: [
      (v) => !!v || 'E-mail is required',
      (v) => /.+@.+\..+/.test(v) || 'E-mail must be valid'
    ],
    password: ''
  }),

  methods: {
    login() {
      this.$router.push('loggedIn')
    }
  }
}
</script>

<style type="scss" scoped>
p {
  margin-top: 16px;
}
.v-form {
  margin: auto;
  max-width: 90%;
}
</style>
