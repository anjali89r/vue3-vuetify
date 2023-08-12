<template>

   <div class="container container--fluid mt-6">
    <v-row class="ma-0">
      <v-col v-for="(result, key) in results" :key="key" cols="12" sm="3">
        <v-card
    :class="result.type"
    max-width="368"
  >
    <v-card-item :title="result.title">
      <v-icon :color="result.color" icon="mdi-sale-outline"></v-icon>
    </v-card-item>

    <v-card-text>
      <v-row align="center" no-gutters>
        <v-col
          class="text-h8"
          cols="6"
        >
          No. orders
        </v-col>

        <v-col cols="6" class="text-right">
          <v-icon
            :color="result.color"
            :icon="result.icon"
            size="20"
          ></v-icon>{{result.orders}}
        </v-col>
      </v-row>
    </v-card-text>

    <v-divider></v-divider>

    <!-- <v-card-actions>
      <v-btn>
        Learn More
      </v-btn>
    </v-card-actions> -->
  </v-card>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12" md="12">

    <VueApexCharts
      width="800"
      type="bar"
      :options="chartOptions"
      :series="series"
      class="mt-6"
    ></VueApexCharts>

  </v-col>
    </v-row>
   </div>
</template>
<script setup>
import { ref } from 'vue'
import VueApexCharts from 'vue3-apexcharts'
const chartOptions = ref({
        chart: {
          id: "vuechart-example",
        },
        xaxis: {
          categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
        },
      })
const series = ref([
        {
          name: "series-1",
          data: [30, 40, 35, 50, 49, 60, 70, 91],
        },
      ])
  const results = ref([
          {
            title: 'Daily Sales',
            type: 'daily',
            orders: 20,
            color: 'success',
            icon: 'mdi-arrow-up-bold-outline'
          },
          {
            title: 'Weekly Sales',
            type: 'weekly',
            orders: 140,
            color: 'error',
            icon: 'mdi-arrow-down-bold-outline'
          },
          {
            title: 'Monthly Sales',
            type: 'monthly',
            orders: 600,
            color: 'success',
            icon:'mdi-arrow-down-bold-outline'
          },
          {
            title: 'Yearly Sales',
            type: 'yearly',
            orders: 1000,
            color: 'error',
            icon: 'mdi-arrow-up-bold-outline'
          }
        ])
</script>
<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
.v-card.daily {
  border-left: 4px solid #00897b;
}
.v-card.weekly {
  border-left: 4px solid #1e88e5;
}
.v-card.monthly {
  border-left: 4px solid #ffd54f;
}
.v-card.yearly {
  border-left: 4px solid #ba68c8;
}
</style>
