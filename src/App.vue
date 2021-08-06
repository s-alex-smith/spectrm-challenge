<template>
<div>
  <h1>"Ich bin ein Berliner!"</h1>
  <button @click="testlog">Test Log</button>
  <donut-chart-card :profiles="profiles" />
  <!-- <DonutChartCard /> -->
  </div>
</template>

<script>
import DonutChartCard from '@/components/DonutChartCard.vue'

export default {
  name: 'App',

  components: {
    DonutChartCard
  },


  methods: {
    testConsole() {
      console.log("THIS BETTER FUCKING WORK!");
    }
  },


  data() {
    return {
    "profiles": [
        {
            "title": "Gender",
            "totalLabel": "Total Users",
            "data": [
                {
                    "label": "Female",
                    "value": 50
                },
                {
                    "label": "Male",
                    "value": 35
                },
                {
                    "label": "Diverse",
                    "value": 15
                }
            ]
        },
        {
            "title": "Age Range",
            "totalLabel": "Total Users",
            "data": [
                {
                    "label": "Below 25",
                    "value": 20
                },
                {
                    "label": "Between 25 and 40",
                    "value": 67
                },
                {
                    "label": "Above 40",
                    "value": 13
                }
            ]
        },
        {
            "title": "Country",
            "totalLabel": "Total Users",
            "data": [
                {
                    "label": "Costa Rica",
                    "value": 22
                },
                {
                    "label": "India",
                    "value": 37
                },
                {
                    "label": "Canada",
                    "value": 41
                }
            ]
        }
    ]
}
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
