<template>
<div class="app">
  <h1>"Ich bin ein Berliner!"</h1>
    <div v-for="profile in profiles" :key="profile.index">
        <donut-chart-card :profile="profile" @clone="clone" :index="profile.index"/>
    </div>
  </div>
</template>

<script>
import DonutChartCard from './components/DonutChartCard.vue';
import data from './static/data.json';

export default {

  name: 'App',

  components: {
    DonutChartCard

  },

  methods: {
      clone(index) {
          this.profiles.push(this.profiles[index])
      }
  },

  data() {
      let jsonProfiles = data.profiles;
      let profiles = jsonProfiles.map((profile, index) => {
          return {
              index: index,
              title: profile.title,
              totalLabel: profile.totalLabel,
              dataObject: {
                  series: profile.data.map(series => series.value),
                  labels: profile.data.map(label => label.label)
              }
          }
      });
    return {
        profiles
    }
  }
  
}
</script>

<style>
.app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #08396b;
  margin-top: 4em;
  align-self: center;
  font-weight: bold;
}

.h1 {
    border-bottom: 0.1em solid #08396b;
    margin: 0 12em 1em 12em;
}
</style>
