<template>
  <v-simple-table>
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">Test name</th>
          <th class="text-left">Code</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in items" :key="item.index">
          <td>{{ item.name }}</td>
          <td>{{ item.code }}</td>
        </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>

<script>
export default {
  name: "Table",
  props: {
    items: {
      type: Array,
      default: []
    }
  }
};
</script>

<style lang="scss" scoped>
.v-data-table {
  margin: auto;
  max-width: 90%;
}
</style>