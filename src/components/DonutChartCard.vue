<template>
<div>
    <h3>{{profile.title}}</h3>
    <h4>{{profile.totalLabel}}</h4>
    <Clone v-if="canClone" @clone="onClone"/>
    <donut-chart-data :dataObject="profile.dataObject" />
</div>
</template>

<script>
import DonutChartData from './DonutChartData.vue';
import Clone from './Clone.vue';

export default {  
    name: "donut-all-data",

    components: {
        DonutChartData,
        Clone
    },
  
    props: {
        profile: Object,
        index: Number
    },
    data() {

        return {
            canClone: true
        }
    },


    methods: {
        onClone() {
            this.$emit("clone", this.index)
            this.canClone = false
        }
    },

};

</script>

<style scoped>
button {
    fill: white

}

</style>