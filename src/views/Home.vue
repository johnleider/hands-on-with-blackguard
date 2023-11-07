<template>
  <v-container class="fill-height">
    <v-responsive class="align-center text-center fill-height">
      <v-img height="300" src="@/assets/logo.svg" />

      <h1 class="text-h3 font-weight-bold mb-2">Welcome to</h1>

      <div class="text-h5 font-weight-light">Hands on with Vuetify Blackguard</div>

      <div class="py-4" />

      <v-row align="center" justify="center">
        <v-col cols="auto">
          <v-btn
            href="https://vuetifyjs.com/components/all/"
            min-width="164"
            rel="noopener noreferrer"
            target="_blank"
            variant="text"
          >
            <v-icon
              icon="mdi-view-dashboard"
              size="large"
              start
            />

            Components
          </v-btn>
        </v-col>

        <v-col cols="auto">
          <v-btn
            color="primary"
            min-width="228"
            size="x-large"
            to="/auth/register"
            variant="flat"
          >
            <v-icon
              icon="mdi-speedometer"
              size="large"
              start
            />

            Get Started
          </v-btn>
        </v-col>

        <v-col cols="auto">
          <v-btn
            href="https://community.vuetifyjs.com/"
            min-width="164"
            rel="noopener noreferrer"
            target="_blank"
            variant="text"
          >
            <v-icon
              icon="mdi-account-group"
              size="large"
              start
            />

            Community
          </v-btn>
        </v-col>

        <v-col cols="12" class="mt-4">
          <div class="d-flex align-center w-25 mx-auto mb-8">
            <v-divider width="250"></v-divider>

            <div class="text-h6 text-no-wrap px-2">Workshop Pages</div>

            <v-divider width="250"></v-divider>
          </div>


          <div class="d-flex ga-4 justify-center">
            <v-btn
              min-width="164"
              border
              to="/auth/login/"
              variant="text"
              text="Login"
              prepend-icon="mdi-login"
            ></v-btn>

            <v-btn
              min-width="164"
              border
              to="/auth/register/"
              variant="text"
              text="Register"
              prepend-icon="mdi-account-plus"
            ></v-btn>

            <v-btn
              min-width="164"
              border
              to="/admin/dashboard/"
              variant="text"
              text="Dashboard"
              prepend-icon="mdi-view-dashboard"
            ></v-btn>

            <v-btn
              min-width="164"
              border
              to="/admin/users/"
              variant="text"
              text="Users"
              prepend-icon="mdi-account-multiple"
            ></v-btn>
          </div>
        </v-col>
      </v-row>
    </v-responsive>
  </v-container>
</template>

<script setup>
  //
</script>
