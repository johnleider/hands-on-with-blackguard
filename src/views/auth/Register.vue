<template>
  <v-container>
    <h1 class="text-center text-h3 mb-4">Register Page</h1>

    <v-img class="mb-16" height="150" src="@/assets/logo.svg" />

    <v-stepper class="mx-auto mb-6" width="600">
      <template #default="{ prev, next }">
        <v-stepper-header>
          <v-stepper-item title="User Information" value="1" />

          <v-divider />

          <v-stepper-item title="Verfication" value="2" />

          <v-divider />

          <v-stepper-item title="Login" value="3" />
        </v-stepper-header>

        <v-stepper-window>
          <v-stepper-window-item value="1">
            <h2 class="text-h5">Details</h2>

            <div class="text-body-2 text-medium-emphasis mb-2">
              Please enter your details below.
            </div>

            <v-form>
              <v-row>
                <v-col cols="6">
                  <v-text-field
                    label="Name"
                    required
                  />
                </v-col>

                <v-col cols="6">

                  <v-text-field
                    label="Email"
                    required
                  />
                </v-col>
                <v-col cols="6">

                  <v-text-field
                    label="Password"
                    required
                  />
                </v-col>

                <v-col cols="6">

                  <v-text-field
                    label="Confirm Password"
                    required
                  />
                </v-col>
              </v-row>
            </v-form>
          </v-stepper-window-item>

          <v-stepper-window-item value="2">
            <v-responsive max-width="400" class="mx-auto text-center">
              <h2 class="text-h5 mb-4">Check your email!</h2>

              <div class="text-body-2 text-medium-emphasis">
                We sent a verification code to john..@gmail.com
                Please check your email and paste the code below.
              </div>

              <v-otp-input />

              <div class="text-caption">
                Didn't receive the code? <a href="#">Resend</a>
              </div>
            </v-responsive>
          </v-stepper-window-item>

          <v-stepper-window-item value="3">
            <h2 class="text-h5">Details</h2>

            <div class="text-body-2 text-medium-emphasis mb-2">
              Thank you for verifying your account, please head over to the <v-btn to="/auth/login/" text="Login" variant="tonal"></v-btn> page.
            </div>
          </v-stepper-window-item>
        </v-stepper-window>

        <v-stepper-actions @click:prev="prev" @click:next="next" />
      </template>
    </v-stepper>

    <div class="text-center text-caption">
      <div class="d-flex align-center justify-center">
        Already have an account?

        <v-btn to="/auth/login/" class="ms-2" text="Login" size="x-small" variant="outlined"></v-btn>
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
