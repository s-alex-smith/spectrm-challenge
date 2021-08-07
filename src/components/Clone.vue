<template>
    <div>
        <!-- <div v-if="canCloneCard"> -->
            <button @click="isOpen = !isOpen">
                <font-awesome-icon icon="ellipsis-v" />
            </button>
        <!-- </div> -->
        <div v-if="isOpen">
            <span @click="onClickClone">
                Clone
            </span>
        </div>
    </div>
</template>

<script>

export default {
    name: "clone",

    props: {
        
    },

    data() {
        return {
            isOpen: false,
            // canCloneCard: true,
        }
    },
    
    methods: {
        onClickClone() {
            this.isOpen = !this.isOpen
            // this.canCloneCard = !this.canCloneCard
            this.$emit("clone");
        }
    },
}

</script>

<style>
</style>
