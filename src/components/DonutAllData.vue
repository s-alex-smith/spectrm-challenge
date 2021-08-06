<template>
<div>
    <div v-for="profile in profiles" :key="profile.title">
        <h3>{{profile.title}}</h3>
        <donut-chart-card-single-data :profile="profile" />
    </div>
</div>
</template>

<script>
import DonutChartCardSingleData from './DonutChartCardSingleData.vue';

export default {  
    name: "donut-all-data",

    components: {
        DonutChartCardSingleData
    },
  
    props: {
        profiles: Array
    },

};

</script>