<template>
  <q-card class="my-card" style="width: 100%; height: 100%">
    <apexchart width="100%" type="donut" :options="options" :series="series">
    </apexchart>
  </q-card>
</template>

<script>
import VueApexCharts from "vue3-apexcharts";

export default {
  components: {
    apexchart: VueApexCharts,
  },
  data: function () {
    return {
      options: {},
      series: [44, 55, 41, 17, 15],
    };
  },
};
</script>
