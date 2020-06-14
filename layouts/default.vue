<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      app
      mobile-breakpoint="0"
      permament
      clipped
      expand-on-hover
    >
      <v-list dense>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-view-dashboard</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Dashboard</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-action>
            <v-icon>mdi-cog</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title>Settings</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <v-app-bar app clipped-left>
      <v-toolbar-title>LIS - SysMed</v-toolbar-title>
    </v-app-bar>

    <v-main>
      <v-container class="fill-height" fluid>
        <nuxt />
      </v-container>
    </v-main>

    <v-footer app>
      <span>&copy; LIS 2020</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data: () => ({
    drawer: true
  })
}
</script>

<style lang="scss" scoped>
footer {
  display: flex;
  justify-content: center;
  align-content: center;
}
</style>
