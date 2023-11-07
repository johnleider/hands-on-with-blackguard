<!-- eslint-disable vue/valid-v-slot -->
<template>
  <v-container>
    <h1 class="text-h3 mb-2">Users Page</h1>

    <v-sheet class="mb-4" color=surface-variant rounded>
      <v-breadcrumbs :items="breadcrumbs"></v-breadcrumbs>
    </v-sheet>

    <v-card title="User information" prepend-icon="mdi-account">
      <v-data-table :items="items" :loading="loading">
        <template #item.date="{ item }">
          <v-menu :close-on-content-click="false">
            <template #activator="{ props: activatorProps }">
              <v-chip v-bind="activatorProps" :text="item.date"></v-chip>
            </template>

            <v-card>
              <v-date-picker></v-date-picker>
            </v-card>
          </v-menu>
        </template>
      </v-data-table>
    </v-card>
  </v-container>
</template>

<script setup>
  import { onMounted } from 'vue';
  import { ref } from 'vue'

  const breadcrumbs = ref([
    {
      title: 'Home',
      to: '/'
    },
    {
      title: 'Users',
      active: true
    }
  ])
  const loading = ref(true)
  const items = ref(Array.from({ length: 35 }, (_, i) => ({
    name: `User ${i + 1}`,
    email: `user${i + 1}@example.com`,
    date: `2021-08-${String(i + 1).padStart(2, '0')}`,
    role: 'Admin',
    status: '✅',
  })))

  onMounted(() => {
    setTimeout(() => {
      loading.value = false
    }, 1500)
  })
</script>
