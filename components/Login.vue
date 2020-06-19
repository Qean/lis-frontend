<template>
  <v-form ref="form" v-model="valid" lazy-validation>
    <h1>Login</h1>
    <v-text-field v-model="email" :rules="emailRules" label="E-mail" required />
    <v-text-field
      v-model="password"
      :append-icon="hidePassword ? 'mdi-eye-off' : 'mdi-eye'"
      :type="hidePassword ? 'password' : 'text'"
      label="Password"
      @click:append="hidePassword = !hidePassword"
      required
    />
    <v-btn :disabled="!valid" color="success" class="mr-4" @click="login">Login</v-btn>
  </v-form>
</template>
<script>
import * as firebase from "firebase/app";
import "firebase/auth";

export default {
  name: "SignUp",
  props: {
    signUpFlag: {
      type: Boolean,
      default: true
    }
  },
  data: () => ({
    hidePassword: true,
    valid: false,
    email: "",
    emailRules: [
      v => !!v || "E-mail is required",
      v => /.+@.+\..+/.test(v) || "E-mail must be valid"
    ],
    password: ""
  }),

  methods: {
    async login() {
      try {
        await this.$fireAuth.signInWithEmailAndPassword(
          this.email,
          this.password
        );
        this.$router.push("dashboard");
      } catch (err) {
        window.alert(
          "An error has occured during login: " + err.message + " " + err.code
        );
      }
    }
  }
};
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
