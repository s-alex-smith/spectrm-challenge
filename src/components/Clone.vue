<template>
    <div>
        <button @click="isOpen = !isOpen">
            <font-awesome-icon icon="ellipsis-v" />
        </button>
        <div v-if="isOpen">
            <span @click="onClickClone" class="dropdown" >
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
            canCloneCard: true,
        }
    },
    
    methods: {
        onClickClone() {
            this.isOpen = !this.isOpen
            this.$emit("clone");
        }
    },
}

</script>

<style>
button {
    background-color: white;
    border: 0;
    color: rgb(83, 82, 82);
    font-size: 1em;
    margin: 0 1.2em;
}

.dropdown {
    padding: 0.2em;
    margin-top: 2em;
    box-shadow: 0.125em 0.125em 0.1875em 0.1875em #979595;
    font-size: 0.75em;
}
</style>
