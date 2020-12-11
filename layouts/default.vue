<template>
  <v-app dark>
    <v-app-bar
      fixed
      app
    >
      <v-tabs>
        <v-tab
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
      </v-tab>
      </v-tabs>
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container class="v-application--wrap  align-center justify-center">
        <nuxt />
      </v-container>
    </v-main>
    <v-footer
      :absolute="!fixed"
      app
    >
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data () {
    return {
      fixed: false,
      items: [
        {
          icon: 'mdi-apps',
          title: 'Welcome',
          to: '/'
        },
        {
          icon: 'mdi-chart-bubble',
          title: 'about',
          to: '/about'
        }
      ]
    }
  }
}
</script>
