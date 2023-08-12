<template>
  <!-- <v-app-bar flat>
    <v-app-bar-title>
      <v-icon icon="mdi-circle-slice-4" />

      Base Preset
    </v-app-bar-title>
  </v-app-bar> -->
  <v-app-bar
        color="primary"
        prominent
      >
        <v-app-bar-nav-icon variant="text" @click.stop="drawer = !drawer"></v-app-bar-nav-icon>

        <v-toolbar-title>XYZ</v-toolbar-title>

        <v-spacer></v-spacer>

        <v-btn variant="text" icon="mdi-magnify"></v-btn>

        <v-btn variant="text" icon="mdi-logout" @click="$router.push({name: 'Home'})"></v-btn>
      </v-app-bar>
      <v-navigation-drawer
        v-model="drawer"
      >
        <v-list density="compact" nav>
          <v-list-item prepend-icon="mdi-view-dashboard" title="Dashboard" value="dashboard" @click="$router.push({name: 'Dashboard'})"></v-list-item>
          <v-list-item prepend-icon="mdi-account-group-outline" title="Users" value="users" @click="$router.push({name: 'Users'})"></v-list-item>
        </v-list>
      </v-navigation-drawer>
</template>

<script setup>
  import { ref } from 'vue'
  import { useRoute } from "vue-router"
  const drawer = ref(true)
  const route =useRoute()
  console.log('route: ', route)
</script>
