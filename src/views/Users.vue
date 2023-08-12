<template>
<div class="container container--fluid mt-6">
    <v-row class="ma-0">
      <v-col cols="12" lg="12" class="py-0">
         <v-card max-width="650" class="mx-auto">
            <v-card-text>
                <v-table
    fixed-header
    height="300px"
  >
    <thead>
      <tr>
        <th class="text-left">
          Users
        </th>
        <th class="text-left">
          Role
        </th>
      </tr>
    </thead>
    <tbody>
      <tr
        v-for="item in users"
        :key="item.name"
      >
        <td>{{ item.name }}</td>
        <td>{{ item.role }}</td>
      </tr>
    </tbody>
  </v-table>
            </v-card-text>
         </v-card>
        </v-col></v-row></div>

</template>
<script>
  export default {
    data () {
      return {
        users: [
          {
            name: 'Ann',
            role: 'Admin',
          },
          {
            name: 'John',
            role: 'Account Manager',
          },
          {
            name: 'Eclair',
            role: 'Member',
          },
          {
            name: 'Tiffany',
            role: 'Sales Manager',
          },
        ],
      }
    },
  }
</script>
