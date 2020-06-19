<template>
  <v-main>
    <v-container class="fill-height" fluid>
      <v-layout column justify-center align-center>
        <v-flex>
          <v-card>
            <v-card-title class="headline">Welcome to the LIS medical system</v-card-title>
            <Login />
            <v-card-actions>
              <v-spacer />
            </v-card-actions>
          </v-card>
        </v-flex>
        <br />
        <v-img
          src="https://cdn.pixabay.com/photo/2017/02/01/10/26/laboratory-2029470_1280.png"
          max-width="500px"
        />
        <br />
      </v-layout>
    </v-container>
  </v-main>
</template>

<script>
import Login from '@/components/Login'

export default {
  components: {
    Login
  }
}
</script>

<style lang="scss" scoped></style>
