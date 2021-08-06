<template>
  <div>
<!-- <apexchart width="500" type="donut" :options="chartData.chartOptions" :series="chartData.series"></apexchart> -->

    <div v-for="profile in profiles" :key="profile.title">
      <div v-for="data in profile.data" :key="data.label">
        <p>{{data.label}}</p>
        <p>{{data.value}}</p>
      </div>
    </div>
  </div>
</template>

<script>
import Vue, { reactive } from "vue";
import VueApexCharts from 'vue-apexcharts'
Vue.use(VueApexCharts)
Vue.component('apexchart', VueApexCharts)



export default {
  name: "donut-chart-card",
  
  props: {
    profiles: Array,
  },

setup() {
    const chartData = reactive({
      series: [],
      chartOptions: {
        labels: []
      }
    })

    return {
      chartData
    }
  },

methods: {
  testConsole(props) {
    console.log(props)
  }
},

data() {
  return {
    // data.value
    series: [],
    chartOptions: {
      // data.label (legend)
      labels: []
}
  }
}

};

</script>
 <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
/* h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
} */
</style>



    //   data: function() {
    //   return {
    //     chartOptions: {
    //       chart: {
    //         id: 'vuechart-example'
    //       },
    //       xaxis: {
    //         categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998]
    //       }
    //     },
    //     series: [{
    //       name: 'series-1',
    //       data: [30, 40, 35, 50, 49, 60, 70, 91]
    //     }]
    //   }
    // },  
