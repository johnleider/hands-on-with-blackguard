<template>
  <v-navigation-drawer>
    <v-list nav density="compact" slim>
      <v-list-item title="Username" subtitle="email@gmail.com">
        <template #prepend>
          <v-avatar color="grey" size="x-small" class="me-1"></v-avatar>
        </template>
      </v-list-item>

      <v-divider class="my-2"></v-divider>

      <v-list-item title="Dashboard" prepend-icon="mdi-view-dashboard" to="/admin/dashboard/"></v-list-item>

      <v-list-item title="Users" prepend-icon="mdi-account-multiple" to="/admin/users/"></v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>

<script setup>
  //
</script>
