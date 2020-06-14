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
      <v-list nav>
        <v-subheader>Pages</v-subheader>
        <v-list-item-group v-model="item">
          <v-list-item
            v-for="(item, i) in items"
            :key="i"
            link
            nuxt
            :to="item.to"
          >
            <v-list-item-icon>
              <v-icon v-text="item.icon"></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title v-text="item.text"></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
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
    drawer: true,
    item: 0,
    items: [{ icon: 'mdi-home', text: 'Welcome', to: '/' }]
  })
}
</script>

<style lang="scss" scoped>
.v-subheader {
  padding: 0px;
}
footer {
  display: flex;
  justify-content: center;
  align-content: center;
}
</style>
