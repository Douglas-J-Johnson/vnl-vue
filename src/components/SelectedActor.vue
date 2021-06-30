<template>
    <div id="selected-actor">
        <h2>{{ selectedActor.name }}</h2>
        <img id="selected-actor-image" :src="selectedActor.image.original" alt="image"/>
    </div>
</template>

<script>
export default {
    name: "SelectedActor",
    props: {
        selectedActor: Object
    }
}
</script>

<style scoped>
    #selected-actor {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    #selected-actor-image {
        width: 50%;
        margin: 1rem;
    }
</style>