<template>
  <v-app>
    <dashboard-app-bar />

    <dashboard-navigation-drawer />

    <dashboard-view />
  </v-app>
</template>

<script setup>
  import DashboardAppBar from './AppBar.vue'
  import DashboardNavigationDrawer from './NavigationDrawer.vue'
  import DashboardView from './View.vue'
</script>
