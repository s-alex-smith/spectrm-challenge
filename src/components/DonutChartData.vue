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
   dataObject: Object
  },

  data(props) {
    let chartOptions = { labels: [] };
    chartOptions.labels = props.dataObject.labels;

    return {
      chartOptions
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

