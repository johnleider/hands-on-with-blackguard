<template>
  <v-container>
    <h1 class="text-center text-h3 mb-4">Login Page</h1>

    <v-img class="mb-16" height="150" src="@/assets/logo.svg" />

    <v-card class="mx-auto mb-6" title="Enter Login details" subtitle="Enter your login information below" width="400">
      <template #text>
        <v-form>
          <v-text-field
            label="Email"
            required
          />

          <v-text-field
            label="Password"
            required
          />

          <v-btn block text="Submit" variant="tonal" to="/admin/dashboard/"></v-btn>
        </v-form>
      </template>
    </v-card>

    <div class="text-center text-caption">
      <div class="d-flex align-center justify-center">
        Don't have an account?

        <v-btn to="/auth/register/" class="ms-2" text="Register" size="x-small" variant="outlined"></v-btn>
      </div>

      <div class="d-flex align-center w-25 mx-auto my-4">
        <v-divider></v-divider>

        <div class="px-4">
          OR
        </div>

        <v-divider></v-divider>
      </div>

      <div class="d-flex align-center justify-center">
        Go Home

        <v-btn to="/" class="ms-2" exact text="Home" size="x-small" variant="outlined"></v-btn>
      </div>
    </div>
  </v-container>
</template>

<script setup>
  //
</script>
