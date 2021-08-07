<template>
  <div>
    <apexchart width="500" type="donut" :options="chartOptions" :series="dataObject.series"></apexchart>
  </div>
</template>

<script>
import Vue from "vue";
import VueApexCharts from 'vue-apexcharts'

Vue.use(VueApexCharts)
Vue.component('apexchart', VueApexCharts)

export default {
  name: "donut-chart-data",
  
  props: {
   dataObject: Object,
   totalLabel: String
  },

  data(props) {
    let chartOptions = { labels: [] };

    chartOptions = {
      labels: props.dataObject.labels,
      colors: ["#c5366e", "#85adff", "#502579"],
      dataLabels: {
        enabled: false
      },
      legend: {
        show: true,
        floating: false,
        position: "right",
        horizontalAlign: "center",
      },
      plotOptions: {
        pie: {
          customScale: 0.8,
          donut: {
            size: "65%",
            labels: {
              show: true,
              name: {
                show: true,
                offsetY: 30,
              },
              value: {
                offsetY: -30,
                fontWeight: 600,
                fontSize: "2.5em"
              },
              total: {
                show: true,
                label: props.totalLabel,
                fontSize: "1.75em",
                color: "black"
                }
            },
          },
        },
      }
    }

    return {
      chartOptions
    }
  }



};

</script>

<style>
.apexcharts-legend {
  text-align: left;
}
</style>

