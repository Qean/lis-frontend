<template>
  <v-main>
    <v-container class="fill-height" fluid>
      <v-layout column justify-center align-center>
        <v-flex>
          <v-card>
            <v-card-title class="headline">Dashboard</v-card-title>
            <Table :items="tests" />
            <v-form ref="form" v-model="valid">
              <v-text-field v-model="testName" label="Test name" required />
              <v-text-field v-model="testCode" label="Test code" required />
              <v-btn color="success" class="mr-4" @click="addTest">Add test</v-btn>
            </v-form>
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
import Table from "@/components/Table";

export default {
  components: {
    Table
  },
  data: () => ({
    valid: false,
    tests: [{ name: "Dummy", code: "123" }],
    testName: "",
    testCode: ""
  }),
  methods: {
    addTest() {
      this.tests.push({ name: this.testName, code: this.testCode });
    }
  }
};
</script>

<style lang="scss" scoped>
.headline {
  justify-content: center;
}
.flex {
  min-width: 70%;
}
.v-form {
  max-width: 90%;
  margin: auto;
}
</style>
