<template>
  <div>
    <apexchart width="500" type="donut" :options="chartOptions" :series="chartSeries"></apexchart>
  </div>
</template>

<script>
import Vue from "vue";
import VueApexCharts from 'vue-apexcharts'

Vue.use(VueApexCharts)
Vue.component('apexchart', VueApexCharts)

export default {
  name: "donut-chart-card-single-data",
  
  props: {
    profile: Object
  },

  data(props) {
    let chartSeries = [];
    let chartOptions = { labels: [] };

    props.profile.data.map(i => chartSeries.push(i.value))
    props.profile.data.map(i => chartOptions.labels.push(i.label))

    return {
      chartSeries,
      chartOptions,
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

