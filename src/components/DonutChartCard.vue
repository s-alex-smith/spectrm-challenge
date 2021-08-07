<template>
    <div class="card">  
        <span class="card-header">
            <h3>{{profile.title}}</h3>
            <Clone v-if="canClone" @clone="onClone" class="clone"/>
        </span>
        <div>
            <donut-chart-data :dataObject="profile.dataObject" :totalLabel="profile.totalLabel"/>
        </div>
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
.card {
    margin: 0.8em;
    padding: 0.75em;
    display: inline-flex;
    box-shadow: 0.125em 0.125em 0.1875em 0.1875em #979595;
    flex-direction: column;
}

.card-header {
    flex-direction: row;
    display: flex;
    justify-content: space-between;
}

.clone {
    align-self: center;
}

h3 {
    border-bottom: 0.2em dotted grey;
}


</style>