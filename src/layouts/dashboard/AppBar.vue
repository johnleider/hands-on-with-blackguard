<template>
  <v-app-bar>
    <template #prepend>
      <v-img width="36" src="@/assets/logo.svg" />
    </template>

    <v-app-bar-title>Admin Project</v-app-bar-title>

    <template #append>
      <v-btn icon="mdi-logout" to="/auth/login/"></v-btn>
    </template>
  </v-app-bar>
</template>

<script setup>
  //
</script>
