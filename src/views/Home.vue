<!-- eslint-disable vue/multi-word-component-names -->
<template>
<div class="container container--fluid">
    <v-row class="mt-9">
      <v-col cols="12" lg="10">
        <v-card class="pa-5 text-center mx-auto" max-width="600">

            <v-card-title class="justify-center">
              <h4>Log In</h4>
            </v-card-title>
            <v-card-text>
              <v-container>
                <v-row>
                  <v-col cols="12" sm="12" md="12">
                    <v-text-field
                      v-model="email"

                      label="Email/Mobile No*"
                      type="text"
                      required
                      outlined
                      hide-details="auto"
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="12" md="12">
                    <v-text-field
                      v-model="password"


                      name="input-10-1"
                      label="Password*"
                      outlined
                      @keyup.enter="$router.push({name: 'Dashboard'})"
                    ></v-text-field>
                  </v-col>
                </v-row>
              </v-container>
            </v-card-text>

          <v-card-actions class="justify-space-between">
            <!-- <v-btn class="primary" dark text @click="clear()">Clear</v-btn> -->
            <v-btn
              class="text-capitalize font-weight-bold"
              color="#5865f2"
              large
              variant="flat"
              @click="$router.push({name: 'Dashboard'})"
              >login</v-btn
            >
            <v-btn text nuxt small>Forgot Password?</v-btn>
          </v-card-actions>
          <!-- <div v-if="loginError" class="red--text text-center">
            <small>{{ errMsg }}</small>
          </div> -->
        </v-card>
      </v-col>
    </v-row>
   </div>
</template>
<script setup>
import { ref } from 'vue'
 const email = ref('test@gmail.com')
 const password = ref('test')
</script>

